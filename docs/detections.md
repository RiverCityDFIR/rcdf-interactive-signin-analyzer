# Detections

## Overview

The RCDF Interactive Sign-In Analyzer identifies authentication patterns that may warrant additional investigative review.

Detections are intended to assist with triage and investigative prioritization and should not be interpreted as automatic conclusions of compromise.

---

## Detection Categories

The tool may identify activity including:

- Improbable travel
- New country for user
- New ASN for user
- New client application for user
- Legacy authentication activity
- Repeated failures followed by successful authentication
- Suspicious IP or ASN activity
- MFA-related anomalies
- OAuth or device code related activity where applicable
- Token or session-related anomalies where supported

Detection availability may vary by release version and available telemetry.

---

## Severity Levels

Detections may be assigned severity levels including:

- Informational
- Low
- Medium
- High
- Critical

Severity is intended to assist review prioritization and does not replace examiner judgment or case-specific analysis.

---

## Kill Chain Mapping

Where applicable, detections may be associated with identity-focused investigative phases such as:

- Recon
- Credential Attack
- Initial Access
- MFA Bypass
- Access Established

These mappings are intended to assist with investigative context and timeline reconstruction.

---

## NIST and Zero Trust Mapping

Certain detections may include references to:

- NIST security controls
- Zero Trust Architecture concepts
- Identity-focused defensive considerations

These mappings are provided for contextual reference only and should not be interpreted as formal compliance analysis.

---

## False Positives

Legitimate activity may trigger detections under certain circumstances, including:

- Travel
- VPN usage
- Cloud infrastructure usage
- Mobile carrier routing
- Device enrollment
- Administrative testing
- Application onboarding
- Conditional access changes

Investigators should validate findings using available telemetry, user interviews, tenant configuration, and additional evidence sources where appropriate.
