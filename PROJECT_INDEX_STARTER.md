# PROJECT_INDEX.md - Master File Registry
## Universal AI Agent Development Tracker

> **AI AGENT**: This is your source of truth. Read this FIRST, update it ALWAYS.

## 🤖 How to Use This Index

### First Time Setup (Agent Instructions)
1. **Replace all placeholders** marked with `[PLACEHOLDER]`
2. **Update project details** in the Overview section
3. **Define your phases** based on logical build segments
4. **List all planned files** in the File Registry
5. **Set initial status** to "Phase 1 - Not Started"
6. **Save this file** and begin development

### During Development
- Update file status: ⏳ Pending → 🚧 In Progress → ✅ Complete
- Mark completed phases with checkboxes
- Document discovered dependencies
- Note any deviations from plan
- Update "Last Modified" timestamps

### Before Switching Agents/Sessions
- Ensure "Current Status" is accurate
- Update "Next Priority" with specific task
- Check all status indicators match reality
- Verify DEVELOPMENT_LOG.md is current

---

## 📋 Project Overview

**Project Name**: [PLACEHOLDER: Your Project Name]  
**Description**: [PLACEHOLDER: 1-2 sentence description]  
**Tech Stack**: [PLACEHOLDER: e.g., Next.js, Node.js, PostgreSQL]  
**Target Users**: [PLACEHOLDER: Who will use this]  
**Key Features**: [PLACEHOLDER: 3-5 main features]  

---

## 🚦 Current Status

```yaml
Current Phase: [PLACEHOLDER: e.g., "Phase 1 - Foundation"]
Status: [PLACEHOLDER: Not Started | In Progress | Complete]
Completion: [PLACEHOLDER: e.g., "0%" or "3/10 tasks"]
Last Updated: [PLACEHOLDER: Date/Time]
Active Agent: [PLACEHOLDER: Agent name/model]
Session Started: [PLACEHOLDER: Time]
Next Priority: [PLACEHOLDER: Specific next task]
Blocking Issues: [PLACEHOLDER: None | Describe issue]
```

---

## 🎯 Development Phases

> **Agent**: Define phases that make sense for your project. Each phase should be independently testable.

### Phase Overview
- [ ] Phase 1: [PLACEHOLDER: e.g., "Foundation & Setup"]
- [ ] Phase 2: [PLACEHOLDER: e.g., "Authentication"]
- [ ] Phase 3: [PLACEHOLDER: e.g., "Core Data Models"]
- [ ] Phase 4: [PLACEHOLDER: e.g., "Business Logic"]
- [ ] Phase 5: [PLACEHOLDER: e.g., "API Layer"]
- [ ] Phase 6: [PLACEHOLDER: e.g., "Frontend"]
- [ ] Phase 7: [PLACEHOLDER: e.g., "Testing & Polish"]

### Phase Details

