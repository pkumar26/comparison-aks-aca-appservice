# Decision Tree - Vertical Layout (Top-Bottom)

This is the vertical layout of the comprehensive Azure service decision tree, best suited for scrolling and reading on standard displays.

## How to Use

1. **Start at the top** with the legend to understand recommendation indicators
2. **Answer each question** in the decision nodes (diamonds)
3. **Follow Yes/No paths** until you reach a recommendation box
4. **Review confidence indicators:**
   - ✅ Best fit
   - ⚠️ Consider carefully
   - ℹ️ Alternative option

## Decision Tree

```mermaid
flowchart TB
    Start([Start: Choose Azure Compute Service]) --> InitialAssessment
    
    subgraph InitialAssessment[" Initial Assessment "]
        Q1{Need Kubernetes<br/>API access?}
        Q2{Is this a web<br/>application or API?}
    end
    
    subgraph TechnicalRequirements[" Technical Requirements "]
        Q3{Using containers?}
        Q4{Microservices<br/>architecture?}
        Q5{Need custom<br/>orchestration?}
        Q6{Legacy dependencies<br/>COM, registry, MSI?}
    end
    
    subgraph TeamOperationalFactors[" Team & Operational Factors "]
        Q7{Team has<br/>Kubernetes expertise?}
        Q8{Can handle high<br/>operational complexity?}
    end
    
    subgraph ArchitecturePatterns[" Architecture Patterns "]
        Q9{Need scale-to-zero<br/>capability?}
        Q10{Event-driven<br/>architecture?}
        Q11{Portability across<br/>clouds required?}
    end
    
    subgraph CostInfrastructure[" Cost & Infrastructure "]
        Q12{Consumption-based<br/>pricing preferred?}
        Q13{Need advanced<br/>networking control?}
    end
    
    Q1 -->|Yes| AKS1[✅ AKS<br/>Full Kubernetes API access<br/>Maximum control]
    Q1 -->|No| Q2
    
    Q2 -->|Yes| Q3
    Q2 -->|No| Q3
    
    Q3 -->|No| Q6
    Q3 -->|Yes| Q4
    
    Q4 -->|No| AppService1[✅ App Service<br/>Simple deployment<br/>Single application focus]
    Q4 -->|Yes| Q5
    
    Q5 -->|Yes| Q7
    Q5 -->|No| Q9
    
    Q6 -->|Yes| AppService2[✅ App Service<br/>Supports legacy components<br/>Windows containers]
    Q6 -->|No| AppService3[✅ App Service<br/>Traditional web hosting<br/>Built-in features]
    
    Q7 -->|Yes| Q8
    Q7 -->|No| Q9
    
    Q8 -->|Yes| Q11
    Q8 -->|No| ACA1[✅ Container Apps<br/>Kubernetes benefits<br/>Without complexity]
    
    Q9 -->|Yes| Q12
    Q9 -->|No| Q10
    
    Q10 -->|Yes| ACA2[✅ Container Apps<br/>Built-in KEDA scaling<br/>Event-driven ready]
    Q10 -->|No| Q13
    
    Q11 -->|Yes| AKS2[✅ AKS<br/>Kubernetes portability<br/>Multi-cloud ready]
    Q11 -->|No| Q13
    
    Q12 -->|Yes| ACA3[✅ Container Apps<br/>Pay-per-execution<br/>Scale-to-zero]
    Q12 -->|No| Q13
    
    Q13 -->|Yes| AKS3[⚠️ AKS<br/>Custom networking<br/>Network policies]
    Q13 -->|No| Decision
    
    Decision{Complex<br/>microservices?}
    Decision -->|Yes| AKS4[✅ AKS<br/>Full orchestration<br/>Enterprise-grade]
    Decision -->|No| ACA4[ℹ️ Container Apps<br/>Simpler microservices<br/>Managed infrastructure]
    
    style Start fill:#e1f5ff
    style AKS1 fill:#4caf50
    style AKS2 fill:#4caf50
    style AKS3 fill:#ff9800
    style AKS4 fill:#4caf50
    style ACA1 fill:#4caf50
    style ACA2 fill:#4caf50
    style ACA3 fill:#4caf50
    style ACA4 fill:#2196f3
    style AppService1 fill:#4caf50
    style AppService2 fill:#4caf50
    style AppService3 fill:#4caf50
    style Legend fill:#fff3cd
```

## Interactive Options

- **In VS Code**: Install [Mermaid extension](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-mermaid), then right-click and "Open Preview to the Side"
- **Online Editor**: Copy diagram code to [Mermaid Live Editor](https://mermaid.live/) for interactive exploration
- **Export**: Use Mermaid Live Editor to export as PNG or SVG

## Alternative Views

- [Horizontal Layout](decision-tree-horizontal.md) - Left-to-right flowchart for wide screens
- [Simplified Version](decision-tree-simplified.md) - Quick 7-question decision tree
- [All Diagrams](README.md) - Overview of available diagram formats

---

[← Back to Main README](../README.md) | [View Diagrams Overview →](README.md)
