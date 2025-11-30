# Using the AI Chat Assistant

**Ask Questions About Your Infrastructure in Plain English**

cloudeval's AI chat assistant understands your infrastructure and can answer questions, provide insights, and help you optimize your cloud setup.

<video controls preload="metadata" style="min-width: 600px; max-width: 100%; height: auto; display: block; margin: 1.5rem auto;">
  <source src="../assets/videos/chat-with-your-cloud.webm" type="video/webm">
  Your browser does not support the video tag.
</video>

## Getting Started

### Opening the Chat

1. Click the **chat icon** in the bottom right corner
2. Or press **Ctrl+K** (Cmd+K on Mac)
3. The chat panel opens

### Your First Question

Try asking:

```
Show me all resources with public access
```

The AI will:
1. Analyze your infrastructure
2. Identify public resources
3. Highlight them in the diagram
4. Provide a detailed response

## Common Use Cases

### Security Questions

```
"Find all resources without encryption"
"Show me publicly accessible storage buckets"
"Which resources have overly permissive IAM policies?"
"Identify security vulnerabilities in my VPC"
```

### Cost Questions

```
"What's my current AWS spending?"
"Find underutilized EC2 instances"
"Show me the most expensive resources"
"Recommend cost optimizations"
```

### Architecture Questions

```
"Explain the network topology of my VPC"
"Show me all resources connected to this database"
"What's the dependency chain for this application?"
"Visualize the data flow in my architecture"
```

### Troubleshooting

```
"Why is this resource not accessible?"
"Find all resources in this region"
"Show me resources with errors"
"What changed in the last 24 hours?"
```

## Advanced Features

### Context Awareness

The AI understands:
- Your current diagram view
- Selected resources
- Recent changes
- Your cloud provider

### Follow-up Questions

Ask follow-ups without repeating context:

```
User: "Show me all databases"
AI: [Lists databases]
User: "Which ones are encrypted?"
AI: [Filters to encrypted databases]
```

### Diagram Interaction

The AI can:
- Highlight resources in the diagram
- Zoom to specific areas
- Filter the view
- Create new diagrams

## Tips for Best Results

### Be Specific

**Bad:** "Tell me about my infrastructure"  
**Good:** "Show me all EC2 instances in us-east-1"

### Use Natural Language

You don't need special syntax:
- "Find resources without tags"
- "What's the cost of my S3 buckets?"
- "Show me the network flow"

### Ask Follow-ups

Build on previous answers:
1. "Show me all databases"
2. "Which ones are public?"
3. "What's the cost of the public ones?"

## Example Conversations

### Security Audit

```
You: Find all publicly accessible resources

AI: I found 3 publicly accessible resources:
    - S3 bucket: my-public-bucket
    - EC2 instance: web-server-01
    - RDS database: public-db
    
    Would you like me to show security recommendations?

You: Yes, and highlight them in the diagram

AI: [Highlights resources and shows recommendations]
```

### Cost Optimization

```
You: What's my current AWS spending?

AI: Your current monthly AWS spending is $2,450:
    - EC2 instances: $1,200 (49%)
    - RDS databases: $800 (33%)
    - S3 storage: $300 (12%)
    - Other: $150 (6%)
    
    I found 5 underutilized instances that could save $400/month.

You: Show me those instances

AI: [Highlights underutilized instances]
```

## Keyboard Shortcuts

- **Ctrl+K** / **Cmd+K**: Open chat
- **Esc**: Close chat
- **Enter**: Send message
- **Shift+Enter**: New line
- **↑**: Previous message
- **↓**: Next message

## Limitations

The AI chat:
- Can read your infrastructure
- Can analyze and provide insights
- Can highlight resources
- Cannot modify your infrastructure
- Cannot access your data
- Cannot make changes to resources

## Privacy & Security

- All queries processed securely
- No data stored permanently
- Conversations encrypted
- No sharing with third parties

## Next Steps

- **[Customize Diagrams](../tutorials/customize-diagrams.md)** - Perfect your diagrams
- **[Export Diagrams](../features/export.md)** - Share your work
- **[Collaborate](../features/collaboration.md)** - Work with your team

---

**Have questions?** [Join our community](../community.md) or [contact support](../support.md)

