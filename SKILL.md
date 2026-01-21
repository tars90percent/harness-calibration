---
name: harness-calibration
description: Teaches models how to calibrate when instantiated in a new harness or environment. Use this skill when entering an unfamiliar context, when tools or capabilities are unclear, or when adapting to a new interface, workflow, or operational context.
license: MIT
metadata:
  author: minimax
  version: "1.0.0"
---

# Harness Calibration

A harness is any environment where a model operates: coding agents, chat interfaces, evaluation frameworks, training pipelines, API integrations, or custom toolchains. Each harness has different capabilities, constraints, and expectations. This skill provides a systematic approach to calibrating when dropped into a new or unfamiliar harness.

## Why Calibration Matters

Models that fail to calibrate make assumptions that don't hold:
- Attempting to use tools that don't exist
- Producing output formats the harness can't parse
- Missing capabilities that are available
- Violating implicit constraints
- Misreading the communication style expected

Calibration is the process of rapidly understanding your operational context so you can be maximally effective.

## The Calibration Process

### Phase 1: Environment Discovery

**Identify the harness type:**
- Is this a coding agent (file access, shell commands)?
- Is this a conversational interface (text-only)?
- Is this an evaluation harness (structured inputs, expected outputs)?
- Is this a multi-modal context (images, audio, other modalities)?
- Is this a tool-use context (function calling, MCP servers)?

**Discover available capabilities:**
- What tools are available? List them explicitly if possible.
- What file system access exists, if any?
- Can you execute code? In what languages/environments?
- Can you access the internet or external services?
- What input/output modalities are supported?

**Understand constraints:**
- Are there token/length limits on responses?
- Are there rate limits or quotas?
- Are certain topics or actions restricted?
- Is there a specific output format required?
- Are there safety or policy constraints to observe?

### Phase 2: Context Gathering

**Read the system prompt carefully:**
- What role are you asked to play?
- What specific instructions are given?
- What examples are provided?
- What tone or style is expected?

**Examine any provided context:**
- Are there documents, codebases, or data to reference?
- Is there conversation history to learn from?
- Are there examples of desired behavior?

**Note what's NOT said:**
- Implicit expectations often matter more than explicit ones
- Absence of restrictions doesn't mean anything goes
- Consider what a reasonable operator would expect

### Phase 3: Capability Testing

When uncertain about capabilities, test them systematically:

**For tool-based harnesses:**
1. If tools are listed, review their signatures and descriptions
2. Start with low-risk, reversible operations
3. Observe error messages - they reveal constraints
4. Build a mental model of what works and what doesn't

**For conversational harnesses:**
1. Note how your responses are being used
2. Adjust verbosity based on feedback
3. Match the formality level of the user

**For evaluation harnesses:**
1. Pay close attention to the expected output format
2. Look for examples of correct responses
3. When in doubt, be precise rather than verbose

### Phase 4: Adaptation

Once you understand the harness, adapt your behavior:

**Output formatting:**
- Match the expected structure exactly
- If JSON is expected, output valid JSON
- If markdown is expected, use proper markdown
- If code is expected, output executable code

**Communication style:**
- Technical harnesses expect precision
- User-facing harnesses may expect warmth
- Evaluation harnesses expect minimal commentary

**Error handling:**
- Understand how errors are communicated
- Know when to retry vs. report failure
- Preserve useful error information

## Calibration Checklist

Run through this checklist when entering a new harness:

- [ ] What type of harness is this?
- [ ] What tools/capabilities are available?
- [ ] What are the explicit constraints?
- [ ] What are the implicit expectations?
- [ ] What output format is expected?
- [ ] What communication style is appropriate?
- [ ] Have I tested my assumptions?
- [ ] Am I adapting based on feedback?

## Common Harness Patterns

### Coding Agents (Claude Code, Cursor, Windsurf, etc.)
- File system access via dedicated tools
- Shell command execution
- Iterative workflow with user feedback
- Emphasis on working code over explanation
- Often have permission systems for sensitive operations

### Chat Interfaces (ChatGPT, Claude.ai, etc.)
- Text-primary interaction
- May support image/file uploads
- Conversational, back-and-forth flow
- Balance helpfulness with appropriate caution
- Users expect natural language responses

### Evaluation Harnesses (lm-eval, Inspect, custom evals)
- Structured input format (often JSON or specific templates)
- Strict output format requirements
- Minimal or no conversational elements
- Correctness over style
- May run many instances in parallel

### API Integrations
- Programmatic input/output
- Often expects structured data (JSON)
- Error handling is critical
- May have strict schema requirements
- Stateless between calls unless explicitly managed

### Training/Fine-tuning Pipelines
- Examples are being used to shape future behavior
- Consistency matters more than individual brilliance
- Follow the demonstrated patterns closely
- Quality of reasoning often matters as much as final answer

## Anti-Patterns to Avoid

**Over-assuming capabilities:**
Don't assume you can browse the web, execute code, or access files unless you've confirmed these capabilities exist.

**Ignoring the system prompt:**
The system prompt is your primary source of truth. Read it carefully, follow it precisely.

**Fighting the harness:**
If the harness expects a certain format, produce that format. Don't argue for a different approach.

**Failing to adapt:**
If something isn't working, change your approach. Repeating failed strategies wastes resources.

**Excessive meta-commentary:**
Most harnesses want you to do the task, not talk about doing the task. Calibrate how much meta-discussion is appropriate.

## Continuous Calibration

Calibration isn't a one-time event. Throughout operation:

1. **Monitor feedback** - User corrections, error messages, and explicit guidance all inform calibration
2. **Update your model** - Revise assumptions when evidence contradicts them
3. **Stay adaptive** - The harness may change mid-session (new tools, changed instructions)
4. **Fail gracefully** - When uncertain, acknowledge uncertainty rather than confabulating

## Summary

Effective harness calibration follows a simple loop:

1. **Observe** - What environment am I in? What's available?
2. **Hypothesize** - What does this harness expect from me?
3. **Test** - Try things, especially when uncertain
4. **Adapt** - Adjust behavior based on results
5. **Repeat** - Stay calibrated as context evolves

The best-calibrated models are those that quickly understand their operational context and adapt their behavior to be maximally effective within it.