#### Phase 1: [PLACEHOLDER: Phase Name]
**Goal**: [PLACEHOLDER: What this phase accomplishes]  
**Success Criteria**: [PLACEHOLDER: How to know it's complete]  
**Dependencies**: [PLACEHOLDER: What must exist first]  
**Estimated Time**: [PLACEHOLDER: Hours/Days]  

[PLACEHOLDER: Repeat for each phase]

---

## 📁 File Registry

> **Agent**: Track EVERY file you plan to create or modify. Update status as you work.

### Configuration Files (Root)
| File | Purpose | Status | Dependencies | Notes |
|------|---------|--------|--------------|-------|
| `package.json` | Project dependencies | ⏳ Pending | - | [PLACEHOLDER] |
| `.env.template` | Environment template | ⏳ Pending | - | [PLACEHOLDER] |
| `[PLACEHOLDER]` | [PLACEHOLDER] | ⏳ Pending | - | - |

### Source Files (/src)

#### [PLACEHOLDER: Module Name] Module
| File | Purpose | Status | Dependencies | Notes |
|------|---------|--------|--------------|-------|
| `/src/[path]` | [Purpose] | ⏳ Pending | [Dependencies] | [Notes] |

[PLACEHOLDER: Repeat for each module]

### Test Files (/tests)
| File | Purpose | Status | Coverage Target | Notes |
|------|---------|--------|----------------|-------|
| `/tests/[path]` | [Purpose] | ⏳ Pending | [X%] | [Notes] |

---

## 🔄 Dependency Map

> **Agent**: Document how modules connect. Update when you discover new dependencies.

```
[PLACEHOLDER: Visual representation of module dependencies]
Example:
  index.ts
  ├── config/* (standalone)
  ├── auth/* → config
  ├── database/* → config
  └── api/* → auth, database
```

### External Dependencies
```json
{
  "production": [
    "[PLACEHOLDER: package-name]"
  ],
  "development": [
    "[PLACEHOLDER: dev-package]"
  ]
}
```

### Internal Dependencies
- Module A requires: [PLACEHOLDER]
- Module B requires: [PLACEHOLDER]

---

## 🔌 API/Interface Registry

> **Agent**: List all public APIs, routes, or interfaces that other modules will use.

### REST Endpoints
| Method | Path | Purpose | Status | Auth Required |
|--------|------|---------|--------|---------------|
| GET | `/api/[path]` | [Purpose] | ⏳ Pending | Yes/No |
| POST | `/api/[path]` | [Purpose] | ⏳ Pending | Yes/No |

### Key Interfaces/Types
| Name | Location | Purpose | Status |
|------|----------|---------|--------|
| `[InterfaceName]` | `/src/types/[file]` | [Purpose] | ⏳ Pending |

---

## 🧪 Testing Strategy

### Coverage Goals
- Unit Tests: [PLACEHOLDER: e.g., "80%"]
- Integration Tests: [PLACEHOLDER: e.g., "Critical paths"]
- E2E Tests: [PLACEHOLDER: e.g., "User workflows"]

### Test Commands
```bash
# [PLACEHOLDER: Add your test commands]
npm test          # Run all tests
npm test:unit     # Unit tests only
npm test:e2e      # End-to-end tests
```

---

## 🚀 Quick Start Commands

> **Agent**: Keep these updated so any agent can start immediately.

```bash
# Initial Setup
[PLACEHOLDER: git clone command]
[PLACEHOLDER: install command]
[PLACEHOLDER: environment setup]

# Development
[PLACEHOLDER: dev server command]
[PLACEHOLDER: build command]

# Testing
[PLACEHOLDER: test command]

# Deployment
[PLACEHOLDER: deploy command]
```

---

## 📝 Agent Handoff Checklist

Before ending your session, verify:
- [ ] All modified files are saved
- [ ] Status indicators are accurate
- [ ] DEVELOPMENT_LOG.md is updated
- [ ] Tests pass for completed work
- [ ] Next priority is clear
- [ ] Any blocking issues are documented
- [ ] Environment setup is documented
- [ ] Quick start commands work

---

## ⚠️ Known Issues & Workarounds

> **Agent**: Document any issues and their temporary solutions.

| Issue | Workaround | Permanent Fix Needed |
|-------|------------|---------------------|
| [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

---

## 📚 Project Documentation

| Document | Purpose | Location | Status |
|----------|---------|----------|--------|
| README.md | User documentation | `/README.md` | ⏳ Pending |
| API.md | API documentation | `/docs/API.md` | ⏳ Pending |
| [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | ⏳ Pending |

---

## 🎯 Decision Log

> **Agent**: Document important architectural decisions.

| Date | Decision | Reasoning | Impact |
|------|----------|-----------|--------|
| [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

---

## 📊 Progress Metrics

**Overall Completion**: [PLACEHOLDER: 0%]  
**Files Created**: [PLACEHOLDER: 0/50]  
**Tests Passing**: [PLACEHOLDER: 0/0]  
**Current Velocity**: [PLACEHOLDER: files/hour]  
**Estimated Completion**: [PLACEHOLDER: date/time]  

---

## 🔄 Last 5 Actions

> **Agent**: Quick reference of recent work. Update as you work.

1. [PLACEHOLDER: Most recent action]
2. [PLACEHOLDER: Previous action]
3. [PLACEHOLDER: Earlier action]
4. [PLACEHOLDER: Earlier action]
5. [PLACEHOLDER: Earlier action]

---

## 💡 Agent Notes

> **Agent**: Leave helpful notes for the next session/agent.

**Environment Quirks**: [PLACEHOLDER]  
**Useful Resources**: [PLACEHOLDER]  
**Key Decisions Made**: [PLACEHOLDER]  
**Recommended Next Steps**: [PLACEHOLDER]  

---

**Index Version**: 1.0.0  
**Template Source**: Universal AI Agent Development Tracker  
**Last Structure Update**: [PLACEHOLDER: Date]  

---

### 🤖 Remember: This index is your map. Keep it accurate, and you'll never get lost.