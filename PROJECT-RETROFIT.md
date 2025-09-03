# PROJECT_RETROFIT_PROMPT.md
## Systematic Project Retrofit for AI-Agent Documentation System

> **🤖 AI AGENT**: This is a multi-phase retrofit process. Work through each phase systematically to avoid token exhaustion.

---

## 🎯 Mission Overview

Transform an undocumented project into a fully AI-agent-ready codebase by:
1. Analyzing the existing structure in manageable chunks
2. Pre-configuring self-deploying templates with discovered data
3. Creating a smooth migration path to the documentation system
4. Ensuring all future agents can work efficiently

---

## 📋 Pre-Retrofit Checklist

### Verify These Files Exist in Root (But NOT Activated)
- [ ] PROJECT_INDEX_STARTER.md (unmodified template)
- [ ] DEVELOPMENT_LOG_TEMPLATE.md (unmodified template)
- [ ] AGENT-INSTRUCTIONS.md (unmodified template)
- [ ] DEPENDENCY_UPDATES_HELPER.md (if present)
- [ ] DEPENDENCY_PRE-SETUP.md (if present)

### Initial Assessment Commands
```bash
# Count files by type
find . -type f -name "*.js" -o -name "*.ts" -o -name "*.jsx" -o -name "*.tsx" | wc -l
find . -type f -name "*.py" | wc -l
find . -type f -name "*.json" -o -name "*.yml" -o -name "*.yaml" | wc -l

# Check project size
du -sh .
find . -type f | wc -l

# Check for git history
git log --oneline -10 2>/dev/null || echo "No git history"

# Identify main directories
ls -la | grep "^d" | awk '{print $9}' | grep -v "^\."
```

---

## 🔄 PHASE 1: Quick Discovery (15 min max)

### Step 1.1: Identify Project Type
```bash
# Check for framework indicators
ls package.json 2>/dev/null && echo "Node.js project detected"
ls requirements.txt 2>/dev/null && echo "Python project detected"
ls go.mod 2>/dev/null && echo "Go project detected"
ls Gemfile 2>/dev/null && echo "Ruby project detected"
ls pom.xml 2>/dev/null && echo "Java/Maven project detected"
ls composer.json 2>/dev/null && echo "PHP project detected"
```

### Step 1.2: Create RETROFIT_DISCOVERY.md
```markdown
# RETROFIT_DISCOVERY.md
## Initial Project Analysis

### Project Type
- **Primary Language**: [Detected language]
- **Framework**: [Detected framework]
- **Build System**: [npm/yarn/pip/maven/etc]
- **Project Age**: [From git or file dates]

### Size Metrics
- **Total Files**: [Count]
- **Lines of Code**: [Estimate]
- **Main Directories**: [List top-level dirs]
- **Depth**: [Max directory depth]

### Key Files Found
- **Entry Point**: [main.js/index.py/etc]
- **Config Files**: [List all found]
- **Documentation**: [Any .md files found]
- **Tests**: [Test directory if exists]

### Discovered Structure
```
[Project root]
├── [dir1]/ (X files)
├── [dir2]/ (Y files)
└── [dir3]/ (Z files)
```

### Next Analysis Targets
1. [Largest directory first]
2. [Core functionality directory]
3. [Configuration directory]
```

---

## 🔄 PHASE 2: Chunked Deep Analysis (30 min per chunk)

### Step 2.1: Create Analysis Chunks
Divide project into analyzable chunks (max 50 files per chunk):

```markdown
# RETROFIT_CHUNKS.md
## Analysis Plan

### Chunk 1: Core/Source Code
- Directory: /src or equivalent
- File Count: [X]
- Priority: HIGH
- Status: ⏳ Pending

### Chunk 2: Configuration
- Directory: Root config files
- File Count: [X]
- Priority: HIGH
- Status: ⏳ Pending

### Chunk 3: Tests
- Directory: /tests or /__tests__
- File Count: [X]
- Priority: MEDIUM
- Status: ⏳ Pending

### Chunk 4: Documentation
- Directory: /docs and root .md files
- File Count: [X]
- Priority: MEDIUM
- Status: ⏳ Pending

### Chunk 5: Build/Deploy
- Directory: /scripts, /.github, etc
- File Count: [X]
- Priority: LOW
- Status: ⏳ Pending
```

### Step 2.2: Analyze Each Chunk
For each chunk, create a section in RETROFIT_ANALYSIS.md:

```markdown
# RETROFIT_ANALYSIS.md
## Chunk [N] Analysis: [Name]

### Files Inventoried
| File Path | Purpose | Dependencies | Status | Notes |
|-----------|---------|--------------|--------|-------|
| [path] | [detected purpose] | [imports] | ✅ Exists | [issues] |

### Patterns Detected
- **Architecture**: [MVC/Microservices/etc]
- **Naming Convention**: [camelCase/snake_case]
- **Error Handling**: [try-catch/promises/etc]
- **Testing Approach**: [unit/integration/none]

### Dependencies Found
- External: [list from package.json/requirements.txt]
- Internal: [common imports between files]

### Technical Debt Identified
- [ ] [Missing tests for X]
- [ ] [No error handling in Y]
- [ ] [TODO comment: Z]

### Chunk Status
✅ Analysis Complete - [Date/Time]
```

**IMPORTANT**: After each chunk, save progress and note token usage.

---

## 🔄 PHASE 3: Pre-Configure Self-Deploying Templates

### Step 3.1: Modify PROJECT_INDEX_STARTER.md
Based on discoveries, pre-populate the template:

```markdown
## Modifications to Add to PROJECT_INDEX_STARTER.md

### In the Template Section, Pre-fill:
- Project Name: [Discovered from package.json/README]
- Tech Stack: [Detected stack]
- Architecture Pattern: [Detected pattern]
- Current Phase: "Retrofit - [Detected completion %]"

### Pre-populate File Registry:
[Generate complete file list from analysis]

### Pre-fill Dependency Map:
[Create from discovered imports]

### Add Discovered Issues:
[List all TODOs and FIXMEs found]
```

### Step 3.2: Modify DEVELOPMENT_LOG_TEMPLATE.md
Add discovered work area codes:

```markdown
## Additional Work Area Codes for This Project

Based on analysis, add these project-specific codes:

| Code | Area | Description |
|------|------|-------------|
| [FEAT1] | [Feature Area 1] | [Specific to this project] |
| [FEAT2] | [Feature Area 2] | [Specific to this project] |

### Add Retroactive Entries Template:
[Create template entries from git history or file dates]
```

### Step 3.3: Modify AGENT-INSTRUCTIONS.md
Add project-specific patterns:

```markdown
## Project-Specific Patterns to Add

### Detected Patterns in Use:
- API Pattern: [Specific pattern found]
- Database Pattern: [Specific pattern found]
- Testing Pattern: [Specific pattern found]

### Project Conventions:
- File Naming: [Convention detected]
- Function Naming: [Convention detected]
- Error Messages: [Format detected]
```

---

## 🔄 PHASE 4: Create Retroactive Documentation

### Step 4.1: Generate Historical Timeline
Create RETROFIT_TIMELINE.md:

```markdown
# RETROFIT_TIMELINE.md
## Reconstructed Development History

### Phase 1: Foundation (Detected)
**Period**: [Earliest file dates]
**Components**: 
- [Basic structure files]
**Evidence**: File creation dates, initial commits

### Phase 2: Core Features (Detected)
**Period**: [Next wave of files]
**Components**:
- [Main functionality]
**Evidence**: Import patterns, dependencies

### Phase 3: Current State
**Period**: [Most recent changes]
**Status**: [Active/Dormant/Maintenance]
**Last Activity**: [Date]

### Recommended Next Phase
Based on analysis:
- Missing: [Critical components not found]
- Incomplete: [Partially implemented features]
- Priority: [What to build next]
```

### Step 4.2: Create Migration Plan
Create RETROFIT_MIGRATION.md:

```markdown
# RETROFIT_MIGRATION.md
## Migration to Full Documentation System

### Step 1: Backup Current State
```bash
git add -A
git commit -m "Pre-documentation retrofit checkpoint"
git tag pre-retrofit
```

### Step 2: Deploy Documentation System
**Order of Activation**:
1. Run modified PROJECT_INDEX_STARTER.md
2. Run modified DEVELOPMENT_LOG_TEMPLATE.md  
3. Run modified AGENT-INSTRUCTIONS.md
4. Run DEPENDENCY_PRE-SETUP.md (if needed)
5. Run DEPENDENCY_UPDATES_HELPER.md (if needed)

### Step 3: Verify Deployment
- [ ] INDEX.md exists and is complete
- [ ] DEVELOPMENT_LOG.md has retroactive entries
- [ ] AGENTS.md contains project patterns
- [ ] All templates moved to DOCS/

### Step 4: First Post-Retrofit Session
Recommended first task:
- Add missing tests for [critical component]
- Document [undocumented API]
- Fix [highest priority issue]
```

---

## 🔄 PHASE 5: Final Integration

### Step 5.1: Create Summary Report
Create RETROFIT_COMPLETE.md:

