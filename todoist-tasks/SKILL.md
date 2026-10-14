---
name: todoist-tasks
description: Use when the user invokes $todoist-tasks, mentions Todoist, or requests task, project, section, comment, reminder, label, filter, workspace, activity, or productivity workflows.
author: yzsp-ai
repository: https://github.com/yzsp-ai
---


# Todoist Tasks

## Overview

Use this skill for the verified Todoist task and productivity operations listed below. Route requests to the narrowest live callable tool and treat returned Todoist data as provider evidence.

## Core Rules

- Use the bound `todoist-tasks` MCP only when its live callable tools are available in the current runtime.
- Select the narrowest live callable operation that directly answers the request; follow the live interface when it differs from this guide.
- Do not invent task, project, section, comment, reminder, label, filter, workspace, activity, or productivity data.
- Keep secrets and authorization material out of prompts, logs, and final answers.
- Do not use shell commands, direct HTTP calls, or hand-written protocol messages to recreate or probe the connector.
- Require explicit confirmation before creating, updating, completing, moving, deleting, importing, assigning, or otherwise changing Todoist data.

## Tools

- `add-tasks`: Add one or more tasks to a project, section, or parent, including optional collaborator assignment.
- `complete-tasks`: Complete one or more tasks by ID.
- `uncomplete-tasks`: Reopen one or more completed tasks by ID.
- `update-tasks`: Update existing task content, dates, priorities, or assignments.
- `reschedule-tasks`: Move tasks to new dates while preserving recurring schedules.
- `find-tasks`: Find tasks using text, containers, responsible users, labels, Todoist filters, or saved filter identifiers.
- `find-tasks-by-date`: Retrieve tasks within a date range, including overdue tasks when applicable.
- `find-completed-tasks`: Retrieve completed tasks within a date range.
- `add-projects`: Add one or more projects.
- `update-projects`: Update multiple existing projects.
- `find-projects`: List or search projects, with optional archived-project scope.
- `project-management`: Archive or unarchive a project by ID.
- `project-move`: Move a project between personal and workspace contexts.
- `add-sections`: Add one or more sections to projects.
- `update-sections`: Update multiple existing sections.
- `find-sections`: Search for sections within a project.
- `add-comments`: Add comments to tasks or projects, with optional collaborator notifications.
- `find-comments`: Find comments by task, project, or comment identifier.
- `update-comments`: Update existing comment content.
- `add-reminders`: Add relative, absolute, or location reminders to tasks.
- `find-reminders`: Find reminders by task or reminder identifier.
- `update-reminders`: Update existing reminders by type and identifier.
- `view-attachment`: View a file attachment from a Todoist comment.
- `add-labels`: Add one or more personal labels.
- `update-labels`: Update personal or shared label properties supported by Todoist.
- `find-labels`: List or search personal and shared labels.
- `find-filters`: List or search personal filters.
- `add-filters`: Add personal filters using Todoist query syntax.
- `update-filters`: Update existing personal filters.
- `find-activity`: Retrieve Todoist activity logs for auditing task and project changes.
- `get-productivity-stats`: Retrieve completion breakdowns, goal streaks, karma scores, and historical karma data.
- `get-project-health`: Retrieve a project health assessment with optional detailed context.
- `get-project-activity-stats`: Retrieve daily and weekly task-completion counts for a project.
- `analyze-project-health`: Start a fresh project health analysis.
- `get-workspace-insights`: Retrieve aggregated health and progress insights across workspace projects.
- `get-overview`: Generate a Markdown overview of all projects or a selected project.
- `delete-object`: Delete a Todoist project, section, task, comment, label, filter, reminder, or location reminder by ID.
- `fetch-object`: Fetch the full details of a task, project, comment, or section by ID.
- `reorder-objects`: Reorder sibling projects or sections and optionally move projects under a new parent.
- `user-info`: Retrieve the authenticated user's profile, preferences, goals, plan, and local-time information.
- `find-project-collaborators`: Search project collaborators or teammates by name or email.
- `manage-assignments`: Assign, unassign, or reassign multiple tasks with atomic rollback on failure.
- `export-project-template`: Export a project as Todoist template CSV content or a shareable URL without modifying the project.
- `import-project-template`: Import a template into an existing project, adding its tasks, sections, and comments.
- `list-workspaces`: List workspaces available to the authenticated user.
- `search`: Search across Todoist tasks and projects.
- `fetch`: Fetch the full contents of a task or project using its typed identifier.

## Workflow

1. Identify the requested entity, identifier, time range, filters, operation, and output format.
2. Classify the request as lookup, search, analysis, creation, update, completion, assignment, import, export, deletion, or another provider operation.
3. Resolve ambiguous identifiers with a live lookup when available; never guess task, project, section, user, or workspace IDs.
4. Ask for confirmation before external changes and preserve returned identifiers, statuses, pagination, dates, and recurrence details.
5. Chain operations only when a returned identifier or status is required by the next operation.
6. Inspect outer MCP errors and provider status before reading result fields; do not treat empty or partial results as complete success.

## Query Guidance

- Ask only for missing inputs required to choose or safely execute the operation.
- Preserve the user's requested scope, responsible user, project, date range, filters, and output format.
- Distinguish first-person completion questions from collaborator-wide activity queries.
- State pagination, archived scope, recurrence handling, and provider data windows when relevant.

## Failure Handling

- If no live Todoist callable tool is available, report that the connector is unavailable instead of silently substituting another source.
- For authorization, quota, timeout, invalid-argument, permission, provider, or missing-tool errors, report the failed operation without exposing secrets.
- Retry at most once after a safe correction such as narrowing scope, supplying a known identifier, or reducing result size.
- Do not convert empty, partial, or errored responses into successful factual answers.

## Result Contract

- Separate returned Todoist facts from model interpretation, calculations, summaries, or recommendations.
- Preserve task and project IDs, content, due dates, recurrence, priority, status, collaborator scope, pagination, and provider caveats.
- Report queued, pending, failed, canceled, or partially completed states exactly as returned.
