# Claude AI Prompt Configuration

This file defines prompt settings and guidelines for using Claude AI.

## Updating Specifications

When updating prompt specifications, always check **[specs/AGENTS.md](specs/AGENTS.md)**.
It contains guidelines on how to write specifications and detailed documentation.

---

## Basic Settings

### Tone & Style
- [Describe appropriate tone and style for the project]
- Example: Professional and technical, prioritizing accuracy

### Context
- [Project background and purpose]
- [Technology stack in use]
- [Important constraints]

---

## Task-Specific Prompts

### Code Review

```
[Code review prompt template]

Example:
Review the following code for:
- Security issues
- Performance improvements
- Code readability
```

### Code Generation

```
[Code generation prompt template]

Example:
Generate code based on these requirements:
- Requirement 1
- Requirement 2
```

### Documentation

```
[Documentation prompt template]

Example:
Create documentation covering:
- Purpose
- Usage
- Considerations
```

---

## Prompt Engineering Guidelines

1. **Specificity**: Avoid ambiguity, provide concrete requirements
2. **Context**: Provide necessary background information
3. **Constraints**: Specify clear limitations
4. **Examples**: Show expected output examples
5. **Incremental**: Break complex tasks into steps

## Quality Standards

Quality criteria for generated content:

- **Accuracy**: Technically correct
- **Completeness**: Contains all necessary information
- **Consistency**: Adheres to project conventions
- **Readability**: Well-structured and understandable

## Best Practices

### Do's ✓
- Give clear and specific instructions
- Provide necessary context
- Specify expected output format
- Use incremental approach

### Don'ts ✗
- Avoid vague instructions
- Avoid excessively long prompts
- Don't request complex tasks without context

---

## Detailed Specifications

For detailed prompt specifications:

1. Refer to [specs/AGENTS.md](specs/AGENTS.md) guidelines
2. Create detailed specs in specs/ directory
3. Link appropriately from this file

## Change History

| Date | Changes | Author |
|------|---------|--------|
| YYYY-MM-DD | Initial version | [Name] |

---

## Reference Links

- [Claude AI Documentation](https://docs.anthropic.com/claude/docs)
- [Prompt Engineering Guide](https://www.promptingguide.ai/)
- [Project AGENTS.md](AGENTS.md)
