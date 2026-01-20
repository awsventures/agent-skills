# Content Creation Skill

Professional content creation templates for business communications, technical documents, and presentations.

## Overview

This skill provides structured templates for creating professional business content. It uses a three-layer architecture inspired by Trevor Longino's [instant-marketing-mastery](https://github.com/TrevorLongino/instant-marketing-mastery) framework, adapted for general professional use.

## Three-Layer Architecture

### Layer 1: Global Writing Standards
[writing-standards.md](writing-standards.md) - Core writing principles applied to all content
- Professional voice and tone
- Structure and formatting
- Style guidelines (active voice, varied sentences, contractions)
- Human elements (specific details, thoughtful qualifiers)
- Quality standards

### Layer 2: Content-Type Templates
Specialized templates for different content types, organized by category:

**Communications** ([communications/](communications/))
- [professional-email.md](communications/professional-email.md) - Business emails
- [memo.md](communications/memo.md) - Internal memos
- [announcement.md](communications/announcement.md) - Organizational announcements

**Documents** ([documents/](documents/))
- [reports.md](documents/reports.md) - Status, analysis, incident, performance reports
- [proposals.md](documents/proposals.md) - Project, budget, process, technology proposals
- [documentation.md](documents/documentation.md) - Technical docs, how-to guides, runbooks

**Presentations** ([presentations/](presentations/))
- [slide-content.md](presentations/slide-content.md) - Presentation slides
- [talking-points.md](presentations/talking-points.md) - Speaker notes and meeting prep

### Layer 3: Execution
Each template follows this pattern:
1. References global writing standards
2. Provides specifications for that content type
3. Asks clarifying questions before creating content
4. Includes quality checks
5. Shows examples of what works

## Quick Start

### Using with Claude Code

The skill is automatically available in Claude Code:

```
Just ask for what you need:
- "Write a professional email to my team about [topic]"
- "Create a proposal for [project]"
- "Draft slides for a presentation on [topic]"
```

Claude will:
1. Select the appropriate template
2. Ask clarifying questions
3. Create content following writing standards
4. Apply quality checks
5. Deliver polished content

### Using with Other AI Chat Interfaces

If you're using ChatGPT, Gemini, or other chat interfaces, you can copy the relevant template content and use it in your conversation.

**Example workflow**:
1. Copy content from [writing-standards.md](writing-standards.md)
2. Copy content from the specific template you need (e.g., [communications/professional-email.md](communications/professional-email.md))
3. Paste both into your chat
4. Answer the clarifying questions
5. Receive your content

## File Structure

```
content-creation/
├── SKILL.md                          # Main skill definition for Claude Code
├── README.md                         # This file - overview and usage
├── writing-standards.md              # Global writing standards (Layer 1)
│
├── communications/                   # Communication templates (Layer 2)
│   ├── professional-email.md         # Email template
│   ├── memo.md                       # Memo template
│   └── announcement.md               # Announcement template
│
├── documents/                        # Document templates (Layer 2)
│   ├── reports.md                    # Report template (status, analysis, etc.)
│   ├── proposals.md                  # Proposal template (project, budget, etc.)
│   └── documentation.md              # Documentation template (technical, how-to, etc.)
│
└── presentations/                    # Presentation templates (Layer 2)
    ├── slide-content.md              # Slide content template
    └── talking-points.md             # Talking points and speaker notes template
```

## Template Pattern

Each template follows this structure:

```markdown
Reference the writing standards in ../writing-standards.md, then create [content type] following these specifications:

## [Content Type] Specifications
- Structure requirements
- Content types/variations
- Format elements

## Prompt for [Content Type] Creation
1. Question 1
2. Question 2
...

## Output Format
What will be delivered

## Quality Checks Applied
✓ Check 1
✓ Check 2
...

## Example Outputs
### Example 1: [Type]
[Detailed example with explanation]
```

This pattern ensures:
- Consistency across all content types
- Clear requirements and specifications
- Guided question-based approach
- Quality standards applied
- Examples showing best practices

## Key Features

