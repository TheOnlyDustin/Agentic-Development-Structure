# PROJECT_INDEX_STARTER.md
## Self-Deploying Project Index System for AI-Assisted Development

---

# 🚀 PART 1: DEPLOYMENT INSTRUCTIONS

> **AI AGENT**: Follow these steps exactly to deploy the indexing system for this project.

## Step 1: Create INDEX.md
Copy the template from Part 2 below into a new file called `INDEX.md` in the project root.

## Step 2: Analyze the Codebase
Review these sources to gather project information:
- **README.md** - Project overview and setup instructions
- **Steering documents** - Architecture decisions, design docs
- **DOCS folder** - Any existing documentation
- **Root directory files** - Often contains unfiled notes, TODO lists, or developer documentation
- **Configuration files** - package.json, .env files, docker-compose.yml, etc.
- **Source code structure** - Examine /src, /lib, /app directories

## Step 3: Backfill INDEX.md
Using the information gathered, complete the INDEX.md file by:
1. **Replace ALL placeholders** marked with `[PLACEHOLDER]`
2. **Map the complete file structure** - every file gets an entry
3. **Document discovered dependencies** from package files
4. **Identify logical development phases** based on code organization
5. **Note any technical debt** found in comments or structure
6. **List all APIs/routes** discovered in the codebase
7. **Document environment variables** found in code or config files

## Step 4: Organize Documentation
1. **Create DOCS folder** if it doesn't exist:
   ```bash
   mkdir -p DOCS
   ```

2. **Move this file** (PROJECT_INDEX_STARTER.md) to DOCS folder:
   ```bash
   mv PROJECT_INDEX_STARTER.md DOCS/
   ```

3. **Move any loose documentation** from root to DOCS:
   - Any .md files (except README.md and INDEX.md)
   - Any .txt files with documentation
   - Any steering documents or notes
   ```bash
   # Example moves (adjust based on what you find):
   mv NOTES.md DOCS/ 2>/dev/null || true
   mv TODO.md DOCS/ 2>/dev/null || true
   mv ARCHITECTURE.md DOCS/ 2>/dev/null || true
   ```

## Step 5: Update INDEX.md References
Update any document paths in INDEX.md to reflect the new DOCS/ location:
- Change references from `/NOTES.md` to `/DOCS/NOTES.md`
- Update any links in the Documentation section
- Verify all file paths are accurate

## Step 6: Create Agent Reminder
Add this notice at the top of INDEX.md after deployment:

```markdown
<!-- 
🤖 AI AGENT REMINDER:
After completing any development task, please update this INDEX.md by:
1. Running: "Please add the previous developments to INDEX.md, following the best practices set forth in the indexing instructions"
2. Updating file statuses (⏳ → 🚧 → ✅)
3. Recording decisions in the Decision Log
4. Updating the Current Status section
-->
```

## Step 7: Verification Checklist
Confirm these items before considering deployment complete:
- [ ] INDEX.md exists in project root
- [ ] All placeholders in INDEX.md are replaced with actual data
- [ ] Every project file is listed in the File Registry
- [ ] DOCS folder exists and contains documentation
- [ ] PROJECT_INDEX_STARTER.md is moved to DOCS/
- [ ] All root-level docs (except README.md and INDEX.md) are in DOCS/
- [ ] File paths in INDEX.md are updated to reflect moves
- [ ] Agent reminder is added to top of INDEX.md
- [ ] Current Status section shows accurate project state

## 📝 Post-Deployment Usage

### For Every Development Session:
1. **Start** by reading INDEX.md Current Status
2. **During** development, note changes mentally or in comments
3. **After** completing tasks, run:
   > "Please add the previous developments to INDEX.md, following the best practices set forth in the indexing instructions"
4. **Verify** all changes are reflected in INDEX.md

### Maintenance Commands:
```bash
# Check INDEX.md is current
git diff INDEX.md

# Find files not in INDEX.md
find . -type f -name "*.js" -o -name "*.ts" -o -name "*.jsx" | while read f; do grep -q "$f" INDEX.md || echo "Missing: $f"; done

# List recently modified files to update
find . -type f -mtime -1 ! -path "./.git/*"
```

---

# 📋 PART 2: INDEX.md TEMPLATE

> **Copy everything below this line into INDEX.md**

---

# INDEX.md - Master Project Registry
## AI-Assisted Development Tracker

<!-- 
🤖 AI AGENT REMINDER:
After completing any development task, please update this INDEX.md by:
1. Running: "Please add the previous developments to INDEX.md, following the best practices set forth in the indexing instructions"
2. Updating file statuses (⏳ → 🚧 → ✅)
3. Recording decisions in the Decision Log
4. Updating the Current Status section
-->

