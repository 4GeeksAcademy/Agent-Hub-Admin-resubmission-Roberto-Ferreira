# AgentHub Admin Panel - Project Specification

## 1. Product Description

AgentHub is an internal platform for managing AI agents and their skill contracts. The Admin Panel is a frontend-only operational dashboard used by internal administrators to monitor platform activity, manage users, configure agents, inspect contracts, and resolve runtime issues.

### Primary Admin User

- Platform Operations Admin
- Responsible for user lifecycle management, agent configuration checks, contract validation, and incident triage.

## 2. Tech Stack and Constraints

### Stack

- HTML5 (semantic structure)
- Tailwind CSS via CDN only
- Vanilla JavaScript (no frameworks)

### Hard Constraints

- No backend/API integration (hardcoded data only)
- No React, Vue, Angular, or other frameworks
- No jQuery
- No external CSS files
- No inline `style` attributes
- Interactivity must be implemented with vanilla JavaScript only

## 3. Global Layout and Navigation

### Sidebar

- Persistent left sidebar visible across all sections.
- Sidebar includes six navigation items in this exact order:
  1. Dashboard
  2. User Management
  3. Agent Management
  4. Skills
  5. Agent Contracts
  6. Error Log
- Active section link is visually highlighted.

### Top Bar

- Contains page title and section context text.
- Includes a dark/light mode toggle.
- Theme changes apply to the entire panel.

## 4. Section Specifications

### 4.1 Dashboard

1. Display exactly 4 metric summary cards (e.g., total users, active agents, active contracts, open errors).
2. Include a weekly activity placeholder panel (visual placeholder only, no live chart library required).
3. Show short status context text indicating operational health.
4. Preserve readability in both light and dark themes.

### 4.2 User Management

1. Render a table with at least 5 hardcoded users.
2. Each row must provide an action dropdown menu.
3. Dropdown options include View detail and at least one secondary action.
4. View detail opens a modal with user information.
5. Modal closes via explicit close button and backdrop click.

### 4.3 Agent Management

1. Render at least 4 hardcoded agents with status metadata.
2. Each agent includes a collapsed-by-default skills list.
3. Skills list expands/collapses with visible smooth transition.
4. Each row includes actions with Configure option.
5. Configure action opens a modal with editable prompt textarea.

### 4.4 Skills

1. Show at least 4 skills with name, description, and enabled-agent count.
2. Include a short explanatory block describing what a skill is.
3. Each skill row has an action dropdown.
4. At least one action opens a detail modal.

### 4.5 Agent Contracts

1. Show at least 4 contracts mapped to existing agents/skills.
2. Contract rows include status, total cost, and updated date.
3. View detail opens a modal with itemized skill pricing breakdown.
4. Contract data must be consistent with Skills and Agent Management naming.

### 4.6 Error Log

1. Show at least 6 hardcoded error log entries.
2. Each entry includes timestamp, source, severity/type, and summary.
3. Error type badge is color-coded by category/severity.
4. Row actions include View detail and Mark as resolved.
5. View detail opens a modal and supports close button + backdrop close.

## 5. Reusable Component Inventory

1. Sidebar navigation item
2. Top bar with theme toggle
3. Metric card
4. Data table row
5. Status badge
6. Error severity badge
7. Row action dropdown menu
8. Modal shell (header/body/footer)
9. Modal backdrop overlay
10. Collapsible skills container
11. Section panel container

## 6. Interaction Specifications

### Theme Toggle

- Toggle switches between light and dark modes for the whole application.
- Theme state persists while navigating between sections.

### Section Switching

- Clicking a sidebar item shows the corresponding section content and hides others.
- Active navigation state updates immediately.

### Dropdown Behavior

- Clicking row action button opens that row dropdown.
- Opening a dropdown closes other open dropdowns.
- Clicking outside any dropdown closes all dropdowns.

### Modal Behavior

- View detail actions open context-specific modal content.
- Configure action in Agent Management opens prompt-edit modal.
- Modals close through close button and backdrop click.

### Collapsible Agent Skills

- Agent skills are collapsed by default.
- Clicking expand control toggles collapsed state.
- Transition is visible and smooth for expand/collapse.

## 7. Data Consistency Rules

1. Agent names used in contracts must exist in Agent Management section.
2. Skill names used in contract breakdown must exist in Skills section.
3. Dashboard metrics must reflect counts represented in section tables.
4. Error entries should reference valid subsystem labels used elsewhere.

## 8. Numbered Acceptance Criteria

1. SPECS.md exists at project root and was committed before UI implementation commits.
2. Application uses only HTML, Tailwind CDN, and vanilla JavaScript.
3. No external stylesheet files and no inline style attributes are used.
4. Sidebar shows all six required sections and each is accessible.
5. Dashboard contains exactly 4 metric cards and one weekly activity placeholder.
6. User Management table contains at least 5 users and row action dropdowns.
7. User detail modal opens and closes via close button and backdrop click.
8. Agent Management lists at least 4 agents with collapsed-by-default skills.
9. Agent skills expand/collapse with visible transition.
10. Configure modal includes editable prompt textarea.
11. Skills section lists at least 4 skills with name, description, and enabled count.
12. Skills section includes a short explainer about skill purpose.
13. Agent Contracts lists at least 4 contracts.
14. Contract detail modal shows itemized skill pricing.
15. Error Log contains at least 6 entries with color-coded type/severity badges.
16. Error row actions include View detail and Mark as resolved.
17. Dropdown menus close on outside click.
18. Dark/light mode toggles whole panel and persists while navigating sections.
19. Data naming is consistent across Users, Agents, Skills, Contracts, and Error Log.
20. Layout remains usable on desktop and tablet viewport sizes.
21. Semantic HTML landmarks and table semantics are used appropriately.