### Professional Standards
- Based on classical writing principles (Strunk & White, Orwell)
- Modern business communication best practices
- Anti-AI detection elements (human-sounding writing)

### Human-Sounding Content
- Natural contractions (I'm, you're, don't)
- Varied sentence and paragraph length
- Specific, contextual details
- Thoughtful qualifiers when appropriate
- Conversational but professional tone

### Structured Approach
- Clear templates for each content type
- Guided questions to gather information
- Quality checks before delivery
- Examples showing what works

### Flexible and Adaptable
- Adjust tone for different audiences
- Modify length based on needs
- Adapt templates for specific use cases
- Add new templates as needed

## Use Cases

### For Managers and Leaders
- Team communications (memos, announcements)
- Executive updates and reports
- Budget and project proposals
- Presentation materials

### For Technical Professionals
- Technical documentation
- How-to guides and runbooks
- Status reports and incident reports
- Technical proposals and analysis

### For Individual Contributors
- Professional emails (outreach, updates, follow-ups)
- Project documentation
- Presentation materials
- Proposals for initiatives

## Writing Standards Philosophy

This skill emphasizes:

**Clarity First**: Direct, understandable language over cleverness
**Specific Over Generic**: Concrete examples and data, not vague statements
**Active Over Passive**: "We completed the project" not "The project was completed"
**Human Over Robotic**: Natural rhythm and voice, not template-sounding
**Actionable**: Clear next steps and outcomes
**Audience-Focused**: Written from reader's perspective

## Quality Guarantees

All content created with this skill:
- Uses active voice throughout (unless passive serves a purpose)
- Includes specific details and examples (not generic statements)
- Follows professional structure and formatting
- Sounds natural and human-written (not AI-generated)
- Is appropriate for the intended audience and context
- Has clear next steps or call-to-action
- Passes quality checks before delivery

## Customization Options

### Tone Adjustment
- **Formal**: C-suite, external stakeholders, official communications
- **Professional Friendly**: Colleagues, team members, warm relationships
- **Direct and Brief**: Busy executives, time-sensitive communications

### Length Options
- **Brief**: Essential information only (75-200 words for emails, 500-800 for reports)
- **Standard**: Complete but concise (100-300 words for emails, 800-1500 for reports)
- **Detailed**: Comprehensive coverage (150-400 words for emails, 1500-3000 for reports)

### Adding New Templates

To add a new content type:
1. Create a new .md file in the appropriate category folder
2. Follow the standard template pattern:
   - Reference writing-standards.md
   - Define specifications
   - Include prompt questions
   - Add quality checks
   - Provide examples
3. Update this README and SKILL.md to list the new template

## Comparison to Instant-Marketing-Mastery

This skill is inspired by Trevor Longino's instant-marketing-mastery framework but adapted for general professional content:

### Similarities
- Three-layer architecture (global standards → context → execution)
- Template-based approach with prompts
- Quality checks built in
- Example-driven learning

### Differences
- **Audience**: Professional business content (not marketing copy)
- **Tone**: Professional and credible (not persuasive sales language)
- **Structure**: Simpler, single-user (not multi-client project structure)
- **Standards**: Enhanced with human-writing elements and anti-AI detection
- **Categories**: Communications, documents, presentations (not marketing campaigns)

## Credits

**Inspired by**:
- Trevor Longino's [instant-marketing-mastery](https://github.com/TrevorLongino/instant-marketing-mastery) - three-layer architecture and template approach

**Writing principles based on**:
- Strunk & White's "Elements of Style" - clarity, brevity, active voice
- George Orwell's writing rules - plain language, avoid jargon, cut unnecessary words
- Modern anti-AI detection research (2025-2026) - human-sounding elements
- Professional business communication best practices

## Contributing

To improve this skill:
1. Add new templates for additional content types
2. Enhance existing templates with more examples
3. Refine writing standards based on feedback
4. Share successful use cases and outcomes

## License

This skill is part of the awesome-agent-skills collection and follows the same license.

---

**Ready to create professional content?** Reference [SKILL.md](SKILL.md) for usage instructions or start asking for what you need.