## 📋 Project Overview

**Project Name**: [PLACEHOLDER: Your Project Name]  
**Repository**: [PLACEHOLDER: GitHub/GitLab URL]  
**Description**: [PLACEHOLDER: 1-2 sentence description]  
**Tech Stack**: [PLACEHOLDER: e.g., Next.js, Node.js, PostgreSQL]  
**Architecture Pattern**: [PLACEHOLDER: e.g., MVC, Microservices, Serverless]  
**Target Users**: [PLACEHOLDER: Who will use this]  
**Key Features**: 
- [PLACEHOLDER: Feature 1]
- [PLACEHOLDER: Feature 2]
- [PLACEHOLDER: Feature 3]

---

## 🚦 Current Status

```yaml
Current Phase: [PLACEHOLDER: e.g., "Phase 1 - Foundation"]
Overall Progress: [PLACEHOLDER: e.g., "15%" or "3/10 modules"]
Status: [PLACEHOLDER: Active | On Hold | Blocked]
Last Updated: [PLACEHOLDER: Date/Time]
Active Developer: [PLACEHOLDER: Human/AI Agent name]
Current Focus: [PLACEHOLDER: What's being worked on now]
Next Priority: [PLACEHOLDER: Specific next task]
Blocking Issues: [PLACEHOLDER: None | Describe blockers]
```

### Quick Health Check
- **Build Status**: [PLACEHOLDER: ✅ Passing | ❌ Failing | ⚠️ Unstable]
- **Test Coverage**: [PLACEHOLDER: XX%]
- **Lint Status**: [PLACEHOLDER: ✅ Clean | ⚠️ Warnings | ❌ Errors]
- **Deploy Status**: [PLACEHOLDER: 🟢 Live | 🟡 Staging | 🔴 Local Only]

---

## 🎯 Development Phases

### Phase Overview
- [ ] **Phase 1**: [PLACEHOLDER: e.g., "Foundation & Setup"]
- [ ] **Phase 2**: [PLACEHOLDER: e.g., "Core Data Models"]
- [ ] **Phase 3**: [PLACEHOLDER: e.g., "Authentication & Authorization"]
- [ ] **Phase 4**: [PLACEHOLDER: e.g., "Business Logic Layer"]
- [ ] **Phase 5**: [PLACEHOLDER: e.g., "API Development"]
- [ ] **Phase 6**: [PLACEHOLDER: e.g., "Frontend Implementation"]
- [ ] **Phase 7**: [PLACEHOLDER: e.g., "Testing & Optimization"]
- [ ] **Phase 8**: [PLACEHOLDER: e.g., "Deployment & DevOps"]

### Detailed Phase Breakdown

#### Phase 1: [PLACEHOLDER: Phase Name]
**Goal**: [PLACEHOLDER: What this phase accomplishes]  
**Success Criteria**: 
- [PLACEHOLDER: Measurable outcome 1]
- [PLACEHOLDER: Measurable outcome 2]
**Dependencies**: [PLACEHOLDER: What must exist first]  
**Estimated Effort**: [PLACEHOLDER: Story points or hours]  
**Actual Effort**: [PLACEHOLDER: Track actual time spent]

[PLACEHOLDER: Repeat for each phase]

---

## 📁 Complete File Registry

> **Legend**: ⏳ Pending | 🚧 In Progress | ✅ Complete | ❌ Deprecated | 🔒 Do Not Modify

### Root Configuration Files
| File | Purpose | Status | Owner | Last Modified | Notes |
|------|---------|--------|-------|---------------|-------|
| `package.json` | Dependencies & Scripts | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |
| `tsconfig.json` | TypeScript Config | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |
| `.env.template` | Environment Template | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |
| `.gitignore` | Git Ignore Rules | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |
| `README.md` | Project Documentation | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |
| `INDEX.md` | This File | ✅ Complete | AI System | [PLACEHOLDER] | Auto-generated |

### Source Code (/src or /app)

#### [PLACEHOLDER: Module/Feature Name]
| File | Purpose | Status | Dependencies | Test Coverage | Notes |
|------|---------|--------|--------------|---------------|-------|
| `/src/[path]/[file]` | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

[PLACEHOLDER: Repeat for each module/feature area]

### Test Files (/tests or /__tests__)
| File | Testing | Status | Type | Coverage | Last Run |
|------|---------|--------|------|----------|----------|
| `/tests/[path]` | [PLACEHOLDER] | [PLACEHOLDER] | Unit/Integration/E2E | [PLACEHOLDER]% | [PLACEHOLDER] |

