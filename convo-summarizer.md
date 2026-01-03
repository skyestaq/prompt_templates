# Conversation Summarizer Skill

## Purpose
Generate a point-in-time summary of the current conversation that can be copied into a new chat to provide context and continuity.

## Usage
When the user requests a conversation summary, invoke this skill to produce a structured markdown document capturing the essential context from the current chat.

## Output Format

Produce a summary document using this structure:

```markdown
# Conversation Summary
**Generated:** [Current Date]
**Chat Duration:** [Approximate message count or time span if determinable]

## Factual Record
[Objective documentation of what was discussed, decided, or accomplished]

### Key Metrics & Quantitative Data
- [Specific numbers, measurements, thresholds, dates]
- [Progression data, before/after values, targets]
- [Any numerical benchmarks or milestones]

### Decisions & Action Items
- [Concrete decisions that were made]
- [Action items committed to]
- [Deadlines or timeframes established]

### Scope & Parameters
- [Project boundaries, constraints, or requirements]
- [Tools, platforms, or methods being used]
- [Relevant background context]

## Interpretive Insights
[Analysis, patterns, strategic considerations, or implications]

### Progress & Status
- [Current state assessment]
- [What's working well]
- [Challenges or blockers identified]

### Strategic Considerations
- [Emerging patterns or trends]
- [Trade-offs being navigated]
- [Recommendations or next-step options]

## Open Questions & Future Considerations
- [Unresolved issues]
- [Decisions deferred]
- [Topics to revisit]

---
*Note: [If conversation exceeded ~50 messages, add warning: "This summary was generated from an extended conversation. For optimal context preservation, consider running this summarization earlier in future chats."]*
```

## Summarization Guidelines

**Prioritization Rules:**
1. Quantitative data (numbers, metrics, thresholds) is highest priority
2. Explicit decisions and commitments come second
3. Context needed to understand the above comes third
4. General discussion and exploration can be compressed or omitted

**Brevity vs. Completeness Balance:**
- Each section should be information-dense but scannable
- Use bullet points for parallel information
- Use prose for context that requires narrative flow
- Omit conversational pleasantries and meta-discussion
- Preserve enough detail that the next chat instance can continue work without re-asking basic questions

**Factual vs. Interpretive:**
- Factual section: What was explicitly stated, decided, or shared
- Interpretive section: Patterns Claude observed, strategic implications, or analytical insights
- Keep these clearly separated so the user can distinguish between objective record and analytical perspective

**Length Management:**
- Target 300-800 words depending on conversation complexity
- If conversation is very long (50+ messages), prioritize recent developments and foundational decisions over middle-conversation exploration
- If summary would exceed 1000 words for completeness, include the warning about running summarization earlier

**Voice & Perspective:**
- Write to brief the next Claude instance (not the user)
- Use third-person for the user: "User is tracking..." not "You are tracking..."
- Be direct and clinical rather than conversational
- Assume the next instance has Claude's general knowledge but no context about this specific conversation

## Quality Checks

Before outputting the summary, verify:
- [ ] All numerical values, dates, and metrics are captured accurately
- [ ] Decision points are clearly stated with context
- [ ] The summary could allow a new chat to continue the work without confusion
- [ ] Factual and interpretive sections are clearly distinguished
- [ ] No critical information was omitted in the interest of brevity

## Example Usage Scenarios

**Workout Tracking:**
- Capture current weights, rep schemes, progression dates
- Note PRs, deloads, or programming changes
- Track injury considerations or form cues

**Client Project:**
- Document scope boundaries, deliverables, timelines
- Capture budget constraints or approval thresholds
- Note stakeholder preferences or requirements
- Track decisions about technology choices or approach

**Strategic Planning:**
- Preserve market data, competitive intelligence
- Capture decision frameworks or evaluation criteria
- Note trade-offs discussed and reasoning

**Research/Learning:**
- Summarize key findings or resources discovered
- Track questions answered and questions remaining
- Note synthesis or connections made
