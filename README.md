# AI Project Codification Standard
## Version 1.0 | December 2025

---

## Table of Contents
1. [Introduction](#introduction)
2. [Codification Format](#codification-format)
3. [Segment Definitions](#segment-definitions)
4. [Quick Reference Guide](#quick-reference-guide)
5. [Examples](#examples)
6. [Naming Decision Tree](#naming-decision-tree)

---

## Introduction

### Purpose
This document establishes a standardized naming convention for all AI program projects to ensure:
- **Clarity**: Instantly understand project scope and status
- **Organization**: Easy sorting, filtering, and searching
- **Scalability**: System works from 10 to 1000+ projects
- **Traceability**: Track project evolution and versions
- **Consistency**: Uniform approach across all teams

### Scope
Applies to all:
- AI/ML project folders in SharePoint
- Project documentation
- Model repositories
- Application deployments
- Infrastructure components

---

## Codification Format

### Standard Pattern
```
[Serial]-[Department]-[ProjectID]-[ArtifactType]-[Status]-[Version]
```

### Structure Breakdown
| Segment | Length | Required | Example |
|---------|--------|----------|---------|
| Serial Number | 2 digits | Yes | `01` |
| Department | 2-6 chars | Yes | `HR` |
| Project ID | 3-6 chars | Yes | `AVA` |
| Artifact Type | 3-8 chars | Yes | `WEBAPP` |
| Status | 3-4 chars | Yes | `PROD` |
| Version | Semantic | Yes | `v1.0` |

### Format Rules
- Use **HYPHENS (-)** as separators
- Use **UPPERCASE** for all segments except version
- **NO SPACES** in any segment
- Version always starts with lowercase **'v'**

---

## Segment Definitions

### 1. Serial Number [XX]
Sequential project identifier for easy reference and sorting.

**Format**: Two-digit number with leading zero

**Examples**:
- `01` - First project
- `09` - Ninth project
- `15` - Fifteenth project
- `99` - Ninety-ninth project

**Rules**:
- Always use 2 digits (pad with zero: `01`, `02`, `09`)
- Assign chronologically based on project initiation
- Once assigned, never change the serial number
- Reserve `00` for shared/administrative folders

**When to Increment**:
- New project starts → Assign next available number
- Don't reuse numbers from cancelled projects

---

### 2. Department/Domain [XX to XXXXXX]
Identifies the business unit or functional area owning the project.

**Standard Department Codes**:

| Code | Department | Description |
|------|------------|-------------|
| `HR` | Human Resources | HR systems, employee tools |
| `FIN` | Finance | Financial AI, accounting |
| `MFG` | Manufacturing | Production, quality control |
| `SUP` | Supply Chain | Supplier, logistics, inventory |
| `SALES` | Sales | CRM, lead generation |
| `MKT` | Marketing | Customer analytics, campaigns |
| `IT` | Information Technology | IT infrastructure, support |
| `OPS` | Operations | Business operations |
| `RND` | Research & Development | Experimental, innovation |
| `SHARED` | Cross-functional | Multi-department projects |
| `INFRA` | Infrastructure | Shared technical infrastructure |

**Creating New Codes**:
- Keep 2-6 characters
- Use standard abbreviations
- Get approval from governance committee
- Document in this guide

**Special Cases**:
- **Program Names**: Use program acronym (e.g., `AAFAQ`)
- **Multi-Department**: Use `SHARED` or create compound code (e.g., `HR-FIN`)

---

### 3. Project ID [XXX to XXXXXX]
Short, memorable identifier for the specific project.

**Guidelines**:
- 3-6 characters
- Abbreviate key project name terms
- Make it pronounceable if possible
- Avoid numbers unless necessary

**Creation Methods**:

**Method 1: Acronym**
- HR Avatar Assistant → `AVA`
- Real-time Data Bridge → `RDB`
- Supplier Agent Tool → `SAT`

**Method 2: Truncation**
- Vision Project → `VIS`
- Hub Application → `HUB`
- Studio Platform → `STUD`

**Method 3: Key Term**
- Customer Chatbot → `CHAT`
- Recommendation Engine → `RECO`
- Fraud Detection → `FRAUD`

**Examples**:
| Project Name | Project ID | Rationale |
|--------------|-----------|-----------|
| HR Avatar Assistant | `AVA` | Acronym of Avatar |
| AAFAQ AI Vision | `VIS` | Key term Vision |
| Manufacturing RDB | `RDB` | Existing acronym |
| LLM Local Server | `LLM` | Standard abbreviation |
| AI Supplier Agent | `SUPAGT` | Supplier + Agent |
| Project Hub App | `HUB` | Key term |
| Avatar Studio | `AVS` | Acronym Avatar Studio |

---

### 4. Artifact Type [XXX to XXXXXXXX]
Categorizes what the project produces or represents.

**Standard Types**:

#### Applications & Systems
| Code | Type | Description |
|------|------|-------------|
| `WEBAPP` | Web Application | Browser-based application |
| `MOBILEAPP` | Mobile Application | iOS/Android app |
| `DESKTOP` | Desktop Application | Windows/Mac desktop software |
| `N8N` | Web Server | Browser-based application |
| `API` | API Service | Backend API/microservice |
| `BOT` | Chatbot/Agent | Conversational AI |

#### AI/ML Specific
| Code | Type | Description |
|------|------|-------------|
| `MODEL` | ML Model | Trained AI/ML model |
| `PIPELINE` | ML Pipeline | Training/inference pipeline |
| `DATASET` | Dataset | Training/test data |
| `ALGO` | Algorithm | Custom algorithm implementation |

#### Infrastructure
| Code | Type | Description |
|------|------|-------------|
| `SERVER` | Server | Physical/virtual server |
| `INFRA` | Infrastructure | Cloud/network infrastructure |
| `DB` | Database | Database system |
| `TOOL` | Development Tool | Internal dev tool |

#### Documentation & Governance
| Code | Type | Description |
|------|------|-------------|
| `DOCS` | Documentation | Project documentation |
| `PROGRAM` | Program | Collection of projects |
| `REPORT` | Report/Analysis | Analysis or research report |

**Selection Guidelines**:
- Choose the **primary** artifact type
- If multiple types exist, use the **user-facing** one
- For hybrid projects, pick the **most prominent** component

**Examples**:
- Web app with ML model → `WEBAPP` (user interacts with web interface)
- API serving ML model → `API` (primary interface is API)
- Standalone trained model → `MODEL` (model is the deliverable)

---

### 5. Status/Phase [XXX to XXXX]
Current lifecycle stage of the project.

**Standard Status Codes**:

| Code | Status | Description | Color |
|------|--------|-------------|-------|
| `PLAN` | Planning | Requirements gathering, design | 🟦 Blue |
| `POC` | Proof of Concept | Initial feasibility testing | 🟧 Orange |
| `DEV` | Development | Active development | 🟨 Yellow |
| `TEST` | Testing | QA/Testing phase | 🟪 Purple |
| `UAT` | User Acceptance Testing | End-user testing | 🟪 Purple |
| `PROD` | Production | Live/deployed | 🟩 Green |
| `MAINT` | Maintenance | Production + ongoing updates | 🟩 Green |
| `SUSP` | Suspended | Temporarily paused | ⚪ Gray |
| `ARCH` | Archived | Completed/deprecated | ⚫ Black |

**Status Transitions**:
```
PLAN → POC → DEV → TEST → UAT → PROD → MAINT
                                         ↓
                                       ARCH
```

**Update Triggers**:
- Project moves to new phase → Update status in folder name
- Status changes require version update (at minimum patch version)

**Special Cases**:
- **Ongoing/Continuous**: Use `ONGOING` for administrative folders
- **Multi-Phase**: Use current primary phase
- **Parallel Development**: Use `DEV` until primary deployment

---

### 6. Version [vX.Y.Z]
Tracks iterations and changes using semantic versioning.

**Format**: `vMAJOR.MINOR.PATCH`

**Semantic Versioning Rules**:

| Component | When to Increment | Examples |
|-----------|-------------------|----------|
| **MAJOR** (X) | Breaking changes, major redesign | `v1.0` → `v2.0` |
| **MINOR** (Y) | New features, enhancements | `v1.0` → `v1.1` |
| **PATCH** (Z) | Bug fixes, small updates | `v1.0.0` → `v1.0.1` |

**Common Patterns**:

**Initial Development**:
- `v0.1` - First POC
- `v0.5` - Advanced POC/alpha
- `v0.9` - Beta/pre-production

**Production Releases**:
- `v1.0` - First production release
- `v1.1` - Added new feature
- `v1.1.1` - Fixed bug in v1.1
- `v2.0` - Major overhaul

**Pre-release Suffixes** (Optional):
- `v1.0-alpha` - Early testing version
- `v1.0-beta` - Feature-complete testing
- `v1.0-rc1` - Release candidate 1

**Version Update Guidelines**:
- Start every project at `v0.1`
- First production deployment = `v1.0`
- Document version changes in project log
- Never skip major versions

---

## Quick Reference Guide

### Codification Cheat Sheet

```
[Serial]-[Dept]-[ProjID]-[Type]-[Status]-[Version]
  01    -  HR  -  AVA   -WEBAPP-  PROD  - v1.0

Step 1: Assign next serial number
Step 2: Choose department code
Step 3: Create 3-6 char project ID
Step 4: Select artifact type
Step 5: Set current status
Step 6: Assign version (start v0.1)
```

### Most Common Combinations

| Scenario | Example Code |
|----------|--------------|
| New web app in development | `XX-DEPT-PROJ-WEBAPP-DEV-v0.1` |
| Production API service | `XX-DEPT-PROJ-API-PROD-v1.0` |
| ML model in testing | `XX-RND-PROJ-MODEL-TEST-v0.8` |
| Infrastructure server | `XX-INFRA-PROJ-SERVER-PROD-v2.1` |
| Documentation folder | `XX-SHARED-PROJ-DOCS-ONGOING-v1.0` |

---

## Examples

### Complete Real-World Examples

#### Example 1: HR Avatar Assistant
**Current Name**: `01. HR Avatar Assistant`

**New Codification**: `01-HR-AVA-WEBAPP-PROD-v1.0`

**Breakdown**:
- `01` = First project in portfolio
- `HR` = Human Resources department
- `AVA` = Avatar (project identifier)
- `WEBAPP` = Web application
- `PROD` = In production/live
- `v1.0` = First production version

---

#### Example 2: AAFAQ AI Vision
**Current Name**: `02. AAFAQ AI Vision`

**New Codification**: `02-AAFAQ-VIS-PROGRAM-PLAN-v1.0`

**Breakdown**:
- `02` = Second project
- `AAFAQ` = AAFAQ program name
- `VIS` = Vision
- `PROGRAM` = This is a program (collection of projects)
- `PLAN` = In planning phase
- `v1.0` = Initial planning version

---

#### Example 3: Manufacturing RDB
**Current Name**: `03. RDB – Manufacturing AI`

**New Codification**: `03-MFG-RDB-WEBAPP-DEV-v2.1`

**Breakdown**:
- `03` = Third project
- `MFG` = Manufacturing department
- `RDB` = Real-time Data Bridge
- `WEBAPP` = Web application
- `DEV` = In development
- `v2.1` = Second major version, first update

---

#### Example 4: LLM Local Server
**Current Name**: `04. LLM Local Server`

**New Codification**: `04-INFRA-LLM-SERVER-PROD-v1.0`

**Breakdown**:
- `04` = Fourth project
- `INFRA` = Infrastructure (shared service)
- `LLM` = Large Language Model
- `SERVER` = Server infrastructure
- `PROD` = Production/live
- `v1.0` = First production version

---

#### Example 5: AI Supplier Agent
**Current Name**: `05. AI Supplier Agent`

**New Codification**: `05-SUP-AGT-BOT-POC-v0.5`

**Breakdown**:
- `05` = Fifth project
- `SUP` = Supply chain department
- `AGT` = Agent
- `BOT` = Chatbot/agent application
- `POC` = Proof of concept stage
- `v0.5` = Mid-POC version

---

#### Example 6: AAFAQ Project Hub
**Current Name**: `06. AAFAQ Project Hub App`

**New Codification**: `06-AAFAQ-HUB-WEBAPP-PROD-v1.2`

**Breakdown**:
- `06` = Sixth project
- `AAFAQ` = AAFAQ program
- `HUB` = Hub (central platform)
- `WEBAPP` = Web application
- `PROD` = Production
- `v1.2` = Third minor release

---

#### Example 7: Avatar Studio
**Current Name**: `07. Aafaq Avatar Studio`

**New Codification**: `07-AAFAQ-AVS-WEBAPP-DEV-v1.0`

**Breakdown**:
- `07` = Seventh project
- `AAFAQ` = AAFAQ program
- `AVS` = Avatar Studio
- `WEBAPP` = Web application
- `DEV` = In development
- `v1.0` = Approaching first release

---

#### Example 8: Shared Documents
**Current Name**: `00. Projects Documents`

**New Codification**: `00-SHARED-DOCS-DOCS-ONGOING-v1.0`

**Breakdown**:
- `00` = Reserved for shared resources
- `SHARED` = Cross-functional
- `DOCS` = Documents (Project ID)
- `DOCS` = Documentation type
- `ONGOING` = Continuous/no end date
- `v1.0` = Current structure version

---

### Complete Migration Table

| # | Current Name | New Codification | Notes |
|---|--------------|------------------|-------|
| 00 | Projects Documents | `00-SHARED-DOCS-DOCS-ONGOING-v1.0` | Shared resources |
| 00 | Timesheets records | `00-SHARED-TIME-DOCS-ONGOING-v1.0` | Administrative |
| 01 | HR Avatar Assistant | `01-HR-AVA-WEBAPP-PROD-v1.0` | Production web app |
| 02 | AAFAQ AI Vision | `02-AAFAQ-VIS-PROGRAM-PLAN-v1.0` | Program planning |
| 03 | RDB – Manufacturing AI | `03-MFG-RDB-WEBAPP-DEV-v2.1` | In development |
| 04 | LLM Local Server | `04-INFRA-LLM-SERVER-PROD-v1.0` | Infrastructure |
| 05 | AI Supplier Agent | `05-SUP-AGT-BOT-POC-v0.5` | POC stage |
| 06 | AAFAQ Project Hub App | `06-AAFAQ-HUB-WEBAPP-PROD-v1.2` | Production |
| 07 | Aafaq Avatar Studio | `07-AAFAQ-AVS-WEBAPP-DEV-v1.0` | In development |

---

## Naming Decision Tree

### Step-by-Step Process

```
START: New Project Needs Naming
│
├─→ Step 1: Assign Serial Number
│   ├─ Check last used number in portfolio
│   ├─ Increment by 1
│   └─ Use 00 only for shared/admin folders
│
├─→ Step 2: Identify Department/Domain
│   ├─ Single department? → Use dept code
│   ├─ Part of program? → Use program code
│   ├─ Infrastructure? → Use INFRA
│   └─ Cross-functional? → Use SHARED
│
├─→ Step 3: Create Project ID
│   ├─ Extract key terms from name
│   ├─ Create 3-6 char abbreviation
│   ├─ Check for conflicts with existing IDs
│   └─ Make it memorable and pronounceable
│
├─→ Step 4: Select Artifact Type
│   ├─ User-facing application?
│   │   ├─ Web-based? → WEBAPP
│   │   ├─ Mobile? → MOBILEAPP
│   │   ├─ Desktop? → DESKTOP
│   │   └─ Conversational? → BOT
│   ├─ Backend service? → API
│   ├─ ML/AI component?
│   │   ├─ Model file? → MODEL
│   │   ├─ Training system? → PIPELINE
│   │   └─ Data? → DATASET
│   ├─ Infrastructure? → SERVER or INFRA
│   ├─ Documentation? → DOCS
│   └─ Program/Portfolio? → PROGRAM
│
├─→ Step 5: Determine Current Status
│   ├─ Just starting? → PLAN
│   ├─ Testing feasibility? → POC
│   ├─ Building features? → DEV
│   ├─ QA testing? → TEST
│   ├─ User testing? → UAT
│   ├─ Live/deployed? → PROD
│   ├─ Continuous updates? → MAINT
│   └─ Finished/old? → ARCH
│
└─→ Step 6: Set Version
    ├─ First time creating?
    │   ├─ POC/Planning? → v0.1
    │   └─ Production ready? → v1.0
    ├─ Updating existing?
    │   ├─ Major change? → Increment X (v1.0→v2.0)
    │   ├─ New feature? → Increment Y (v1.0→v1.1)
    │   └─ Bug fix? → Increment Z (v1.0.0→v1.0.1)
    └─ Pre-release? → Add suffix (v1.0-beta)

RESULT: [Serial]-[Dept]-[ProjID]-[Type]-[Status]-[Version]
```

---

### Version Control of This Document

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| v1.0 | Dec 2025 | Initial release | [Ali] |

**Update Process**:
- Minor clarifications: Update immediately, increment patch version
- New codes/types: Governance approval, increment minor version
- Major restructure: Full review, increment major version

---

## Appendices

### Appendix A: Full Code Lists

**Department Codes**:
```
FIN     - Finance
HR      - Human Resources
IT      - Information Technology
MFG     - Manufacturing
MKT     - Marketing
OPS     - Operations
RND     - Research & Development
SALES   - Sales
SUP     - Supply Chain
SHARED  - Cross-functional
INFRA   - Infrastructure
```

**Artifact Types**:
```
API        - API Service
BOT        - Chatbot/Agent
DATASET    - Dataset
DB         - Database
DESKTOP    - Desktop Application
DOCS       - Documentation
INFRA      - Infrastructure
MOBILEAPP  - Mobile Application
MODEL      - ML Model
PIPELINE   - ML Pipeline
PROGRAM    - Program/Portfolio
REPORT     - Report/Analysis
SERVER     - Server
TOOL       - Development Tool
WEBAPP     - Web Application
```

**Status Codes**:
```
PLAN    - Planning
POC     - Proof of Concept
DEV     - Development
TEST    - Testing
UAT     - User Acceptance Testing
PROD    - Production
MAINT   - Maintenance
ONGOING - Continuous
SUSP    - Suspended
ARCH    - Archived
```

---

### Appendix B: Naming Worksheet

Use this template when naming a new project:

```
PROJECT NAMING WORKSHEET
========================

Project Name: _________________________________

1. Serial Number: ____ (Next available: __)

2. Department/Domain: ______ 
   Options: HR, FIN, MFG, SUP, SALES, MKT, IT, OPS, RND, SHARED, INFRA
   Custom: ________

3. Project ID (3-6 chars): ______
   Based on: □ Acronym  □ Key Term  □ Truncation

4. Artifact Type: __________
   Options: WEBAPP, MOBILEAPP, API, BOT, MODEL, SERVER, DOCS, PROGRAM
   Other: __________

5. Current Status: ______
   Options: PLAN, POC, DEV, TEST, UAT, PROD, MAINT, ARCH

6. Version: v____
   Starting: v0.1 (POC/Dev)  or  v1.0 (Production)

FINAL CODE:
═══════════════════════════════════════════════
[____]-[____]-[____]-[____]-[____]-[____]
```