### Documentation (/DOCS)
| File | Content | Status | Audience | Last Updated |
|------|---------|--------|----------|--------------|
| `/DOCS/PROJECT_INDEX_STARTER.md` | Index System Template | ✅ Complete | AI Agents | [PLACEHOLDER] |
| `/DOCS/[PLACEHOLDER]` | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

### Build & Distribution (/dist, /build)
| Path | Content | Generated By | Git Ignored | Notes |
|------|---------|--------------|-------------|-------|
| `/dist/` | [PLACEHOLDER] | [PLACEHOLDER] | Yes/No | [PLACEHOLDER] |
| `/build/` | [PLACEHOLDER] | [PLACEHOLDER] | Yes/No | [PLACEHOLDER] |

---

## 🔄 Dependency Map

### Module Dependency Graph
```
[PLACEHOLDER: Visual representation of module dependencies]
Example Format:
  index.ts
  ├── config/* (standalone - no deps)
  ├── database/* → config
  ├── models/* → database
  ├── auth/* → models, config
  ├── services/* → models, auth
  └── api/* → services, auth
```

### Package Dependencies
```json
{
  "production": {
    "[PLACEHOLDER: package]": "[PLACEHOLDER: version]",
  },
  "development": {
    "[PLACEHOLDER: package]": "[PLACEHOLDER: version]",
  },
  "peerDependencies": {
    "[PLACEHOLDER: package]": "[PLACEHOLDER: version]",
  }
}
```

