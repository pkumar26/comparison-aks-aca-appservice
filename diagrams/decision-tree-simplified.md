# Decision Tree - Simplified Version

A streamlined 7-question decision tree for quick service selection when you need a fast answer.

## When to Use This

- ✅ You need a quick initial recommendation
- ✅ Your requirements are straightforward
- ✅ You want to filter services before deep analysis
- ✅ Time-constrained decision making

**For comprehensive analysis**, use the [full decision tree](decision-tree-vertical.md) or [decision matrix](../docs/decision-matrix.md).

## Quick Decision Tree

```mermaid
flowchart TB
    Start([Choose Azure Compute Service]) --> Q1{Need Kubernetes<br/>API access?}
    
    Q1 -->|Yes| AKS1[✅ AKS<br/>Full Kubernetes control<br/>API access required]
    Q1 -->|No| Q2{Using<br/>containers?}
    
    Q2 -->|No| Q3{Traditional<br/>web app?}
    Q2 -->|Yes| Q4{Need<br/>scale-to-zero?}
    
    Q3 -->|Yes| AppService1[✅ App Service<br/>Simple PaaS<br/>Fast deployment]
    Q3 -->|No| Q4
    
    Q4 -->|Yes| ACA1[✅ Container Apps<br/>Serverless containers<br/>Cost-optimized]
    Q4 -->|No| Q5{Complex<br/>microservices<br/>15+ services?}
    
    Q5 -->|Yes| Q6{Team has<br/>K8s expertise?}
    Q5 -->|No| Q7{Event-driven<br/>architecture?}
    
    Q6 -->|Yes| AKS2[✅ AKS<br/>Complex orchestration<br/>Full control]
    Q6 -->|No| ACA2[⚠️ Container Apps<br/>Simpler than AKS<br/>Consider K8s training]
    
    Q7 -->|Yes| ACA3[✅ Container Apps<br/>Built-in KEDA<br/>Event-driven ready]
    Q7 -->|No| Decision{Prefer simplicity<br/>over control?}
    
    Decision -->|Yes| ACA4[ℹ️ Container Apps<br/>Managed infrastructure<br/>Lower complexity]
    Decision -->|No| AKS3[ℹ️ AKS<br/>Maximum flexibility<br/>Higher complexity]
    
    style Start fill:#e1f5ff
    style AKS1 fill:#4caf50
    style AKS2 fill:#4caf50
    style AKS3 fill:#2196f3
    style ACA1 fill:#4caf50
    style ACA2 fill:#ff9800
    style ACA3 fill:#4caf50
    style ACA4 fill:#2196f3
    style AppService1 fill:#4caf50
    style Legend fill:#fff3cd
```

## Decision Shortcuts

### Immediate Selections

**Choose AKS if:**
- ✅ You need Kubernetes API access (no alternatives)
- ✅ 15+ microservices with complex orchestration
- ✅ Team has strong Kubernetes expertise
- ✅ Multi-cloud portability is required

**Choose Container Apps if:**
- ✅ Need scale-to-zero for cost savings
- ✅ Event-driven architecture (queues, events)
- ✅ Want containers without Kubernetes complexity
- ✅ Variable/unpredictable traffic patterns

**Choose App Service if:**
- ✅ Traditional web application or API
- ✅ Not using containers (native code deployment)
- ✅ Need fastest time to production
- ✅ Team has limited DevOps experience

## Next Steps After Quick Decision

1. **Validate your choice** with the [comprehensive decision tree](decision-tree-vertical.md)
2. **Score your requirements** using the [decision matrix](../docs/decision-matrix.md)
3. **Review similar scenarios** in the [detailed guide](../docs/detailed-decision-guide.md)
4. **Compare features** in the [comparison table](../docs/comparison-table.md)

## What's Missing from Simplified Version?

This simplified tree omits these important considerations:
- Operational complexity tolerance
- Cost model preferences
- Networking requirements
- Legacy dependency support
- Portability needs across clouds
- Team expertise assessment

**Recommendation:** Use this for initial filtering, then validate with comprehensive tools.

---

[← Back to Main README](../README.md) | [View Full Decision Tree →](decision-tree-vertical.md)
