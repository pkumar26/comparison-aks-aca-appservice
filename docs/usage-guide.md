# Usage Guide

Learn how to effectively use the decision tools in this repository to choose the right Azure compute service for your needs.

## Overview

This repository provides three complementary approaches to help you make an informed decision:

1. **[Decision Flowchart](#using-the-decision-flowchart)** - Visual, step-by-step decision tree
2. **[Decision Matrix](#using-the-decision-matrix)** - Quantitative scoring approach
3. **[Detailed Guide](#using-the-detailed-guide)** - In-depth explanations and scenarios

---

## Using the Decision Flowchart

### What It Is

The decision flowchart is an interactive visual guide that walks you through key decision points to recommend the most appropriate Azure service.

### When to Use It

- ✅ You want a quick, intuitive way to explore options
- ✅ You prefer visual decision-making tools
- ✅ You have a general understanding of your requirements
- ✅ You want to see how different paths lead to different services

### How to Use It

**Option 1: View in GitHub (Recommended)**

1. Open the [main README](../README.md)
2. Navigate to the "Decision Flowchart" section
3. GitHub natively renders Mermaid diagrams - you'll see the full flowchart
4. Follow the decision nodes from top to bottom
5. Answer each question based on your requirements
6. Follow the Yes/No paths until you reach a recommendation box

**Option 2: VS Code Interactive Preview**

1. Install the [Mermaid extension](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-mermaid) in VS Code
2. Open [README.md](../README.md) or any diagram file
3. Right-click on the editor → "Open Preview to the Side" (Ctrl+K V)
4. Interact with the diagram in the preview pane
5. Use Ctrl+Mouse Wheel to zoom in/out for better visibility

**Option 3: Mermaid Live Editor**

1. Copy the mermaid code from any `.mmd` file in [diagrams/](../diagrams/)
2. Open [Mermaid Live Editor](https://mermaid.live/)
3. Paste the code into the editor
4. Export as PNG, SVG, or share the link

### Understanding the Flowchart Elements

**Legend Indicators:**
- ✅ **Best fit** - This service is strongly recommended for your scenario
- ⚠️ **Consider carefully** - This service may work but evaluate trade-offs
- ℹ️ **Alternative option** - Valid choice with specific considerations

**Node Types:**
- **Diamond shapes (◆)** - Decision questions (answer Yes or No)
- **Rectangle shapes (▢)** - Recommendation outcomes
- **Grouped boxes** - Related decision categories (e.g., "Technical Requirements")

**Subgraphs (Grouped Sections):**
- **Initial Assessment** - Basic questions to filter services
- **Technical Requirements** - Container and architecture needs
- **Team & Operational Factors** - Skills and complexity tolerance
- **Architecture Patterns** - Event-driven, scale-to-zero, portability
- **Cost & Infrastructure** - Pricing and networking considerations

### Interpretation Tips

**Multiple Recommendations:**
If you reach multiple recommendation boxes (e.g., both AKS and Container Apps appear in different paths):
- Review which path more closely matches your scenario
- Check the descriptions in each recommendation box
- Consider consulting the [Detailed Guide](detailed-decision-guide.md) for scenario validation

**Conflicting Results:**
If your answers lead to a service that doesn't feel right:
- Re-evaluate your answers - some questions may need clarification
- Check the [Decision Matrix](decision-matrix.md) for a quantitative approach
- Review [real-world scenarios](detailed-decision-guide.md#real-world-scenario-walkthroughs) similar to yours

**Using Alternative Layouts:**
- **Vertical layout (Top-Bottom)**: Default view, best for scrolling
- **Horizontal layout (Left-Right)**: Available in [diagrams/decision-tree-horizontal.md](../diagrams/decision-tree-horizontal.md), better for wide screens
- **Simplified version**: [Quick decision tree](../diagrams/decision-tree-simplified.md) with 7 key questions only

---

## Using the Decision Matrix

### What It Is

A scoring-based approach where you rate each requirement (1-5 scale) and calculate weighted scores for each service.

### When to Use It

- ✅ You need a data-driven, objective approach
- ✅ Multiple stakeholders need to align on requirements
- ✅ You want to document decision rationale
- ✅ Your requirements are complex with many competing factors
- ✅ You need to compare services with similar scores

### How to Use It

**Step 1: Open the Decision Matrix**

Navigate to [Decision Matrix](decision-matrix.md)

**Step 2: Rate Each Criterion**

For each of the 12 criteria:
- Read the criterion description
- Rate its importance to your project on a 1-5 scale:
  - **1** = Not important / Not applicable
  - **2** = Slightly important / Basic need
  - **3** = Moderately important / Standard requirement
  - **4** = Very important / Critical requirement
  - **5** = Absolutely essential / Non-negotiable

**Example:**
```
Criterion: Scale-to-Zero Requirement
Your project: Dev environment used only during work hours (8am-6pm)
Your rating: 5 (cost optimization is critical)
```

**Step 3: Calculate Scores**

Use the formulas provided in the Decision Matrix:

```
AKS Score = (C1 × 5) + (C2 × 3) + (C3 × 2) + ... + (C12 × 1)
ACA Score = (C1 × 0) + (C2 × 2.5) + (C3 × 2) + ... + (C12 × 0)
App Service Score = (C1 × 0) + (C2 × 2.5) + (C3 × 1) + ... + (C12 × 3)
```

**Note:** Each criterion has different weight multipliers for each service reflecting how well that service supports that requirement.

**Step 4: Compare Results**

- **Clear winner (>15 point difference)**: Proceed confidently with the highest-scoring service
- **Close competition (5-15 point difference)**: Review criteria weights and organizational factors
- **Tie (<5 point difference)**: All services viable; default to simplicity or consult detailed guide

**Step 5: Validate**

Cross-reference your result with:
- [Threshold recommendations table](decision-matrix.md#interpretation-guidelines)
- [Special cases section](decision-matrix.md#special-cases) for immediate selection scenarios
- [Example walkthroughs](decision-matrix.md#example-scenario-walkthroughs)

### Tips for Best Results

**Be Honest with Ratings:**
- Don't rate everything as 5 (critical)
- Distinguish between "nice to have" and "must have"
- Consider constraints (budget, timeline, team skills)

**Involve Stakeholders:**
- Have technical leads rate operational criteria
- Include business stakeholders for cost and simplicity ratings
- Use average scores if ratings differ significantly

**Document Your Ratings:**
- Save your ratings in a spreadsheet or document
- Include reasoning for high-rated criteria
- Use as decision documentation for future reference

**Re-evaluate Periodically:**
- Requirements change as projects evolve
- Recalculate scores if significant changes occur
- Consider migration paths between services

---

## Using the Detailed Guide

### What It Is

Comprehensive documentation with expanded explanations for each decision criterion and real-world scenario walkthroughs.

### When to Use It

- ✅ You need deep understanding of each decision factor
- ✅ You want to see how others solved similar problems
- ✅ The flowchart or matrix gave unexpected results
- ✅ You're evaluating complex or edge-case scenarios
- ✅ You need to justify your decision to stakeholders

### How to Navigate It

**Section 1: [Understanding Decision Criteria](detailed-decision-guide.md#understanding-decision-criteria)**

For each of the 13 key criteria:
- Detailed explanation of what the criterion means
- Specific examples of when it matters
- Service-by-service breakdown
- Decision guidance

**Section 2: [Real-World Scenario Walkthroughs](detailed-decision-guide.md#real-world-scenario-walkthroughs)**

Five detailed scenarios:
1. **E-Commerce Platform Migration** - Monolith to microservices journey
2. **IoT Data Processing Pipeline** - Event-driven architecture
3. **Multi-Tenant SaaS Platform** - Complex enterprise requirements
4. **Startup MVP** - Fast launch with limited budget
5. **ML Model Training Platform** - GPU workloads and batch processing

Each scenario includes:
- Context and requirements
- Requirements analysis
- Decision process
- Rationale for the chosen service
- Why other services weren't selected

**Section 3: [Migration Considerations](detailed-decision-guide.md#migration-considerations)**

Guidance for moving between services:
- App Service → Container Apps
- App Service → AKS
- Container Apps → AKS
- Estimated effort and complexity

**Section 4: [Common Pitfalls](detailed-decision-guide.md#common-pitfalls)**

Mistakes to avoid for each service with solutions

### How to Use Scenarios

**Finding Similar Scenarios:**

1. Identify your application type:
   - Web application → E-Commerce scenario
   - Event processing → IoT scenario
   - Multi-tenant platform → SaaS scenario
   - Early-stage product → Startup scenario
   - Batch/ML workloads → ML scenario

2. Read the scenario walkthrough completely

3. Compare your requirements to the scenario's requirements analysis

4. Note where your situation differs and adjust conclusions accordingly

**Adapting Scenarios:**

If no scenario matches perfectly:
- Identify the closest 1-2 scenarios
- Extract relevant decision factors from each
- Combine insights to inform your decision
- Use the [Decision Matrix](decision-matrix.md) to quantify differences

---

## Combining Approaches

### Recommended Workflow

For best results, use all three tools in sequence:

**Phase 1: Quick Assessment (15-30 minutes)**
1. Start with the [Decision Flowchart](../README.md#-decision-flowchart)
2. Follow the flow to get initial recommendation
3. Note any questions where you were uncertain

**Phase 2: Quantitative Validation (30-60 minutes)**
1. Complete the [Decision Matrix](decision-matrix.md)
2. Calculate scores for all three services
3. Compare result with flowchart recommendation

**Phase 3: Deep Validation (1-2 hours)**
1. Read relevant sections of the [Detailed Guide](detailed-decision-guide.md)
2. Find and study similar scenarios
3. Review migration paths if transitioning from existing service

**Phase 4: Decision Documentation**
1. Document your decision rationale
2. Include scores from Decision Matrix
3. Reference scenario(s) from Detailed Guide
4. Note any trade-offs or risks

### When Results Disagree

**Flowchart says AKS, but Matrix scores Container Apps higher:**
- Review your "Kubernetes API Access" rating (if rated 5, AKS is correct)
- Check "Operational Complexity" rating (may be overconfident)
- Evaluate team's actual Kubernetes expertise

**Matrix gives tie, but Flowchart recommends one clearly:**
- Trust the flowchart for qualitative factors (team skills, organizational fit)
- Re-examine tied scores for criteria that matter most to your organization
- Default to simpler option if truly uncertain

**Scenarios suggest different service than scores:**
- Your situation may have unique constraints not captured in the matrix
- Review "Common Pitfalls" section for your initial choice
- Consider starting with simpler option and migrating later

---

## Practical Tips

### For Technical Decision Makers

- ✅ Start with flowchart for quick filtering
- ✅ Use matrix to justify decision to management
- ✅ Reference scenarios in architecture design docs
- ✅ Bookmark resources section for implementation phase

### For Business Stakeholders

- ✅ Focus on cost sections in comparison table
- ✅ Review "Deployment Simplicity" in decision matrix
- ✅ Check timeline estimates in detailed scenarios
- ✅ Use [pricing calculator](resources.md#pricing-calculators) early

### For Teams New to Azure

- ✅ Start with simplified flowchart version
- ✅ Default to App Service or Container Apps initially
- ✅ Review [learning resources](resources.md#learning-resources)
- ✅ Consider proof-of-concept before full commitment

### For Migration Projects

- ✅ Review current service capabilities first
- ✅ Check migration sections in detailed guide
- ✅ Estimate effort using migration considerations
- ✅ Consider phased migration approach

---

## Getting Help

### Still Uncertain?

1. **Review the [Comparison Table](comparison-table.md)** - Side-by-side feature comparison
2. **Check [Resources](resources.md)** - Official Azure documentation and decision guides
3. **Open an Issue** - Use our [issue templates](https://github.com/pkumar26/comparison-aks-aca-appservice/issues/new/choose)
   - Request clarification on decision paths
   - Report scenarios not covered
   - Suggest improvements

### Contributing

Found this guide helpful? Consider contributing:
- Add new scenarios from your experience
- Improve decision criteria explanations
- Submit corrections or updates
- See [CONTRIBUTING.md](../CONTRIBUTING.md) for guidelines

---

## Quick Reference

| Task | Tool | Time Required |
|------|------|---------------|
| Quick initial assessment | [Decision Flowchart](../README.md#-decision-flowchart) | 15 min |
| Quantitative comparison | [Decision Matrix](decision-matrix.md) | 30-60 min |
| Deep understanding | [Detailed Guide](detailed-decision-guide.md) | 1-2 hours |
| Feature comparison | [Comparison Table](comparison-table.md) | 15-30 min |
| Find migration path | [Migration Considerations](detailed-decision-guide.md#migration-considerations) | 15 min |
| Explore similar scenarios | [Scenario Walkthroughs](detailed-decision-guide.md#real-world-scenario-walkthroughs) | 30-45 min |

---

[← Back to README](../README.md) | [View Resources →](resources.md)
