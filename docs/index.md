# Cloudeval Documentation

**Stop Manually Drawing Cloud Diagrams – Here's the 2-Minute Fix**

Welcome to Cloudeval, the AI-powered cloud infrastructure visualization platform that automatically generates architecture diagrams from your Infrastructure as Code.

## What is Cloudeval?

Cloudeval is an AI-powered cloud diagramming tool designed for DevOps engineers, SREs, and cloud architects. It automatically visualizes your Azure infrastructure from ARM templates, generates interactive diagrams, and provides AI-powered insights through natural language chat.

### Core Capabilities

![Infrastructure as Code](assets/images/features/infra-as-code.png)

- **Infrastructure as Code** - Upload ARM templates to generate diagrams (Bicep support coming Early Feb 2026)
- **AI-Powered Diagram Generation** - Intelligent layouts that make sense of complex architectures

<video controls preload="metadata" style="min-width: 600px; max-width: 100%; height: auto; display: block; margin: 1.5rem auto;">
  <source src="assets/videos/automated-diagrams.webm" type="video/webm">
  Your browser does not support the video tag.
</video>

- **Chat with Your Infrastructure** - Ask questions in plain English and get instant answers

<video controls preload="metadata" style="min-width: 600px; max-width: 100%; height: auto; display: block; margin: 1.5rem auto;">
  <source src="assets/videos/chat-with-your-cloud.webm" type="video/webm">
  Your browser does not support the video tag.
</video>

- **Web Editor for IaC** - Edit your ARM templates directly in the browser

<video controls preload="metadata" style="min-width: 600px; max-width: 100%; height: auto; display: block; margin: 1.5rem auto;">
  <source src="assets/videos/web-editor.webm" type="video/webm">
  Your browser does not support the video tag.
</video>

- **Export & Share** - Export diagrams as PNG, Visio, or draw.io formats
- **Real-Time Collaboration** - Work with your team on infrastructure diagrams
- **Interactive Visualizations** - Cost, security, and WAF overlays

## Quick Start

Get up and running in minutes:

1. **[Try the Playground](https://cloudeval.ai/playground)** - Explore features without signing up
2. **[Sign up](https://cloudeval.ai/signup)** for a free account
3. **[Upload your ARM template](getting-started/overview.md)** - Generate your first diagram
4. **[Start chatting](getting-started/ai-chat.md)** with your infrastructure

## Key Value Propositions

### Speed

Stop spending hours manually drawing diagrams. Cloudeval generates accurate architecture diagrams from your Infrastructure as Code in seconds.

### Clarity

Visualize complex Azure environments with intelligent layouts that show relationships and dependencies from your ARM templates.

### Automation

AI handles the heavy lifting—from parsing your Infrastructure as Code to diagram generation to answering questions.

### Accuracy

Always up-to-date diagrams that reflect your actual infrastructure code, eliminating documentation drift.

## Popular Guides

- **[Getting Started Guide](getting-started/overview.md)** - From sign-up to first diagram
- **[Work with ARM Templates](tutorials/arm-templates.md)** - ARM template visualization
- **[AI Chat Tutorial](tutorials/ai-chat-basics.md)** - Master the AI assistant
- **[Export Diagrams](features/export.md)** - Share your diagrams

## Try Cloudeval Free

**[Launch Playground](https://cloudeval.ai/playground)** - Try features without signing up  
**[Sign Up Free](https://cloudeval.ai/signup)** - No credit card required

---

## FAQ

### What is Cloudeval?

Cloudeval is an AI-powered cloud infrastructure visualization platform that automatically generates architecture diagrams from your Infrastructure as Code (ARM templates), answers questions about your infrastructure, and provides interactive visualizations.

### How does Cloudeval work?

1. Upload your ARM template
2. Cloudeval parses and analyzes the code
3. Maps resources and dependencies
4. Generates interactive diagrams
5. You can ask questions, edit code, and export diagrams

### Is Cloudeval secure?

Yes. Cloudeval:

- **No Cloud Access Required** - Works entirely from your code files
- **Encrypted Storage** - All data encrypted at rest and in transit
- **No Data Sharing** - Your infrastructure code is never shared

### What Infrastructure as Code formats are supported?

**Available Now:**

- Azure ARM Templates (JSON)
- Modular templates (linked templates)
- Parameter files

**Coming Soon:**

- Azure Bicep files - Early Feb 2026 ([View roadmap](https://cloudeval.ai/home/roadmap))
- Terraform - Early Feb 2026 ([View roadmap](https://cloudeval.ai/home/roadmap))
- AWS CloudFormation - Early Feb 2026 ([View roadmap](https://cloudeval.ai/home/roadmap))

### Can I connect my Azure account directly?

::: warning Coming Soon
Direct Azure account connection is coming in **March 2026** as part of our "Azure Cloud Sync v1" release. [View roadmap](https://cloudeval.ai/home/roadmap) for details.

Cloudeval currently works with Infrastructure as Code files (ARM templates). **[Join our waitlist](https://cloudeval.ai/waitlist)** to be notified when this feature launches.
:::

### Do I need to install anything?

No. Cloudeval is a web-based application. Just sign up and use it in your browser.

### How do I get started?

1. **[Try the Playground](https://cloudeval.ai/playground)** - Explore features without signing up
2. **[Sign up](https://cloudeval.ai/signup)** for a free account
3. **[Upload your ARM template](getting-started/overview.md)**
4. Generate your first diagram

### What is the Playground?

The [Playground](https://cloudeval.ai/playground) is an interactive demo where you can:

- Explore sample infrastructure diagrams
- Try the AI chat assistant
- Test diagram features
- Learn Cloudeval without uploading files

**No sign-up required!**

### How do I upload my ARM template?

1. Create a new project
2. Click **"Upload File"**
3. Select your ARM template (`.json`) file
4. Cloudeval automatically parses and generates the diagram

### How long does it take to generate a diagram?

Typical times:

- Small template (< 20 resources): 5-10 seconds
- Medium template (20-100 resources): 10-30 seconds
- Large template (100-500 resources): 30-60 seconds
- Very large template (> 500 resources): 1-2 minutes

### How do I export diagrams?

Click **Export** and choose format:

- PNG (images)
- SVG (vector)
- Visio (VSDX)
- draw.io (XML)
- PDF (documents)

### What's the maximum template size?

Cloudeval can handle:

- **Free tier:** Up to 1,000 resources per template
- **Pro tier:** Up to 10,000 resources per template
- **Enterprise:** Unlimited resources

---

## Community

### Join Our Community

**Discord Server**

Join our Discord for:

- Real-time help and support
- Feature discussions
- Tips and tricks
- User showcases

**[Join Discord →](https://discord.gg/tk5dcU2a7T)**

**GitHub Discussions**

Participate in:

- Feature requests
- Bug reports
- Documentation improvements
- Q&A

**[GitHub Discussions →](https://github.com/ganakailabs/cloudeval/discussions)**

### Contribute

**Suggest Documentation Improvements**

Found an error or have a suggestion?

1. Click **"Suggest an Edit"** on any page
2. Make your changes
3. Submit a pull request
4. We'll review and merge

**Report Bugs**

Found a bug?

1. [Open an issue](https://github.com/ganakailabs/cloudeval/issues)
2. Describe the problem
3. Include steps to reproduce
4. Add screenshots if helpful

**Request Features**

Have an idea?

1. [Start a discussion](https://github.com/ganakailabs/cloudeval/discussions)
2. Describe your use case
3. Explain the benefit
4. Get community feedback

---

## Support

### Contact Support

**Email Support**

- **Support:** [support@ganak.ai](mailto:support@ganak.ai)

**Response Time:**

- Free tier: Within 48 hours
- Pro tier: Within 24 hours
- Enterprise: Within 4 hours (SLA)

### Self-Service Resources

**Documentation**

- **[Getting Started](getting-started/overview.md)** - Start here
- **[Tutorials](tutorials/)** - Step-by-step guides
- **[Feature Guides](features/)** - Deep dives

**Community**

- **[Discord](https://discord.gg/tk5dcU2a7T)** - Real-time help
- **[GitHub Discussions](https://github.com/ganakailabs/cloudeval/discussions)** - Q&A

### Before Contacting Support

To help us help you faster:

1. **Check Documentation** - Your answer might be in the docs
2. **Search FAQ** - Common issues are covered above
3. **Check Community** - Others may have asked the same question
4. **Gather Information:**
   - Error messages
   - Steps to reproduce
   - Screenshots
   - Browser/OS information

### Bug Reports

Found a bug?

1. [Open an issue](https://github.com/ganakailabs/cloudeval/issues)
2. Use the bug report template
3. Include:
   - Steps to reproduce
   - Expected behavior
   - Actual behavior
   - Screenshots/logs
   - Environment details

### Security Issues

**Important:** For security vulnerabilities, email [support@ganak.ai](mailto:support@ganak.ai) directly. Do not post publicly.

---

**Need more help?** [View full documentation](getting-started/overview.md) or [contact support](mailto:support@ganak.ai)
