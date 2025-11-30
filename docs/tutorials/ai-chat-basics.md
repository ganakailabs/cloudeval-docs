# Tutorial: Use the AI Assistant to Explain Your Infrastructure

**Master cloudeval's AI Chat for Instant Infrastructure Insights**

This tutorial teaches you how to effectively use cloudeval's AI chat assistant to understand, analyze, and optimize your cloud infrastructure.

## Getting Started with AI Chat

### Opening the Chat

**Methods:**

1. Click the **chat icon** (bottom right)
2. Press **Ctrl+K** (Cmd+K on Mac)
3. Use command: `/chat` in search

### Your First Question

Start simple:

```
What resources do I have?
```

The AI will:

- List your resources
- Group by type
- Show counts
- Highlight in diagram

## Question Types

### Discovery Questions

Learn what you have:

```
"Show me all my EC2 instances"
```

```
"List all S3 buckets"
```

```
"What databases are in my account?"
```

```
"Show me all resources in us-east-1"
```

### Analysis Questions

Understand your infrastructure:

```
"Explain the network topology"
```

```
"What's the relationship between these resources?"
```

```
"How does data flow through this architecture?"
```

```
"What are the dependencies for this application?"
```

### Security Questions

Find security issues:

```
"Find all publicly accessible resources"
```

```
"Show me resources without encryption"
```

```
"Which security groups allow port 22 from 0.0.0.0/0?"
```

```
"Identify compliance violations"
```

### Cost Questions

Optimize spending:

```
"What's my current AWS spending?"
```

```
"Find underutilized resources"
```

```
"Show me the most expensive resources"
```

```
"Recommend cost optimizations"
```

### Troubleshooting Questions

Debug issues:

```
"Why can't I access this resource?"
```

```
"Find resources with errors"
```

```
"What changed in the last hour?"
```

```
"Show me all resources in this VPC"
```

## Advanced Techniques

### Context-Aware Questions

The AI understands your current view:

1. **Select a resource** in the diagram
2. Ask: `"What's connected to this?"`
3. AI uses selected resource as context

### Follow-up Questions

Build on previous answers:

```
You: "Show me all databases"
AI: [Lists databases]

You: "Which ones are encrypted?"
AI: [Filters to encrypted databases]

You: "What's the cost of the unencrypted ones?"
AI: [Shows cost analysis]
```

### Diagram Interaction

The AI can modify the diagram:

```
"Highlight all public resources"
```

```
"Zoom to the VPC"
```

```
"Show only EC2 instances"
```

```
"Group resources by environment tag"
```

## Real-World Scenarios

### Scenario 1: Security Audit

**Goal:** Find all security issues

```
You: "Perform a security audit"

AI: I found 5 security issues:
    1. S3 bucket 'public-data' is publicly accessible
    2. Security group 'sg-web' allows SSH from 0.0.0.0/0
    3. RDS database 'prod-db' has encryption disabled
    4. IAM role 'lambda-role' has overly permissive policy
    5. EC2 instance 'web-01' has no security group

    Would you like me to highlight these in the diagram?

You: "Yes, and show recommendations"

AI: [Highlights issues and shows fix recommendations]
```

### Scenario 2: Cost Optimization

**Goal:** Reduce cloud spending

```
You: "What's my current monthly AWS cost?"

AI: Your current monthly AWS spending is $3,450:
    - EC2 instances: $1,800 (52%)
    - RDS databases: $1,200 (35%)
    - S3 storage: $300 (9%)
    - Other: $150 (4%)

You: "Find ways to reduce costs"

AI: I found 3 optimization opportunities:
    1. 5 EC2 instances running at <10% CPU - save $400/month
    2. RDS database can be downsized - save $200/month
    3. 3 S3 buckets with no lifecycle policy - save $50/month

    Total potential savings: $650/month (19%)

You: "Show me the underutilized instances"

AI: [Highlights underutilized instances with details]
```

### Scenario 3: Architecture Understanding

**Goal:** Understand complex architecture

```
You: "Explain this infrastructure"

AI: This is a 3-tier web application:

    Tier 1 - Web Layer:
    - 3 EC2 instances behind Application Load Balancer
    - Auto Scaling Group (2-5 instances)
    - Public subnets in 2 AZs

    Tier 2 - Application Layer:
    - 2 EC2 instances in private subnets
    - Auto Scaling Group (2-4 instances)
    - Connected to web tier via security groups

    Tier 3 - Data Layer:
    - RDS Multi-AZ database
    - ElastiCache cluster
    - S3 buckets for storage

    Network:
    - VPC with public/private subnets
    - NAT Gateway for outbound internet
    - Internet Gateway for inbound traffic

You: "Show me the data flow"

AI: [Highlights data flow paths with arrows]
```

## Pro Tips

### Be Specific

**Bad:** "Tell me about my infrastructure"  
**Good:** "Show me all EC2 instances in production"

### Use Natural Language

You don't need special syntax:

- "Find resources without tags"
- "What's the cost of my databases?"
- "Show me the network flow"

### Combine Questions

Ask multiple things:

```
"Show me all public resources and their costs"
```

### Use Filters

Narrow down scope:

```
"Find EC2 instances in us-east-1 with tag Environment=Production"
```

## Keyboard Shortcuts

- **Ctrl+K** / **Cmd+K:** Open chat
- **Esc:** Close chat
- **Enter:** Send message
- **Shift+Enter:** New line
- **↑:** Previous message
- **↓:** Next message
- **Tab:** Autocomplete

## Limitations

The AI chat:

- Can read and analyze your infrastructure
- Can provide insights and recommendations
- Can highlight and filter resources
- Cannot modify your infrastructure
- Cannot access your data
- Cannot make changes to resources

## Next Steps

- **[Customize Diagrams](customize-diagrams.md)** - Perfect your diagrams
- **[Export Diagrams](../features/export.md)** - Share your work
- **[Collaborate](../features/collaboration.md)** - Work with your team

---

**Ready to master AI chat?** Try asking questions about your infrastructure now!
