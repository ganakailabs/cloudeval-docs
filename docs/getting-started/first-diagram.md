# Generate Your First Diagram

**Automatically Visualize Your Cloud Infrastructure**

Once you've connected your cloud provider, generating your first diagram is just a few clicks away.

## Quick Start

1. **Create a Project**

   - Click **"New Project"** in the dashboard
   - Name your project (e.g., "Production AWS")
   - Select your cloud connection

2. **Configure Resource Filters** (Optional)

   - Choose specific regions
   - Filter by resource types
   - Include/exclude by tags

3. **Generate Diagram**
   - Click **"Generate Diagram"**
   - Wait 30 seconds to 2 minutes
   - Your diagram appears automatically!

## Understanding the Diagram

### Diagram Components

**Nodes (Resources)**

- Each cloud resource appears as a node
- Color-coded by resource type
- Size indicates resource importance

**Edges (Connections)**

- Lines show relationships between resources
- Dependencies and data flows
- Network connections

**Groups (Logical Organization)**

- Resources grouped by:
  - Resource groups (Azure)
  - VPCs (AWS)
  - Projects (GCP)
  - Custom groupings

### Navigation

- **Pan:** Click and drag the canvas
- **Zoom:** Mouse wheel or pinch gesture
- **Fit to Screen:** Double-click canvas
- **Select:** Click on any resource
- **Search:** Use search bar (Ctrl+K)

## Customizing Your Diagram

### Layout Options

**Automatic Layout (Default)**

- AI-powered intelligent positioning
- Best for most use cases
- Automatically updates

**Manual Layout**

- Drag nodes to reposition
- Customize spacing
- Save your layout

**Hierarchical Layout**

- Top-down organization
- Shows dependencies clearly
- Good for documentation

### Styling

**Color Schemes**

- Default (provider colors)
- Security-focused (red/yellow/green)
- Cost-focused (by spending)
- Custom themes

**Node Sizing**

- Uniform size
- By resource importance
- By cost
- By usage

## What Happens During Generation

1. **Resource Discovery** (10-30 seconds)

   - Scans your cloud account
   - Discovers all resources
   - Collects metadata

2. **Relationship Mapping** (10-20 seconds)

   - Identifies connections
   - Maps dependencies
   - Detects network flows

3. **Layout Generation** (10-30 seconds)

   - AI calculates optimal positions
   - Groups related resources
   - Optimizes for readability

4. **Rendering** (5-10 seconds)
   - Draws nodes and edges
   - Applies styling
   - Finalizes diagram

**Total Time:** 30 seconds to 2 minutes (depending on infrastructure size)

## Tips for Best Results

### For Large Environments

- **Use Filters:** Start with specific regions or resource types
- **Focus Areas:** Generate separate diagrams for different areas
- **Incremental:** Add resources gradually

### For Complex Architectures

- **Enable Grouping:** Use logical groupings
- **Hide Details:** Collapse groups to see overview
- **Layers:** Use different views for different concerns

### For Documentation

- **Clean Layout:** Use automatic layout for consistency
- **Labels:** Ensure resource names are visible
- **Legend:** Add custom legends for clarity

## Common Issues

### Empty Diagram

**Problem:** Diagram shows no resources

**Solutions:**

- Verify you have resources in the selected region
- Check resource filters aren't too restrictive
- Ensure IAM permissions are sufficient
- Try refreshing the connection

### Slow Generation

**Problem:** Diagram takes too long

**Solutions:**

- Use resource filters to limit scope
- Start with a specific region
- Check cloud provider API status
- Contact support for optimization

### Missing Resources

**Problem:** Some resources don't appear

**Solutions:**

- Check resource filters
- Verify IAM permissions include those resource types
- Some resources may be in different regions
- Refresh the connection

## Next Steps

Now that you have your first diagram:

1. **[Explore the AI Chat](../tutorials/ai-chat-basics.md)** - Ask questions about your infrastructure
2. **[Customize the Layout](../tutorials/customize-diagrams.md)** - Make it your own
3. **[Export the Diagram](../features/export.md)** - Share with your team
4. **[Add Team Members](../features/collaboration.md)** - Collaborate on diagrams

---

**Ready for more?** Check out our [tutorials](../tutorials/) or [feature guides](../features/)