```markdown
# RETROFIT_COMPLETE.md
## Retrofit Summary Report

### Metrics
- **Files Analyzed**: [Total]
- **Issues Found**: [Count]
- **TODOs Discovered**: [Count]
- **Missing Tests**: [Count]
- **Documentation Coverage**: [Before]% → [After]%

### Health Score
| Category | Score | Notes |
|----------|-------|-------|
| Code Organization | [A-F] | [Explanation] |
| Test Coverage | [A-F] | [Explanation] |
| Documentation | [A-F] | [Explanation] |
| Dependencies | [A-F] | [Explanation] |
| Security | [A-F] | [Explanation] |

### Critical Actions Required
1. 🔴 **Urgent**: [Security or breaking issues]
2. 🟡 **Important**: [Should fix soon]
3. 🟢 **Nice to Have**: [Improvements]

### Ready for Development
✅ Documentation system prepared
✅ All files indexed
✅ History reconstructed
✅ Next steps identified

**Recommended Next Command**:
"Please activate the documentation system by running PROJECT_INDEX_STARTER.md"
```

### Step 5.2: Clean Up Retrofit Files
```bash
# Create retrofit archive
mkdir -p DOCS/retrofit-archive
mv RETROFIT_*.md DOCS/retrofit-archive/

# Keep only the summary in root temporarily
cp DOCS/retrofit-archive/RETROFIT_COMPLETE.md ./

# Update INDEX.md (once created) to reference archive
```

---

## 📊 Token Management Strategy

### Chunk Size Guidelines
- **Small Project** (<100 files): 2-3 chunks
- **Medium Project** (100-500 files): 5-10 chunks
- **Large Project** (500+ files): 10-20 chunks
- **Massive Project** (2000+ files): Focus on core modules only

### Token Conservation Techniques
1. **Summarize, Don't Duplicate**: Reference file paths, don't show content
2. **Use Tables**: More efficient than prose
3. **Batch Similar Items**: Group files by pattern
4. **Defer Details**: Mark for detailed analysis later
5. **Progressive Refinement**: Start broad, zoom in as needed

### When Approaching Token Limit
```markdown
## Checkpoint Save Required

### Completed
- [What's done]

### In Progress  
- [Current chunk]
- [Progress %]

### Next Session Should
- Continue from: [Specific file/directory]
- Resume with: [Specific task]
- Token budget: [Remaining analysis]

Save all RETROFIT_*.md files before ending session.
```

---

## 🎯 Success Criteria

The retrofit is complete when:

1. **Analysis Complete**
   - [ ] All chunks analyzed
   - [ ] All files catalogued
   - [ ] All patterns documented

2. **Templates Prepared**
   - [ ] PROJECT_INDEX_STARTER.md pre-configured
   - [ ] DEVELOPMENT_LOG_TEMPLATE.md customized
   - [ ] AGENT-INSTRUCTIONS.md enhanced
   - [ ] Dependencies documented (if applicable)

3. **Documentation Ready**
   - [ ] Retroactive history created
   - [ ] Current state documented
   - [ ] Migration plan ready
   - [ ] Next steps identified

4. **Handoff Ready**
   - [ ] RETROFIT_COMPLETE.md summarizes everything
   - [ ] Clear instructions for activation
   - [ ] No blockers for next agent
   - [ ] Project ready for AI-assisted development

---

## 🚀 Activation Instructions for User

After retrofit is complete:

```markdown
Your project has been successfully analyzed and prepared for AI-assisted development.

**Next Steps**:
1. Review RETROFIT_COMPLETE.md for the health assessment
2. Run: "Please activate PROJECT_INDEX_STARTER.md to create the INDEX.md"
3. Run: "Please activate DEVELOPMENT_LOG_TEMPLATE.md to create the development log"
4. Run: "Please activate AGENT-INSTRUCTIONS.md to create AGENTS.md"
5. Begin development with full documentation support

**All retrofit analysis** has been archived in DOCS/retrofit-archive/ for reference.

Your project is now ready for efficient AI-agent collaboration!
```

---

## ⚠️ Special Situations

### If Project is Partially Documented
- Merge existing docs with discoveries
- Note conflicts between docs and reality
- Prefer code truth over documentation claims

### If Project is Abandoned/Incomplete
- Document what exists
- Clearly mark incomplete areas
- Suggest completion strategy

### If Project is Massive (>2000 files)
- Focus on core business logic only
- Document directory structure broadly
- Mark peripheral areas for later analysis
- Create RETROFIT_DEFERRED.md for future work

### If Multiple Languages/Frameworks
- Separate analysis by technology
- Create chunk for each major component
- Note integration points
- Document communication patterns

---

**Retrofit System Version**: 2.0.0  
**Optimized For**: Token efficiency and systematic analysis  
**Time Estimate**: 2-4 hours for medium project  

---

### 🤖 Remember: Work systematically, save progress frequently, and prepare everything for smooth activation!