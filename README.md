# AI Project Codification Standard
## Version 1.1 | December 2025

---

## Table of Contents
1. [Introduction](#introduction)
2. [Codification Format](#codification-format)
3. [Segment Definitions](#segment-definitions)
4. [Quick Reference Guide](#quick-reference-guide)
5. [Examples](#examples)


---

## Introduction

### Purpose
This document establishes a standardized naming convention for all AI program projects to ensure:
- **Clarity**: Instantly understand project scope and status
- **Organization**: Easy sorting, filtering, and searching
- **Scalability**: System works from 10 to 1000+ projects
- **Traceability**: Track project evolution and versions
- **Consistency**: Uniform approach across all teams

### Key Changes in v3.0
- **Removed Department segment** for simplified structure
- **Removed Versioning segment** - version tracking via file history
- **Maximum 3 characters** for all segments
- **Ultra-concise** 4-segment naming structure

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
[Serial]-[ProjectID]-[Type]-[Status]
```

### Structure Breakdown
| Segment | Length | Required | Example |
|---------|--------|----------|---------|
| Serial Number | 3 chars | Yes | `01` or `A1` |
| Project ID | 2-3 chars | Yes | `AVA` |
| Artifact Type | 3 chars | Yes | `WEB` |
| Status | 3 chars | Yes | `PRD` |

### Format Rules
- Use **HYPHENS (-)** as separators
- Use **UPPERCASE** for all segments
- **NO SPACES** in any segment
- **Maximum 3 characters** per segment

---

## Segment Definitions

### 1. Serial Number [XX or XXX]
Sequential project identifier for easy reference and sorting.

**Format**: 3 character identifier

**Options**:
- **Numeric**: `001`, `002`, `099` (3 digits with leading zero)

**Examples**:
- `001` - First project
- `009` - Ninth project
- `015` - Fifteenth project
- `099` - Ninety-ninth project
- `101` - 101st project (after 01-99)
- `115` - 115th project

**Rules**:
- Always use 2-3 characters
- Start with `01`, `02`, etc.
- After `99`, use `A1`, `A2`, etc.
- Once assigned, never change the serial number
- Reserve `00` for shared/administrative folders

**When to Increment**:
- New project starts → Assign next available number
- Don't reuse numbers from cancelled projects

---

### 2. Project ID [XX to XXX]
Short, memorable identifier for the specific project.

**Guidelines**:
- 2-3 characters maximum
- Abbreviate key project name terms
- Make it pronounceable if possible
- Avoid numbers unless necessary

**Creation Methods**:

**Method 1: Acronym (3 chars)**
- HR Avatar → `AVA`
- Real-time Data Bridge → `RDB`
- Supplier Agent Tool → `SAT`

**Method 2: Truncation (2-3 chars)**
- Vision Project → `VIS`
- Hub Application → `HUB`
- Studio Platform → `STU`

**Method 3: Key Term (2-3 chars)**
- Chatbot → `CHT`
- Recommendation → `REC`
- Fraud Detection → `FRD`

**Examples**:
| Project Name | Project ID | Rationale |
|--------------|-----------|-----------|
| HR Avatar Assistant | `AVA` | Avatar acronym |
| AI Vision | `VIS` | Key term Vision |
| Manufacturing RDB | `RDB` | Existing acronym |
| LLM Local Server | `LLM` | Standard abbreviation |
| AI Supplier Agent | `SAG` | Supplier Agent |
| Project Hub App | `HUB` | Key term |
| Avatar Studio | `AVS` | Avatar Studio |
| Documents | `DOC` | Key term |
| Timesheets | `TIM` | Key term |

---

### 3. Artifact Type [XXX]
Categorizes what the project produces (exactly 3 characters).

**Standard Types**:

#### Applications & Systems
| Code | Type | Description |
|------|------|-------------|
| `WEB` | Web Application | Browser-based application |
| `MOB` | Mobile Application | iOS/Android app |
| `DSK` | Desktop Application | Windows/Mac desktop software |
| `API` | API Service | Backend API/microservice |
| `BOT` | Chatbot/Agent | Conversational AI |

#### AI/ML Specific
| Code | Type | Description |
|------|------|-------------|
| `MOD` | ML Model | Trained AI/ML model |
| `PIP` | ML Pipeline | Training/inference pipeline |
| `DAT` | Dataset | Training/test data |
| `ALG` | Algorithm | Custom algorithm |

#### Infrastructure
| Code | Type | Description |
|------|------|-------------|
| `SRV` | Server | Physical/virtual server |
| `INF` | Infrastructure | Cloud/network infrastructure |
| `DBS` | Database | Database system |
| `TOL` | Development Tool | Internal dev tool |

#### Documentation & Governance
| Code | Type | Description |
|------|------|-------------|
| `DOC` | Documentation | Project documentation |
| `PRG` | Program | Collection of projects |
| `RPT` | Report/Analysis | Analysis or research report |

**Selection Guidelines**:
- Choose the **primary** artifact type
- If multiple types exist, use the **user-facing** one
- For hybrid projects, pick the **most prominent** component

**Examples**:
- Web app with ML model → `WEB` (user interacts with web interface)
- API serving ML model → `API` (primary interface is API)
- Standalone trained model → `MOD` (model is the deliverable)

---

### 4. Status/Phase [XXX]
Current lifecycle stage of the project (exactly 3 characters).

**Standard Status Codes**:

| Code | Status | Description | 
|------|--------|-------------|
| `PLN` | Planning | Requirements gathering, design | 
| `POC` | Proof of Concept | Initial feasibility testing | 
| `DEV` | Development | Active development | 
| `TST` | Testing | QA/Testing phase |
| `UAT` | User Acceptance Testing | End-user testing | 
| `PRD` | Production | Live/deployed | 
| `MNT` | Maintenance | Production + ongoing updates | 
| `ARC` | Archived | Completed/deprecated |
| `ONG` | Ongoing | Continuous/administrative |
| `SUS` | Suspended | Temporarily paused |

**Status Transitions**:
```
PLN → POC → DEV → TST → UAT → PRD → MNT
                                  ↓
                                ARC
```

**Update Triggers**:
- Project moves to new phase → Update status in folder name
- Major changes → Consider creating new project with new serial
- For version tracking → Use file modification dates or internal documentation

---

### 5. Change Tracking
Since version numbers are removed from the naming convention, track changes through:

**File System**:
- Use file modification dates
- Enable version history in SharePoint
- Use "Modified Date" column for tracking

**Documentation**:
- Maintain a CHANGELOG.md inside each project folder
- Document major updates in project documentation
- Use status changes (DEV→TST→PRD) to indicate progress

**Major Revisions**:
- For complete redesigns, create new project with new serial number
- Archive old project by changing status to ARC
- Reference old project in new project documentation

---

## Quick Reference Guide

### Codification Cheat Sheet

```
[Serial]-[ProjID]-[Type]-[Status]
  01    -  AVA   - WEB -  PRD

Step 1: Assign next serial number (01-99, then A1-Z9)
Step 2: Create 2-3 char project ID
Step 3: Select 3-char artifact type
Step 4: Set 3-char current status
```

### Most Common Combinations

| Scenario | Example Code |
|----------|--------------|
| New web app in development | `XX-PRJ-WEB-DEV` |
| Production API service | `XX-PRJ-API-PRD` |
| ML model in testing | `XX-PRJ-MOD-TST` |
| Infrastructure server | `XX-PRJ-SRV-PRD` |
| Documentation folder | `XX-DOC-DOC-ONG` |

### All 3-Character Codes

**Type Codes**:
```
WEB - Web App          MOB - Mobile App       DSK - Desktop
API - API Service      BOT - Chatbot          MOD - ML Model
PIP - ML Pipeline      DAT - Dataset          ALG - Algorithm
SRV - Server           INF - Infrastructure   DBS - Database
TOL - Tool             DOC - Documentation    PRG - Program
RPT - Report
```

**Status Codes**:
```
PLN - Planning         POC - Proof Concept    DEV - Development
TST - Testing          UAT - User Testing     PRD - Production
MNT - Maintenance      ARC - Archived         ONG - Ongoing
SUS - Suspended
```

---

## Examples

### Complete Real-World Examples

#### Example 1: HR Avatar Assistant
**Current Name**: `01. HR Avatar Assistant`

**New Codification**: `01-AVA-WEB-PRD`

**Breakdown**:
- `01` = First project in portfolio
- `AVA` = Avatar
- `WEB` = Web application
- `PRD` = Production/live

---

#### Example 2: AAFAQ AI Vision
**Current Name**: `02. AAFAQ AI Vision`

**New Codification**: `02-VIS-PRG-PLN`

**Breakdown**:
- `02` = Second project
- `VIS` = Vision
- `PRG` = Program (collection of projects)
- `PLN` = In planning phase

---

## Appendices

### Appendix A: Complete Code Reference

**Type Codes (3 chars)**:
```
API - API Service
BOT - Chatbot/Agent
DAT - Dataset
DBS - Database
DOC - Documentation
DSK - Desktop Application
INF - Infrastructure
MOB - Mobile Application
MOD - ML Model
PIP - ML Pipeline
PRG - Program/Portfolio
RPT - Report/Analysis
SRV - Server
TOL - Development Tool
WEB - Web Application
ALG - Algorithm
```

**Status Codes (3 chars)**:
```
PLN - Planning
POC - Proof of Concept
DEV - Development
TST - Testing
UAT - User Acceptance Testing
PRD - Production
MNT - Maintenance
ONG - Ongoing
SUS - Suspended
ARC - Archived
```

---

### Appendix B: Naming Worksheet

Use this template when naming a new project:

```
PROJECT NAMING WORKSHEET
========================

Project Name: _________________________________

1. Serial Number: ____ 
   Next available: __
   (Use 01-99, then A1-Z9)

2. Project ID (2-3 chars): ___
   Based on: □ Acronym  □ Key Term  □ Truncation
   
3. Artifact Type (3 chars): ___
   Options: WEB, MOB, DSK, API, BOT, MOD, PIP, 
            DAT, SRV, INF, DBS, TOL, DOC, PRG, RPT

4. Current Status (3 chars): ___
   Options: PLN, POC, DEV, TST, UAT, PRD, 
            MNT, ONG, SUS, ARC

FINAL CODE:
═══════════════════════════════════════
[__]-[___]-[___]-[___]
```

---
