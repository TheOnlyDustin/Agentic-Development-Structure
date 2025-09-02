## **Project Retrofit Prompt**

You are tasked with retrofitting an existing project with a comprehensive AI-agent tracking system. You will analyze the current codebase and create complete documentation to enable smooth AI-assisted development going forward.

\#\# Your Mission

Transform this existing project into a well-documented, AI-agent-ready codebase by creating a complete index and reconstructing the development history.

\#\# Provided Resources

1\. \*\*AGENT\_INSTRUCTIONS.md\*\* \- Universal coding guidelines for AI development

2\. \*\*DEVELOPMENT\_LOG.md\*\* \- Template for session tracking

3\. \*\*PROJECT\_INDEX\_STARTER.md\*\* \- Template for project indexing

\#\# Phase 1: Project Analysis (Complete First)

1\. \*\*Scan the entire project structure\*\* and create a complete file tree

2\. \*\*Identify the tech stack\*\* by examining:

   \- package.json / requirements.txt / go.mod / Gemfile / etc.

   \- Configuration files

   \- Import statements

   \- File extensions

3\. \*\*Determine project type and purpose\*\* by analyzing:

   \- README.md (if exists)

   \- Main entry points

   \- API routes or user interfaces

   \- Business logic patterns

4\. \*\*Detect development phases\*\* by looking at:

   \- Logical module boundaries

   \- Dependency relationships

   \- Git history (if available)

   \- File creation dates

   \- Code comments

\#\# Phase 2: Create PROJECT\_INDEX.md

Using PROJECT\_INDEX\_STARTER.md as your template:

1\. \*\*Replace ALL placeholders\*\* with actual project information

2\. \*\*Define logical phases\*\* based on your analysis:

   \- Group related functionality into phases

   \- Order phases by dependency (foundation → features)

   \- Each phase should be independently testable

3\. \*\*Create the complete File Registry\*\*:

   \- List EVERY file in the project

   \- Group by module/feature area

   \- Mark all existing files as ✅ Complete

   \- Note any missing files as ⏳ Pending

   \- Document actual dependencies between files

4\. \*\*Map the dependency graph\*\*:

   \- Show how modules interconnect

   \- Identify circular dependencies (mark as issues)

   \- Note external service dependencies

5\. \*\*Document all APIs/Interfaces\*\*:

   \- REST endpoints (scan route files)

   \- GraphQL schemas

   \- Database models

   \- Public functions/classes

6\. \*\*Identify issues and technical debt\*\*:

   \- Missing tests

   \- No documentation

   \- Incomplete features

   \- TODO comments in code

   \- Deprecated dependencies

\#\# Phase 3: Reconstruct DEVELOPMENT\_LOG.md

Create a retroactive development log by:

1\. \*\*If Git history exists\*\*, analyze:

   \`\`\`bash

   git log \--oneline \--graph \--all

   git log \--stat

   git diff \--stat \<commit1\> \<commit2\>

Create log entries for major commits/merges

2. **If no Git history**, examine:  
   * File creation/modification dates  
   * Code comments with dates  
   * TODO/FIXME comments  
   * Version numbers in files  
   * Changelog files  
3. **For the retroactive log entries**, document:  
   * Approximate dates/phases  
   * Major features completed (based on code present)  
   * Likely decision points (why certain patterns were chosen)  
   * Technical debt accumulated  
   * Missing pieces or incomplete features  
4. **Create a "Current State" entry** that includes:  
   * What works  
   * What's broken  
   * What's incomplete  
   * Critical warnings for next developer  
   * Recommended next steps

## **Phase 4: Analysis Report**

Create RETROFIT\_ANALYSIS.md with:

### **Project Health Assessment**

* **Completeness**: X% (based on typical patterns for this project type)  
* **Test Coverage**: X% (actual if available, estimate if not)  
* **Documentation**: X% (inline comments, README, API docs)  
* **Technical Debt Score**: High/Medium/Low

### **Critical Findings**

* **Missing Core Components**: \[List any expected files/features not found\]  
* **Security Concerns**: \[Any obvious security issues\]  
* **Performance Issues**: \[Large files, inefficient patterns\]  
* **Dependency Issues**: \[Outdated, deprecated, or risky packages\]

### **Modernization Recommendations**

* **Immediate Priorities**: \[Top 3 things to fix/add\]  
* **Phase-by-Phase Improvement Plan**: \[How to systematically improve\]  
* **Estimated Effort**: \[Hours/days per phase\]

## **Phase 5: Setup for Future Development**

1. **Create any missing essential files**:  
   * .gitignore (if missing)  
   * .env.template (extract from code)  
   * README.md (if missing, create basic one)  
2. **Add helper scripts** (create /scripts/dev-helpers.md):  
   * How to run the project  
   * How to run tests  
   * How to build/deploy  
   * Common development tasks  
3. **Document the development environment**:  
   * Required tools/versions  
   * Environment variables needed  
   * External services required  
   * Local setup steps

## **Output Requirements**

You should create/update these files:

1. **PROJECT\_INDEX.md** \- Complete index of the existing project  
2. **DEVELOPMENT\_LOG.md** \- Reconstructed history \+ current state  
3. **RETROFIT\_ANALYSIS.md** \- Health assessment and recommendations  
4. **scripts/dev-helpers.md** \- Quick reference commands  
5. **.env.template** \- If missing and environment variables found

## **Special Instructions**

* **Be thorough**: Index EVERY file, even if it seems unimportant  
* **Be honest**: Document what's actually there, not what should be there  
* **Be helpful**: Add notes about confusing code or potential issues  
* **Be practical**: Focus on what will help the next developer

## **Verification**

After completing the retrofit:

1. Verify PROJECT\_INDEX.md accounts for every file  
2. Ensure DEVELOPMENT\_LOG.md explains the current state  
3. Check that another AI agent could continue development using only your documentation  
4. Test that any documented commands actually work

Start by examining the project root directory and telling me:

1. What type of project this is  
2. What the main tech stack appears to be  
3. Whether version control history is available  
4. An estimate of project size (files/lines of code)

Then proceed with the complete retrofit process.

\#\# 🎯 Follow-Up Prompt (After Initial Retrofit)

Now that the project has been indexed and documented, please:

1. **Identify the next logical development phase** based on:  
   * The retrofit analysis findings  
   * Missing critical features  
   * Technical debt priorities  
   * Business value  
2. **Create a PHASE\_\[N\]\_PLAN.md** for the next phase that includes:  
   * Specific tasks with acceptance criteria  
   * Files to be created/modified  
   * Tests to be written  
   * Estimated time for each task  
   * Dependencies and blockers  
3. **Update PROJECT\_INDEX.md** to add this future phase to the plan  
4. **Create a pre-flight checklist** for the next developer that verifies:  
   * The environment is correctly set up  
   * All dependencies are installed  
   * The project builds and runs  
   * Tests pass (or document which ones don't)

This will ensure the project is ready for immediate continued development.

