# CROWN-STANDARD VERSIONING POLICY DOCUMENT
SOVERAIN Verification Bundle — Versioning Framework

This document defines the official versioning policy for all releases of the
SOVERAIN Verification Bundle. It establishes naming conventions, release
criteria, version increments, and archival requirements to ensure consistent,
auditable, and machine-verifiable evolution of the bundle across all future
versions.

---

## 1. Version Format

All versions must follow the Crown-Standard semantic format:

MAJOR.MINOR.PATCH

Where:
- MAJOR — structural or protocol-level changes  
- MINOR — additions or improvements that do not break structure  
- PATCH — checksum updates, metadata corrections, or documentation fixes  

Examples:
- 1.0.0 — initial full release  
- 1.1.0 — new metadata fields added  
- 1.1.1 — checksum refresh or documentation correction  

---

## 2. Versioning Rules

### 2.1 MAJOR Version Increments
A MAJOR version increment occurs when:
- the repository structure changes  
- required files are added or removed  
- protocol requirements change  
- verification logic changes  
- ENS linkage requirements change  

MAJOR changes must be accompanied by:
- updated manifest  
- updated protocol document  
- updated repository index  
- updated release notes  

### 2.2 MINOR Version Increments
A MINOR version increment occurs when:
- new optional files are added  
- metadata fields are expanded  
- documentation is enhanced  
- QR metadata is extended  
- ENS text-record recommendations are updated  

MINOR changes must not break:
- existing verification logic  
- existing file paths  
- existing ENS linkage  

### 2.3 PATCH Version Increments
A PATCH version increment occurs when:
- checksums are updated  
- typos or formatting issues are corrected  
- non-breaking documentation fixes are made  
- metadata timestamps are refreshed  

PATCH changes must not alter:
- structure  
- required fields  
- verification logic  

---

## 3. Release Requirements

Each release must include:
- updated version number in sovereign-identity.json  
- updated version number in manifest.json  
- updated version number in release notes  
- updated version number in the README  

A release is not valid until:
- all checksums are regenerated  
- all documentation references match the new version  
- the release notes file is created or updated  

---

## 4. Archival Requirements

Each version must be archived in the following ways:

### 4.1 GitHub Tag
Every release must be tagged using:

vMAJOR.MINOR.PATCH

Example:
v1.0.0

### 4.2 Release Notes
Each version must have a corresponding file:

docs/release-notes-vMAJOR.MINOR.PATCH.md

### 4.3 Immutable History
Past versions must never be altered.  
Corrections must be issued as PATCH releases.

---

## 5. ENS Versioning Requirements

ENS text records must always reflect the **current MAJOR.MINOR version**.

Required fields:
- url  
- com.github  
- verification-anchor  

ENS records must not include PATCH numbers.

Example:
verification-anchor = SOVERAIN Verification Bundle — Version 1.1

---

## 6. QR Metadata Versioning

qr/qr-metadata.json must include:
- bundle-version  
- issuance-date  

The version must match the MAJOR.MINOR.PATCH release.

---

## 7. Verification Layer Versioning

### 7.1 manifest.json
Must include:
- bundle-version  
- list of files for the current version  

### 7.2 checksums.json
Must be regenerated for every release.

### 7.3 pointer.json
Only changes when:
- ENS domain changes  
- repository root changes  

---

## 8. Documentation Versioning

All documentation files must reflect the current version where applicable.

Required updates:
- protocol document  
- repository index  
- finalization summary  
- audit checklist  
- audit execution script  

---

## 9. Version Approval Process

A version is considered approved when:
1. All required files are updated  
2. All checksums match  
3. ENS text records are correct  
4. Release notes are published  
5. GitHub tag is created  
6. Auditor signs off using the Auditor’s Log  

Only after these steps is the version considered **Crown‑Standard Final**.

---

## 10. Version Lifecycle

Each version progresses through the following states:

- Draft  
- Ready for Audit  
- Audit Passed  
- Released  
- Archived  

A version may never regress to a previous state.

---

# END OF VERSIONING POLICY DOCUMENT
