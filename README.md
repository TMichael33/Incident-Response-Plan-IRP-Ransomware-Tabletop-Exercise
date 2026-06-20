# Project 6: Incident Response Plan (IRP) & Ransomware Tabletop Exercise (TTX)

## Executive Summary
When an enterprise is targeted by an advanced cyberattack, technical defenses must be matched by a coordinated operational response. This project features a comprehensive **Incident Response Plan ** baseline structured around the **NIST SP 800-61 Rev. 2** lifecycle. 

To validate the viability of the plan, this project documents the execution and key findings of a simulated **Ransomware Tabletop Exercise** conducted for a mock defense contractor infrastructure ("Titan Aerospace"). The simulation tested cross-functional coordination, mandatory defense reporting timelines, and technical containment playbooks under stress.

---

## Incident Response Lifecycle (NIST SP 800-61 Rev. 2)
The organization's incident mitigation framework mandates a strict six-phase response pipeline to structure operations during an active anomaly:
1. **Preparation:** Establishing incident response kits, multi-factor authentication baselines, offline backups, and continuous employee training.
2. **Detection & Analysis:** Identifying alerts via SIEM pipelines, verifying indicators of compromise (IOCs), and determining incident scope.
3. **Containment:** Applying automated endpoint isolation (EDR) and network segmentation to limit adversary lateral movement.
4. **Eradication:** Safely removing malicious binaries, resetting compromised administrative credentials, and scanning file structures.
5. **Recovery:** Restoring critical corporate systems from verified immutable cloud backups and verifying system integrity.
6. **Post-Incident Activity:** Documenting lessons learned, calculating full business impact, and updating playbooks to stop repeat exploits.

---

## Tabletop Exercise Timeline & Analysis Matrix

Below is an extract of the multi-phase timeline executed during the simulated ransomware deployment scenario.

<table width="100%">
  <thead>
    <tr>
      <th width="12%">Scenario Phase</th>
      <th width="28%">Injected Threat Event / Prompt</th>
      <th width="30%">Tested Internal Control / Playbook Activity</th>
      <th width="18%">Responsible Functions</th>
      <th width="12%">Target SLA / Status</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>Phase 1:<br>Detection</b></td>
      <td>EDR logs register a high-volume credential dumping attempt on an engineering workstation, followed immediately by localized file encryption.</td>
      <td>• SOC analysts verify automated EDR warning metrics.<br>• Incident Commander declares an official P1 Critical Security Incident.</td>
      <td>• Security Operations (SOC)<br>• Incident Commander</td>
      <td>• Target: &lt; 30 Mins<br>• <span style="color:green;"><b>Met (22 Mins)</b></span></td>
    </tr>
    <tr>
      <td><b>Phase 2:<br>Containment</b></td>
      <td>The ransomware attempts to move laterally across internal networks to compromise active corporate directory backup volumes.</td>
      <td>• Enforce immediate host network isolation protocols via centralized EDR.<br>• Network administrators block all lateral SMB traffic between production segments.</td>
      <td>• Infrastructure Team<br>• Network Security</td>
      <td>• Target: &lt; 1 Hour<br>• <span style="color:green;"><b>Met (45 Mins)</b></span></td>
    </tr>
    <tr>
      <td><b>Phase 3:<br>Regulatory</b></td>
      <td>Forensic analysis confirms the adversary successfully accessed a segmented database hosting Controlled Unclassified Information (CUI).</td>
      <td>• Legal counsel evaluates mandatory disclosure obligations.<br>• Security compliance initiates formal incident reporting to the Department of Defense (DoD).</td>
      <td>• Legal Counsel<br>• GRC Analyst</td>
      <td>• <b>DoD 72-Hour Rule</b><br>• <span style="color:green;"><b>Met (18 Hours)</b></span></td>
    </tr>
    <tr>
      <td><b>Phase 4:<br>Recovery</b></td>
      <td>The threat actor leaves a ransom demand requesting $1.5M BTC for decryption keys. Local servers are entirely locked out.</td>
      <td>• Executive leadership denies ransom payment request.<br>• IT operations initiates complete bare-metal restoration from isolated, immutable cloud storage.</td>
      <td>• Executive Team<br>• IT Operations</td>
      <td>• Target: &lt; 24 Hours<br>• <span style="color:orange;"><b>Delayed (31 Hours)</b></span></td>
    </tr>
  </tbody>
</table>

---

## Critical Findings & POA&M Action Items
While the tabletop exercise confirmed that corporate communication lines functioned well, it highlighted two critical gaps that were immediately deferred to the corporate **Plan of Action and Milestones (POA&M)** for remediation:

1. **Backup Restoration Bottle-neck (Phase 4 Deficiency):** The exercise revealed that while cloud backup data was fully immutable and uncompromised, the bandwidth allocated for full bare-metal restorations exceeded our operational Recovery Time Objective (RTO) by 7 hours.
   * **Remediation Plan:** Provision high-speed local NAS backup arrays to house redundant local copies of critical system baselines, reducing restoration time down to under 4 hours.
2. **Delayed Escalation Workflows:** Non-technical shift supervisors on the factory production floor lacked awareness regarding the initial symptoms of system compromises, causing an 11-minute delay before IT received an alert.
   * **Remediation Plan:** Develop and deliver mandatory, targeted 15-minute training sessions focusing specifically on ransomware identification for all plant operations personnel.

---

## Key Insights & Business Alignment
1. **The Regulatory Reality of Reporting:** In the defense industrial base, reporting an incident isn't a voluntary business decision. Under federal guidelines, contractors handling sensitive information must report a verified cyber breach to the DoD within 72 hours. Failing to run regular tabletop exercises to practice this process creates an existential liability for the company's contracts.
2. **True Crisis Preparation is Cross-Functional:** A cyber incident is not just an "IT problem." A successful containment operation requires immediate synchronization among the technical security analysts (who cut network lines), general legal counsel (who manage data breach notification laws), and executive leaders (who authorize continuity operations).
3. **Tabletops Expose Operational Fiction:** Policies written on paper often collapse during an actual attack. Running a simulated exercise forces teams to test the realistic boundaries of their systems, shifting the organization from a passive compliance mindset to an active state of operational resilience.
