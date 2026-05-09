# soc-analyst-lab-project
SOC Level 1 project with attack simulation and SIEM detection

## 📄 Main Report

👉 Start here:  
[📄 SOC L1 Project Report](./soc_l1_project_report.pdf)

<svg width="680" viewBox="0 0 680 920" xmlns="http://www.w3.org/2000/svg" font-family="'Segoe UI', Arial, sans-serif">
  <title>Multi-stage attack diagram</title>
  <desc>Discovery → Persistence → Credential Access → Lateral Movement</desc>
  <defs>
    <marker id="arrow" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M2 1L8 5L2 9" fill="none" stroke="context-stroke" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
    </marker>
  </defs>
 
  <!-- Background -->
  <rect width="680" height="920" fill="#ffffff"/>
 
  <!-- ── PHASE LABELS ── -->
  <rect x="12" y="40" width="108" height="36" rx="8" fill="#1D9E75" stroke="#0F6E56" stroke-width="0.5"/>
  <text font-size="13" font-weight="600" fill="#E1F5EE" x="66" y="63" text-anchor="middle">Discovery</text>
  <text font-size="11" fill="#5F5E5A" x="66" y="84" text-anchor="middle">TA0007</text>
 
  <rect x="12" y="270" width="108" height="36" rx="8" fill="#BA7517" stroke="#854F0B" stroke-width="0.5"/>
  <text font-size="13" font-weight="600" fill="#FAEEDA" x="66" y="293" text-anchor="middle">Persistence</text>
  <text font-size="11" fill="#5F5E5A" x="66" y="314" text-anchor="middle">TA0003</text>
 
  <rect x="12" y="510" width="108" height="36" rx="8" fill="#993C1D" stroke="#712B13" stroke-width="0.5"/>
  <text font-size="13" font-weight="600" fill="#FAECE7" x="66" y="528" text-anchor="middle">Credential</text>
  <rect x="12" y="550" width="108" height="24" rx="8" fill="#993C1D" stroke="#712B13" stroke-width="0.5"/>
  <text font-size="13" font-weight="600" fill="#FAECE7" x="66" y="567" text-anchor="middle">Access</text>
  <text font-size="11" fill="#5F5E5A" x="66" y="586" text-anchor="middle">TA0006</text>
 
  <rect x="12" y="740" width="108" height="36" rx="8" fill="#534AB7" stroke="#3C3489" stroke-width="0.5"/>
  <text font-size="13" font-weight="600" fill="#EEEDFE" x="66" y="763" text-anchor="middle">Lateral</text>
  <rect x="12" y="780" width="108" height="24" rx="8" fill="#534AB7" stroke="#3C3489" stroke-width="0.5"/>
  <text font-size="13" font-weight="600" fill="#EEEDFE" x="66" y="797" text-anchor="middle">Movement</text>
  <text font-size="11" fill="#5F5E5A" x="66" y="816" text-anchor="middle">TA0008</text>
 
  <!-- Timeline line -->
  <line x1="145" y1="60" x2="145" y2="870" stroke="#B4B2A9" stroke-width="1" stroke-dasharray="4 4"/>
 
  <!-- ════════════════
       PHASE 1 — DISCOVERY
  ════════════════ -->
  <rect x="158" y="30" width="500" height="44" rx="8" fill="#9FE1CB" stroke="#0F6E56" stroke-width="0.5"/>
  <text font-size="13" font-weight="600" fill="#04342C" x="408" y="50" text-anchor="middle">Apr 20 · 01:12–01:13 · User: oolai · Host: asd</text>
  <text font-size="11" fill="#085041" x="408" y="66" text-anchor="middle">Enumeration sequence within 33 seconds</text>
 
  <rect x="158" y="92" width="112" height="52" rx="6" fill="#E1F5EE" stroke="#0F6E56" stroke-width="0.5"/>
  <text font-size="13" font-weight="600" fill="#085041" x="214" y="113" text-anchor="middle">whoami.exe</text>
  <text font-size="11" fill="#0F6E56" x="214" y="131" text-anchor="middle">Identifies user</text>
 
  <rect x="284" y="92" width="112" height="52" rx="6" fill="#E1F5EE" stroke="#0F6E56" stroke-width="0.5"/>
  <text font-size="13" font-weight="600" fill="#085041" x="340" y="113" text-anchor="middle">hostname.exe</text>
  <text font-size="11" fill="#0F6E56" x="340" y="131" text-anchor="middle">Identifies host</text>
 
  <rect x="410" y="92" width="112" height="52" rx="6" fill="#E1F5EE" stroke="#0F6E56" stroke-width="0.5"/>
  <text font-size="13" font-weight="600" fill="#085041" x="466" y="113" text-anchor="middle">tasklist.exe</text>
  <text font-size="11" fill="#0F6E56" x="466" y="131" text-anchor="middle">Lists processes</text>
 
  <rect x="536" y="92" width="122" height="52" rx="6" fill="#E1F5EE" stroke="#0F6E56" stroke-width="0.5"/>
  <text font-size="13" font-weight="600" fill="#085041" x="597" y="113" text-anchor="middle">systeminfo.exe</text>
  <text font-size="11" fill="#0F6E56" x="597" y="131" text-anchor="middle">System details</text>
 
  <text font-size="11" fill="#888780" x="214" y="160" text-anchor="middle">T1033</text>
  <text font-size="11" fill="#888780" x="340" y="160" text-anchor="middle">T1033</text>
  <text font-size="11" fill="#888780" x="466" y="160" text-anchor="middle">T1057</text>
  <text font-size="11" fill="#888780" x="597" y="160" text-anchor="middle">T1082</text>
 
  <rect x="158" y="172" width="500" height="28" rx="6" fill="none" stroke="#B4B2A9" stroke-width="0.5" stroke-dasharray="4 3"/>
  <text font-size="11" fill="#5F5E5A" x="170" y="190">Rule: process.name: ("whoami.exe" OR "hostname.exe" OR "tasklist.exe" OR "systeminfo.exe")</text>
 
  <line x1="408" y1="202" x2="408" y2="238" stroke="#888780" stroke-width="1.5" marker-end="url(#arrow)"/>
  <text font-size="11" fill="#5F5E5A" x="415" y="225">suspicious when executed in sequence</text>
 
  <!-- ════════════════
       PHASE 2 — PERSISTENCE
  ════════════════ -->
  <rect x="158" y="240" width="500" height="44" rx="8" fill="#FAC775" stroke="#854F0B" stroke-width="0.5"/>
  <text font-size="13" font-weight="600" fill="#412402" x="408" y="260" text-anchor="middle">Apr 23 · 22:02:15 · User: ASD\oolai</text>
  <text font-size="11" fill="#633806" x="408" y="276" text-anchor="middle">Registry modification via powershell.exe → reg.exe</text>
 
  <rect x="158" y="302" width="140" height="56" rx="6" fill="#FAEEDA" stroke="#854F0B" stroke-width="0.5"/>
  <text font-size="13" font-weight="600" fill="#412402" x="228" y="322" text-anchor="middle">powershell.exe</text>
  <text font-size="11" fill="#633806" x="228" y="340" text-anchor="middle">Parent process</text>
 
  <line x1="298" y1="330" x2="328" y2="330" stroke="#888780" stroke-width="1.5" marker-end="url(#arrow)"/>
 
  <rect x="330" y="302" width="110" height="56" rx="6" fill="#FAEEDA" stroke="#854F0B" stroke-width="0.5"/>
  <text font-size="13" font-weight="600" fill="#412402" x="385" y="322" text-anchor="middle">reg.exe</text>
  <text font-size="11" fill="#633806" x="385" y="340" text-anchor="middle">Writes Run key</text>
 
  <line x1="440" y1="330" x2="468" y2="330" stroke="#888780" stroke-width="1.5" marker-end="url(#arrow)"/>
 
  <rect x="470" y="302" width="188" height="56" rx="6" fill="#F1EFE8" stroke="#5F5E5A" stroke-width="0.5"/>
  <text font-size="13" font-weight="600" fill="#2C2C2A" x="564" y="318" text-anchor="middle">HKCU\...\Run</text>
  <text font-size="11" fill="#444441" x="564" y="336" text-anchor="middle">cmd.exe /c whoami</text>
  <text font-size="11" fill="#444441" x="564" y="350" text-anchor="middle">Runs at user login</text>
 
  <text font-size="11" fill="#888780" x="385" y="372" text-anchor="middle">T1547.001 – Registry Run Keys / Startup Folder</text>
  <rect x="158" y="382" width="500" height="28" rx="6" fill="none" stroke="#B4B2A9" stroke-width="0.5" stroke-dasharray="4 3"/>
  <text font-size="11" fill="#5F5E5A" x="170" y="400">Rule: process.name:"reg.exe" AND command_line:"Run" AND ("cmd.exe" OR "powershell.exe")</text>
 
  <line x1="408" y1="412" x2="408" y2="448" stroke="#888780" stroke-width="1.5" marker-end="url(#arrow)"/>
  <text font-size="11" fill="#5F5E5A" x="415" y="435">risk level escalated</text>
 
  <!-- ════════════════
       PHASE 3 — CREDENTIAL ACCESS
  ════════════════ -->
  <rect x="158" y="450" width="500" height="44" rx="8" fill="#F5C4B3" stroke="#712B13" stroke-width="0.5"/>
  <text font-size="13" font-weight="600" fill="#4A1B0C" x="408" y="470" text-anchor="middle">Apr 23 · 23:34:12 · User: oolai · Host: asd</text>
  <text font-size="11" fill="#712B13" x="408" y="486" text-anchor="middle">LotL — legitimate binary used to access Credential Manager</text>
 
  <rect x="158" y="512" width="148" height="56" rx="6" fill="#FAECE7" stroke="#712B13" stroke-width="0.5"/>
  <text font-size="13" font-weight="600" fill="#4A1B0C" x="232" y="532" text-anchor="middle">rundll32.exe</text>
  <text font-size="11" fill="#712B13" x="232" y="550" text-anchor="middle">Legitimate binary</text>
 
  <line x1="306" y1="540" x2="334" y2="540" stroke="#888780" stroke-width="1.5" marker-end="url(#arrow)"/>
 
  <rect x="336" y="512" width="148" height="56" rx="6" fill="#FAECE7" stroke="#712B13" stroke-width="0.5"/>
  <text font-size="13" font-weight="600" fill="#4A1B0C" x="410" y="532" text-anchor="middle">keymgr.dll</text>
  <text font-size="11" fill="#712B13" x="410" y="550" text-anchor="middle">KRShowKeyMgr</text>
 
  <line x1="484" y1="540" x2="510" y2="540" stroke="#888780" stroke-width="1.5" marker-end="url(#arrow)"/>
 
  <rect x="512" y="512" width="146" height="56" rx="6" fill="#F1EFE8" stroke="#5F5E5A" stroke-width="0.5"/>
  <text font-size="13" font-weight="600" fill="#2C2C2A" x="585" y="530" text-anchor="middle">Windows</text>
  <text font-size="13" font-weight="600" fill="#2C2C2A" x="585" y="546" text-anchor="middle">Credential Mgr</text>
  <text font-size="11" fill="#444441" x="585" y="562" text-anchor="middle">Credentials exposed</text>
 
  <text font-size="11" fill="#888780" x="408" y="582" text-anchor="middle">T1555 – Credentials from Password Stores</text>
  <rect x="158" y="592" width="500" height="28" rx="6" fill="none" stroke="#B4B2A9" stroke-width="0.5" stroke-dasharray="4 3"/>
  <text font-size="11" fill="#5F5E5A" x="170" y="610">Rule: process.name:"rundll32.exe" AND command_line:"keymgr.dll" AND "KRShowKeyMgr"</text>
 
  <text font-size="11" fill="#5F5E5A" x="408" y="636" text-anchor="middle">↗ Correlated with Persistence phase → multi-stage attack confirmed</text>
 
  <line x1="408" y1="648" x2="408" y2="686" stroke="#888780" stroke-width="1.5" marker-end="url(#arrow)"/>
  <text font-size="11" fill="#5F5E5A" x="415" y="672">possible privilege escalation / data exposure</text>
 
  <!-- ════════════════
       PHASE 4 — LATERAL MOVEMENT
  ════════════════ -->
  <rect x="158" y="688" width="500" height="44" rx="8" fill="#CECBF6" stroke="#3C3489" stroke-width="0.5"/>
  <text font-size="13" font-weight="600" fill="#26215C" x="408" y="708" text-anchor="middle">Apr 19 · 19:02:58 · LotL via WMI service</text>
  <text font-size="11" fill="#3C3489" x="408" y="724" text-anchor="middle">Remote execution chain completed in ~500 ms</text>
 
  <rect x="158" y="750" width="136" height="56" rx="6" fill="#EEEDFE" stroke="#3C3489" stroke-width="0.5"/>
  <text font-size="13" font-weight="600" fill="#26215C" x="226" y="770" text-anchor="middle">WMIC.exe</text>
  <text font-size="11" fill="#3C3489" x="226" y="788" text-anchor="middle">process call create</text>
 
  <line x1="294" y1="778" x2="322" y2="778" stroke="#888780" stroke-width="1.5" marker-end="url(#arrow)"/>
 
  <rect x="324" y="750" width="136" height="56" rx="6" fill="#EEEDFE" stroke="#3C3489" stroke-width="0.5"/>
  <text font-size="13" font-weight="600" fill="#26215C" x="392" y="770" text-anchor="middle">cmd.exe</text>
  <text font-size="11" fill="#3C3489" x="392" y="788" text-anchor="middle">Spawned by WMI</text>
 
  <line x1="460" y1="778" x2="488" y2="778" stroke="#888780" stroke-width="1.5" marker-end="url(#arrow)"/>
 
  <rect x="490" y="750" width="168" height="56" rx="6" fill="#EEEDFE" stroke="#3C3489" stroke-width="0.5"/>
  <text font-size="13" font-weight="600" fill="#26215C" x="574" y="768" text-anchor="middle">whoami.exe</text>
  <text font-size="11" fill="#3C3489" x="574" y="784" text-anchor="middle">Confirms successful</text>
  <text font-size="11" fill="#3C3489" x="574" y="798" text-anchor="middle">remote execution</text>
 
  <text font-size="11" fill="#888780" x="408" y="822" text-anchor="middle">T1047 – Windows Management Instrumentation</text>
  <rect x="158" y="832" width="500" height="28" rx="6" fill="none" stroke="#B4B2A9" stroke-width="0.5" stroke-dasharray="4 3"/>
  <text font-size="11" fill="#5F5E5A" x="170" y="850">Rule: WMIC.exe AND "process call create" AND "cmd.exe" → cmd.exe → whoami.exe</text>
 
  <!-- Severity badge -->
  <rect x="158" y="872" width="500" height="34" rx="8" fill="#E24B4A" stroke="#A32D2D" stroke-width="0.5"/>
  <text font-size="12" font-weight="600" fill="#FCEBEB" x="408" y="893" text-anchor="middle">Severity: HIGH · True Positive · Isolate host · Reset credentials · Investigate lateral movement</text>
</svg>

---

## 📌 Overview

This project demonstrates practical SOC Level 1 skills through the simulation and investigation of multiple attack techniques using Elastic SIEM.

Although executed in a controlled lab environment, the activities were correlated to simulate a realistic multi-stage attack scenario.

---

## ⚔️ Attack Simulation

The following attack techniques were simulated and analyzed:

- Discovery (TA0007)
- Persistence (T1547.001)
- Credential Access (T1555)
- Lateral Movement (T1047)

---

## 🧠 Analyst Approach

The project focuses on:

- Log analysis and event correlation
- Detection logic development
- Investigation of suspicious behavior
- Mapping to MITRE ATT&CK framework

---

## 🚨 Detection & Response

During the analysis:

- Suspicious activity was identified and classified
- Detection rules were created and validated
- Events were correlated to simulate a multi-stage attack
- Response actions were defined based on observed behavior

---

## 🖥️ Environment

- Windows VM (Target)
- Ubuntu (Elastic SIEM)
- PowerShell

---

## 👤 Author

Davi Mauricio Santos Reis





