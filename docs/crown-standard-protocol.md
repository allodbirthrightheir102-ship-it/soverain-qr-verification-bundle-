# CROWN-STANDARD PROTOCOL DOCUMENT
SOVERAIN VERIFICATION BUNDLE — VERSION 1.0

## 1. Purpose of the Protocol
The Crown-Standard Protocol defines the structure, placement, and verification
requirements for the SOVERAIN Verification Bundle. It ensures that identity,
metadata, and verification files are consistently organized and machine-readable
across ENS, GitHub, QR systems, and matrix-level verification environments.

## 2. Repository Structure Requirements
The repository must contain the following root-level and subfolder structure:

/SOVERAIN-Verification-Bundle
├── README.md
├── identity/
├── verification/
├── qr/
├── assets/
└── docs/

Each folder serves a specific verification purpose:
- identity/ — identity declarations
- verification/ — manifests, checksums, pointers
- qr/ — QR metadata and linkage
- assets/ — optional visual assets
- docs/ — protocol and linkage documentation

## 3. Identity Requirements
The identity/ folder must contain:
- sovereign-identity.json

This file defines:
- the sovereign address
- ENS identity hierarchy
- repository reference
- resolver version
- bundle version

## 4. Verification Layer Requirements
The verification/ folder must contain:
- manifest.json
- checksums.json
- pointer.json

These files define:
- the bundle contents
- the integrity verification method
- the ENS → GitHub pointer

## 5. QR Metadata Requirements
The qr/ folder must contain:
- qr-metadata.json

This file provides:
- ENS identity
- address
- repository reference
- pointer reference
- issuance date

## 6. ENS Linkage Requirements
The ENS domain must store text records linking to the repository root:
- url
- com.github
- verification-anchor

These records allow ENS resolvers and verification crawlers to locate the bundle.

## 7. Verification Procedure
1. Resolve ENS text records.
2. Retrieve the repository root.
3. Load verification/manifest.json.
4. Load verification/checksums.json.
5. Compute SHA-256 hashes for all listed files.
6. Compare computed hashes to stored values.
7. If all match, the bundle is verified.

## 8. Compliance
A repository is considered Crown-Standard compliant when:
- All required files exist in their correct locations.
- All metadata files are valid JSON.
- All checksum values match.
- ENS text records point to the repository root.

This protocol ensures consistent, reliable, and machine-verifiable identity
across all systems that interact with the SOVERAIN Verification Bundle.