### Circular Dependencies Detected
| File A | File B | Resolution | Priority |
|--------|--------|------------|----------|
| [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

---

## 🔌 API/Interface Registry

### REST API Endpoints
| Method | Path | Purpose | Status | Auth | Rate Limit | Version |
|--------|------|---------|--------|------|------------|---------|
| GET | `/api/[path]` | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | v1 |
| POST | `/api/[path]` | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | v1 |

### GraphQL Schema
| Type | Name | Purpose | Status | Resolvers |
|------|------|---------|--------|-----------|
| Query | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |
| Mutation | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

### WebSocket Events
| Event | Direction | Payload | Purpose | Status |
|-------|-----------|---------|---------|--------|
| [PLACEHOLDER] | emit/on | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

### Database Schema
| Table/Collection | Purpose | Relationships | Indexes | Status |
|-----------------|---------|---------------|---------|--------|
| [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

### Key Types/Interfaces
| Name | Location | Purpose | Extends | Exported |
|------|----------|---------|---------|----------|
| [PLACEHOLDER] | `/src/types/[file]` | [PLACEHOLDER] | [PLACEHOLDER] | Yes/No |

---

## 🧪 Testing Strategy

### Coverage Requirements
| Type | Target | Current | Gap | Priority |
|------|--------|---------|-----|----------|
| Unit Tests | [PLACEHOLDER]% | [PLACEHOLDER]% | [PLACEHOLDER]% | [PLACEHOLDER] |
| Integration | [PLACEHOLDER]% | [PLACEHOLDER]% | [PLACEHOLDER]% | [PLACEHOLDER] |
| E2E Tests | [PLACEHOLDER]% | [PLACEHOLDER]% | [PLACEHOLDER]% | [PLACEHOLDER] |
| Performance | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

### Test Commands
```bash
# Test execution commands
npm test              # [PLACEHOLDER: Description]
npm run test:unit     # [PLACEHOLDER: Description]
npm run test:e2e      # [PLACEHOLDER: Description]
npm run test:coverage # [PLACEHOLDER: Description]
```

### Critical Test Scenarios
1. [PLACEHOLDER: Business critical flow]
2. [PLACEHOLDER: Security sensitive operation]
3. [PLACEHOLDER: High-traffic endpoint]
4. [PLACEHOLDER: Data integrity check]

---

## 🚀 Development Commands

### Initial Setup
```bash
# Clone and setup
git clone [PLACEHOLDER: repository URL]
cd [PLACEHOLDER: project name]
npm install  # or yarn/pnpm

# Environment setup
cp .env.template .env.local
# Edit .env.local with your values

# Database setup (if applicable)
[PLACEHOLDER: Database setup commands]
```

### Development Workflow
```bash
# Start development server
npm run dev

# Run tests in watch mode
npm test -- --watch

# Check code quality
npm run lint
npm run type-check

# Build for production
npm run build
```

### Deployment
```bash
# Staging deployment
[PLACEHOLDER: Staging deploy command]

# Production deployment
[PLACEHOLDER: Production deploy command]

# Rollback
[PLACEHOLDER: Rollback command]
```

---

## 📝 Environment Variables

| Variable | Purpose | Required | Default | Example |
|----------|---------|----------|---------|---------|
| [PLACEHOLDER] | [PLACEHOLDER] | Yes/No | [PLACEHOLDER] | [PLACEHOLDER] |

---

## ⚠️ Known Issues & Technical Debt

### Critical Issues
| Issue | Impact | Workaround | Fix ETA | Owner |
|-------|--------|------------|---------|-------|
| [PLACEHOLDER] | High/Medium/Low | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

### Technical Debt Register
| Item | Type | Effort | Priority | Notes |
|------|------|--------|----------|-------|
| [PLACEHOLDER] | Code/Design/Docs | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

### TODO Comments in Code
| Location | Comment | Priority | Added By | Date |
|----------|---------|----------|----------|------|
| [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

---

## 🎯 Decision Log

| Date | Decision | Alternatives Considered | Reasoning | Impact | Revisit Date |
|------|----------|------------------------|-----------|--------|--------------|
| [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

---

## 📊 Metrics & Performance

### Build Metrics
| Metric | Current | Target | Status |
|--------|---------|--------|--------|
| Build Time | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |
| Bundle Size | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |
| Lighthouse Score | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

### Runtime Performance
| Metric | Current | Target | Status |
|--------|---------|--------|--------|
| API Response Time (p95) | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |
| Memory Usage | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |
| Error Rate | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

---

## 🔄 Recent Changes Log

### Last 10 Significant Changes
| Date | Change | Files Affected | Developer | Commit/PR |
|------|--------|----------------|-----------|-----------|
| [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

---

## 🚧 Active Work Items

### Currently In Progress
| Item | Developer | Started | Target | Branch | Blockers |
|------|-----------|---------|--------|--------|----------|
| [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

### Queue (Next 5 Items)
| Priority | Item | Estimated Effort | Dependencies | Assigned To |
|----------|------|------------------|--------------|-------------|
| 1 | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |
| 2 | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

---

## 📚 Resources & Links

### External Documentation
- [PLACEHOLDER: API Documentation URL]
- [PLACEHOLDER: Design System URL]
- [PLACEHOLDER: Deployment Guide URL]

### Internal Resources
- [Architecture Diagrams](/DOCS/[PLACEHOLDER])
- [Onboarding Guide](/DOCS/[PLACEHOLDER])
- [Style Guide](/DOCS/[PLACEHOLDER])

### Monitoring & Observability
- [PLACEHOLDER: Logging Dashboard URL]
- [PLACEHOLDER: Metrics Dashboard URL]
- [PLACEHOLDER: Error Tracking URL]

---

## 🤝 Team & Ownership

### Module Ownership
| Module | Primary Owner | Backup Owner | Review Required |
|--------|--------------|--------------|-----------------|
| [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | Yes/No |

### Contact Points
| Role | Name/Identifier | Contact | Timezone |
|------|-----------------|---------|----------|
| Project Lead | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |
| Tech Lead | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |
| AI Agent Handler | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

---

## 🔐 Security Considerations

### Security Checklist
- [ ] Authentication implemented
- [ ] Authorization rules defined
- [ ] Input validation on all endpoints
- [ ] SQL injection prevention
- [ ] XSS protection
- [ ] CSRF tokens implemented
- [ ] Secrets in environment variables
- [ ] Dependencies regularly updated
- [ ] Security headers configured
- [ ] Rate limiting active

### Sensitive Data Locations
| Data Type | Location | Encryption | Access Control |
|-----------|----------|------------|----------------|
| [PLACEHOLDER] | [PLACEHOLDER] | Yes/No | [PLACEHOLDER] |

---

## 📈 Project Velocity

### Sprint/Week Metrics
| Period | Planned | Completed | Velocity | Notes |
|--------|---------|-----------|----------|-------|
| [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] | [PLACEHOLDER] |

---

**Index Version**: 2.0.0  
**Schema Version**: 2024.12  
**Last Structure Update**: [PLACEHOLDER: Date]  
**Next Review Date**: [PLACEHOLDER: Date]  

---

### 🤖 AI Agent Instructions

This INDEX.md is your single source of truth. Before starting any work:
1. Read the Current Status section
2. Check Active Work Items
3. Review Recent Changes
4. Verify your task isn't blocked

After completing work:
1. Update file statuses in the registry
2. Add to Recent Changes Log
3. Update Current Status
4. Run: "Please add the previous developments to INDEX.md, following the best practices set forth in the indexing instructions"

Remember: A well-maintained index enables seamless collaboration between human and AI developers.