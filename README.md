**Alert IQ – Intelligent SOC Alert Prioritization and False Positive Reduction**

Project Overview

Alert IQ is a Splunk-based Security Operations Center (SOC) project designed to prioritize security alerts and reduce known false-positive noise using rule-based filtering and risk scoring.

The project simulates authentication security events, detects suspicious login activities, identifies potential brute-force attacks, filters approved benign sources, and assigns risk-based severity levels to alerts.

**Objectives**

Monitor authentication events using Splunk.

Detect repeated failed login attempts.

Identify potential brute-force attacks.

Correlate authentication activities by source IP.

Reduce known benign and repetitive alert noise.

Calculate risk scores based on suspicious activity.

Prioritize alerts based on severity.

Display security information through a Splunk dashboard.

**Technology Stack**

Splunk Enterprise

Splunk Search Processing Language (SPL)

Linux Fedora

JSON security event logs

CSV lookup tables

Git and GitHub

**Architecture**

Generate simulated authentication events.

Collect JSON logs using Splunk file monitoring.

Store events in the alert_iq index.

Detect failed authentication and brute-force patterns.

Correlate events and calculate risk scores.

Apply known-benign source filtering.

Categorize alerts into Critical, High, Medium and Low.

Display prioritized alerts through a Splunk dashboard.

**Detection Modules**

1. Failed Login Detection

Identifies failed authentication attempts and groups them by source IP and username.

2. Brute-Force Detection

Detects five or more failed authentication attempts from the same source IP against the same username within five minutes.

3. Risk-Based Alert Scoring

Assigns risk points based on authentication failures and suspicious login sequences.

4. False-Positive Reduction

Uses an approved benign IP lookup table to classify known testing activity separately from actionable alerts.

5. Alert Prioritization

Combines detection, risk scoring, and benign-source filtering to identify alerts requiring investigation.

**Risk Scoring**

Condition:	                      Score

3–4 failed logins:	               20

5–7 failed logins:	               35

8+ failed logins:	                 50

3+ failures followed by success:	+25

Severity thresholds:

Critical: 70 or above

High: 50–69

Medium: 25–49

Low: Below 25

**Repository Structure**

data/: Simulated authentication events.

lookups/: Known benign IP lookup.

spl/: Splunk SPL detection queries.

config/: Splunk input and field extraction configuration.

screenshots/: Project implementation evidence.

docs/: Architecture, testing and investigation documentation.

**Testing Scenarios**

Normal successful authentication.

Repeated failed authentication.

Potential brute-force activity.

Suspicious failed-login followed by successful authentication.

Approved benign testing activity.

Unknown source requiring investigation.

**Expected Outcomes**

Identification of repeated failed logins.

Detection of potential brute-force activity.

Risk-based alert prioritization.

Classification of known benign events.

Improved visibility into actionable SOC alerts.


**Limitations**

This is a beginner-level, rule-based SOC project using simulated authentication events. It does not use a trained AI or machine-learning model. Risk scores and benign-source exceptions are illustrative and require environment-specific tuning before production use.

**Disclaimer**

This project is developed for educational and cybersecurity portfolio purposes. All included security events and IP addresses are simulated examples. No unauthorized systems are accessed or attacked.

Author

Usha

Created as a hands-on SOC Analyst portfolio project using Splunk.
