# Reporting

## Overview

The RCDF Interactive Sign-In Analyzer can generate structured investigative output intended to assist with authentication telemetry review and incident response workflows.

Generated reports are intended to support examiner review and technical documentation processes.

---

## Report Content

Depending on the release version and available telemetry, reports may include:

- Source file information
- File hash information
- Summary metrics
- Flagged users
- Suspicious IP addresses
- Detection summaries
- Timeline reconstruction
- Enrichment details
- NIST and Zero Trust reference mappings

---

## Recommended Use

Generated reports should be reviewed prior to use as final work product.

Investigators should validate findings against:

- Original source logs
- Tenant configuration
- Additional telemetry sources
- Victim or administrator interviews
- Available corroborating evidence

---

## File Hashes

Reports may include file hash information to assist with repeatability and evidence tracking workflows. Opened/closed file hashes are stored in /logs/

Recommended practice includes:

- Preserving original source files
- Recording acquisition details
- Retaining associated hashes
- Maintaining chain-of-custody documentation where required

---

## Timeline Output

Timeline views are intended to assist with reconstruction of authentication activity and investigative sequencing.

Timeline analysis may assist with identifying:

- Initial suspicious activity
- Authentication failure clusters
- Successful authentication after failures
- Geographic changes
- Client application changes
- Suspicious authentication patterns

---

## Limitations

Generated output is dependent on the completeness and accuracy of available telemetry.

Factors that may affect analysis include:

- Missing logs
- Incomplete exports
- Time zone inconsistencies
- Tenant-specific configuration
- Conditional access behavior
- Upstream telemetry limitations

Reports should be treated as analytical aids and not as substitutes for full forensic review.
