# Space Coast Cyber Tech — Interactive Sign-In Practice Scenario

## Purpose

This dataset is an **investigator-focused Microsoft 365 interactive sign-in scenario** built for tool validation, testing and training.

## Dataset Summary

- **Organization:** Space Coast Cyber Tech
- **Tenant domain:** `spacecoastcybertech.com`
- **Log type:** Microsoft 365 / Entra ID interactive sign-in style CSV
- **Rows:** 3,708
- **Unique users:** 40
- **Time range (UTC):** 2026-03-16 11:11:00 through 2026-03-24 09:58:15
- **CSV SHA-256:** `C2DBF002887B20372175890B00BC6490CAABC73725EB34B84EEDD30309DEC4D9`

## Training Objective

This scenario is meant to help investigators practice:

1. Distinguishing malicious activity from normal background sign-in noise
2. Validating whether detections fire when malicious events are properly bursty and correlated
3. Confirming that kill chain mapping lights up the expected stages
4. Practicing scoping and narrative reconstruction for account compromise / BEC-style intrusion activity

---

## What Happened — Scenario Narrative

### Phase 1 — Normal Baseline Activity

From **2026-03-16** through **2026-03-20**, the tenant shows normal employee activity from Florida-based infrastructure. Users authenticate to common Microsoft 365 services such as:

- Office 365
- Azure Portal
- Microsoft Teams
- SharePoint Online
- Exchange Online

This baseline is intentionally dense so that "new" detections have prior history to compare against.

### Phase 2 — Reconnaissance / Password Spray

On **2026-03-21 around 11:00 UTC**, attacker-controlled infrastructure begins a coordinated password spray campaign against multiple `spacecoastcybertech.com` accounts.

This portion is intended to trigger:

- `PasswordSpray`
- `Distributed_Spray_Targeted_User`

### Phase 3 — Targeted Brute Force / Credential Validation

Shortly after the spray, one targeted account experiences repeated failures from the **same IP** within a short time window, followed by a successful sign-in. Multiple distinct error codes and reasons are present before the success.

This portion is intended to trigger:

- `BruteForce_Targeted`
- `Success_After_Failures_Same_IP`
- `Failure_Progression_To_Success`

### Phase 4 — MFA Fatigue

A separate user is subjected to repeated MFA denials / interruptions over a short period and then eventually shows a successful sign-in.

This portion is intended to trigger:

- `MFA_Fatigue`

### Phase 5 — Legacy Authentication Abuse

The attacker also attempts mailbox access and credential spray through legacy-auth pathways such as:

- SMTP
- IMAP
- POP
- EWS
- ActiveSync
- MAPI

One user successfully authenticates and then shows legacy-auth activity afterward, which is consistent with mailbox access attempts after a foothold is established.

This portion is intended to trigger:

- `LegacyAuth_Risk`
- `LegacyAuth_SMTP_Spray`
- `LegacyAuth_Abuse`
- `LegacyAuth_After_Success`

### Phase 6 — OAuth Device Code Phishing

One account shows activity associated with Microsoft device login / OAuth device code flow. This simulates a device-code phishing style access path.

This portion is intended to trigger:

- `OAuth_Device_Code_Phishing`

### Phase 7 — BAV2ROPC Activity

The dataset also includes sign-ins using a BAV2ROPC-style user agent, including both failed spray-like behavior and a successful authentication attempt.

This portion is intended to trigger:

- `BAV2ROPC_Failure_Campaign`
- `BAV2ROPC_Authentication_Attempt`

### Phase 8 — Token Reuse / Broker Abuse

The scenario includes:

- the same token/session context used from multiple IPs / countries
- broker-related authentication activity from multiple IPs and countries

This portion is intended to trigger:

- `Refresh_Token_Replay`
- `Token_Broker_Abuse`

### Phase 9 — Access Established / Post-Compromise Expansion

After initial access, the attacker signs in from **new IPs**, **new ASNs**, **new countries**, and **new client/app patterns**, including rapid movement between distant geographies. Some of this activity occurs during off-hours.

This portion is intended to trigger:

- `Improbable_Travel`
- `New_IP_For_User`
- `New_Country_For_User`
- `New_ASN_For_User`
- `New_ClientApp_For_User`
- `New_UserAgent_For_User`
- `OffHours_Success`

---

## Expected Kill Chain Coverage

This dataset should light up the following kill chain stages at least once:

### Recon
- `PasswordSpray`
- `LegacyAuth_SMTP_Spray`
- `LegacyAuth_Abuse`

### Initial Access
- `BruteForce_Targeted`
- `Distributed_Spray_Targeted_User`
- `BAV2ROPC_Failure_Campaign`
- `BAV2ROPC_Authentication_Attempt`

### Credential Attack
- `Success_After_Failures_Same_IP`
- `Failure_Progression_To_Success`
- `LegacyAuth_After_Success`

### MFA Bypass
- `MFA_Fatigue`
- `OAuth_Device_Code_Phishing`

### Access Established
- `Improbable_Travel`
- `New_IP_For_User`
- `New_Country_For_User`
- `New_ASN_For_User`
- `New_ClientApp_For_User`
- `New_UserAgent_For_User`
- `Refresh_Token_Replay`
- `Token_Broker_Abuse`
- `LegacyAuth_Risk`

---


## Suggested Validation Workflow

1. Load the CSV into the Interactive Sign-In Analyzer
2. Confirm the header shows:
   - file metadata
   - time range
   - SHA-256
3. Review **Detections**
4. Review **Kill Chain**
5. Confirm the expected stages light up
6. Export:
   - checked detections
   - timeline narrative
   - HTML / PDF reports
7. Compare the app output to this scenario document

---

## Suggested Investigation Questions

Use this scenario to answer questions such as:

- Which users were first targeted in the spray phase?
- Which account shows the strongest evidence of same-IP brute force followed by success?
- Which users show foreign sign-ins after baseline domestic activity?
- Which events suggest mailbox-oriented legacy-auth abuse?
- Which sign-ins suggest token reuse or replay rather than ordinary credential entry?
- Which detections best support an account-compromise / BEC narrative?

---

## Files Included

- `spacecoastcybertech_interactive_practice_scenario.csv`
- `spacecoastcybertech_interactive_practice_scenario.md`