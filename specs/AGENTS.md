# Specification Writing Guidelines

This document defines the strict format and structure for writing feature specifications.

## Directory Structure

Specifications MUST be organized as follows:

```
specs/[capability]/spec.md
```

Where `[capability]` is a descriptive name for the feature or capability being specified.

## Purpose

Specifications serve as the source of truth for bidirectional synchronization between specs and code:
- **Spec → Code**: Generate code implementation from specifications
- **Code → Spec**: Generate specifications from existing code

## Specification Format

All `spec.md` files MUST strictly follow this format:

```markdown
# [capability-name] Specification

## Purpose
[Brief description of the capability's purpose]

## Requirements
### Requirement: [Requirement Title]
[Description of what the system SHALL do]

#### Scenario: [Scenario description]
- **WHEN** [triggering condition or action]
- **THEN** [expected system behavior]
- **AND** [additional expected behavior]
- **AND** [additional expected behavior]
- **AND** [additional expected behavior]

#### Scenario: [Another scenario description]
- **WHEN** [triggering condition]
- **THEN** [expected behavior]
- **AND** [additional behavior]
```

## Format Rules

### 1. Title
- Format: `# [capability-name] Specification`
- Use kebab-case for capability names
- Example: `# admin-daily-reports Specification`

### 2. Purpose Section
- **Required**: Yes
- Use for newly created specs or update after archiving changes
- Can contain "TBD" during initial creation
- Example: `TBD - created by archiving change add-admin-daily-reports. Update Purpose after archive.`

### 3. Requirements Section
- **Required**: Yes
- Each requirement MUST start with: `### Requirement: [Title]`
- Follow with description using "SHALL" to indicate mandatory behavior
- Example: `The system SHALL aggregate business metrics from multiple data sources.`

### 4. Scenarios
- **Required**: At least one scenario per requirement
- Format: `#### Scenario: [description]`
- MUST use bullet points with keywords: **WHEN**, **THEN**, **AND**
- **WHEN**: Describes the triggering condition or action
- **THEN**: Describes the primary expected behavior
- **AND**: Describes additional expected behaviors (use multiple as needed)

## Complete Example

```markdown
# admin-daily-reports Specification

## Purpose
TBD - created by archiving change add-admin-daily-reports. Update Purpose after archive.

## Requirements
### Requirement: Daily Report Data Aggregation
The system SHALL aggregate business metrics from multiple data sources into a unified daily report.

#### Scenario: Aggregate subscription metrics for report period
- **WHEN** generating daily report for date range
- **THEN** system queries subscription_plan_with_stats view
- **AND** counts new subscriptions created in period
- **AND** counts active subscriptions as of end of period
- **AND** counts cancelled subscriptions in period
- **AND** calculates total revenue from subscriptions
- **AND** groups revenue by plan (top 5 plans by revenue)

#### Scenario: Handle missing data gracefully
- **WHEN** data source is unavailable
- **THEN** system logs error with data source details
- **AND** continues processing other available data sources
- **AND** marks report as partial in output

### Requirement: Report Generation
The system SHALL generate reports in multiple formats.

#### Scenario: Generate JSON report
- **WHEN** JSON format is requested
- **THEN** system outputs report as valid JSON
- **AND** includes metadata section with generation timestamp
- **AND** includes metrics section with aggregated data
```

## Key Points

1. **Strict Compliance**: ALL specifications MUST follow this exact format
2. **Mandatory Keywords**: Use "SHALL" for requirements, "WHEN/THEN/AND" for scenarios
3. **Completeness**: Every requirement needs at least one scenario
4. **Clarity**: Scenarios should be specific and testable
5. **Sync Ready**: Format enables automated spec-code synchronization

## Creating New Specifications

1. Create directory: `specs/[capability-name]/`
2. Create file: `specs/[capability-name]/spec.md`
3. Follow the format template exactly
4. Start with "TBD" in Purpose if needed
5. Define all requirements with scenarios
6. Ensure scenarios are complete and testable
