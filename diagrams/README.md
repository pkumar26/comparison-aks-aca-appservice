# Diagram Files Overview

This directory contains decision tree diagrams in multiple formats to help you choose between Azure Kubernetes Service (AKS), Azure Container Apps (ACA), and Azure App Service.

## Available Diagram Formats

### 📊 Comprehensive Decision Trees

**Vertical Layout (Top-Bottom)**
- **File**: [decision-tree-vertical.mmd](decision-tree-vertical.mmd) (standalone) | [decision-tree-vertical.md](decision-tree-vertical.md) (embedded)
- **Best for**: Scrolling, standard displays, GitHub viewing
- **Contains**: 15 decision nodes organized in 5 themed subgraphs
- **Use when**: Reading on mobile, tablet, or portrait-oriented displays

**Horizontal Layout (Left-Right)**
- **File**: [decision-tree-horizontal.mmd](decision-tree-horizontal.mmd) (standalone) | [decision-tree-horizontal.md](decision-tree-horizontal.md) (embedded)
- **Best for**: Wide screens, landscape displays, presentation mode
- **Contains**: Same 15 decision nodes, optimized for left-to-right flow
- **Use when**: Working on ultra-wide monitors or presenting to teams

### 🚀 Quick Decision Tree

**Simplified Version**
- **File**: [decision-tree-simplified.md](decision-tree-simplified.md)
- **Best for**: Fast initial assessment, time-constrained decisions
- **Contains**: 7 key questions for rapid filtering
- **Use when**: Need quick recommendation before deep analysis

## File Types Explained

### `.mmd` Files (Standalone Mermaid)
- Pure mermaid diagram syntax
- Can be copied to [Mermaid Live Editor](https://mermaid.live/)
- Used by GitHub Actions to generate PNG/SVG exports
- Import into tools supporting mermaid syntax

### `.md` Files (Embedded Markdown)
- Mermaid diagrams embedded in markdown documents
- Includes context, usage instructions, and navigation links
- Renders natively on GitHub
- Best for documentation and reference

### Exported Formats (Auto-Generated)

**PNG and SVG files** are automatically generated from `.mmd` files via GitHub Actions:
- Located in [`exports/png/`](exports/png/) and [`exports/svg/`](exports/svg/) directories
- Created on every push to main branch
- Transparent backgrounds for universal compatibility
- Useful for presentations, documentation, and offline viewing

## How to Use These Diagrams

### Option 1: View on GitHub (Recommended)
1. Open any `.md` file in this directory
2. GitHub automatically renders mermaid diagrams
3. Scroll through and follow decision paths

### Option 2: VS Code with Mermaid Extension
1. Install [Mermaid extension](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-mermaid)
2. Open any `.md` or `.mmd` file
3. Right-click → "Open Preview to the Side" (Ctrl+K V)
4. Interactive navigation and zoom support

### Option 3: Mermaid Live Editor
1. Copy contents of any `.mmd` file
2. Open [Mermaid Live Editor](https://mermaid.live/)
3. Paste and explore interactively
4. Export as PNG, SVG, or share link

### Option 4: Exported Images
1. Navigate to `exports/png/` or `exports/svg/`
2. Download generated diagram files
3. Use in presentations, documentation, or offline

## Diagram Elements Guide

### Node Types

**Start/End Nodes** (Rounded rectangles)
- `([Start: Text])` - Entry point of decision tree
- Visual cue for where to begin

**Decision Nodes** (Diamonds)
- `{Question?}` - Questions requiring Yes/No answer
- Follow arrows based on your answer

**Recommendation Nodes** (Rectangles)
- `[Service Name]` - Final recommendation
- Includes confidence indicator and use case

**Subgraphs** (Grouped boxes)
- Groups related decision criteria
- Examples: "Initial Assessment", "Technical Requirements"

### Confidence Indicators

- ✅ **Best fit** - Strongly recommended for this scenario
- ⚠️ **Consider carefully** - May work but evaluate trade-offs
- ℹ️ **Alternative option** - Valid choice with specific considerations

### Color Coding

- 🟢 **Green** (#4caf50) - Best fit recommendations
- 🟠 **Orange** (#ff9800) - Consider carefully
- 🔵 **Blue** (#2196f3) - Alternative options
- 🟡 **Yellow** (#fff3cd) - Legend/informational nodes
- 🔷 **Light blue** (#e1f5ff) - Start node

## Modifying Diagrams

### To Edit Diagrams

1. Edit the `.mmd` file (standalone mermaid syntax)
2. Test changes in [Mermaid Live Editor](https://mermaid.live/)
3. Update corresponding `.md` file with same changes
4. Commit and push - GitHub Actions will regenerate exports

### Mermaid Syntax Resources

- [Mermaid Documentation](https://mermaid.js.org/)
- [Flowchart Syntax](https://mermaid.js.org/syntax/flowchart.html)
- [Styling Guide](https://mermaid.js.org/config/theming.html)

## Exported Diagram Locations

When diagrams are auto-generated:

```
diagrams/
├── exports/
│   ├── png/
│   │   ├── decision-tree-vertical.png
│   │   ├── decision-tree-horizontal.png
│   │   └── ...
│   └── svg/
│       ├── decision-tree-vertical.svg
│       ├── decision-tree-horizontal.svg
│       └── ...
```

## Which Diagram Should I Use?

| Your Situation | Recommended Diagram |
|----------------|---------------------|
| First-time visitor | [Simplified version](decision-tree-simplified.md) |
| On mobile/tablet | [Vertical layout](decision-tree-vertical.md) |
| On ultra-wide monitor | [Horizontal layout](decision-tree-horizontal.md) |
| Presenting to team | Exported PNG/SVG from `exports/` |
| Need offline copy | Download from `exports/` |
| Comprehensive analysis | [Vertical layout](decision-tree-vertical.md) |
| Embedding in docs | Use `.mmd` file or exported SVG |

## Diagram Versioning

- Diagrams are versioned with the repository
- Changes tracked in Git history
- Exported files regenerated on each update
- Check [CHANGELOG](../CHANGELOG.md) for major diagram updates

## Contributing

To suggest diagram improvements:
1. [Open an issue](https://github.com/pkumar26/comparison-aks-aca-appservice/issues/new/choose) with proposed changes
2. Describe which decision paths need adjustment
3. Provide rationale for changes
4. See [CONTRIBUTING.md](../CONTRIBUTING.md) for full guidelines

---

[← Back to Main README](../README.md) | [View Comparison Table →](../docs/comparison-table.md)
