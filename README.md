# Google Chrome Zero-Day — Web Security Track

**Learn, practice, and defend — ethically.**  
This repository contains course materials and labs for the *Web Security* module . Use only in controlled, legal environments (VMs, lab networks) and follow the Responsible Disclosure & Code of Conduct below.

---

## Table of contents
- Overview
- Learning outcomes
- Case study summary
- Course modules & syllabus
- Lab exercises (safe / controlled)
- Lab environment setup
- Mitigations & detection guidance
- Responsible disclosure & ethics
- Contributing
- References
- License

---

## Overview
This repo supports an offensive-security training track that teaches web vulnerability analysis, exploitation fundamentals, and defensive detection using a real-world case-study approach. Emphasis is on **ethical learning**, reproducible lab setups, and actionable mitigation/detection techniques.

---

## Learning outcomes
By completing this module you will be able to:
- Explain V8 engine basics and how type-confusion bugs arise.
- Analyze a real-world browser vulnerability at a high level.
- Reproduce safe, non-destructive demos in isolated lab VMs.
- Implement mitigation steps and detection signatures for enterprise environments.
- Follow responsible disclosure and incident response best practices.

---

## Case study (summary)
This course uses a browser engine vulnerability as a teaching case. Materials focus on investigation, crash triage, and defensive countermeasures. **No weaponized exploit code is included.** All exercises are designed to be non-destructive and contained within lab VMs.

---

## Course modules & syllabus (high level)
1. Intro to browser engines & V8 internals  
2. Type confusion: theory & safe examples  
3. Case study walkthrough (high level analysis)  
4. Safe lab: controlled memory-behavior demos  
5. Crash analysis & triage  
6. Hunting & detection (EDR / SIEM rules)  
7. Mitigation, patch management, and hardening  
8. Responsible disclosure & ethics

---

## Lab exercises (safe)
Each lab MUST be run on isolated, snapshot-based VM environments. Example labs:
- V8 object layout inspection (debug builds, instrumentation)
- Controlled type-confusion demonstration (instrumentation only, non-exploit)
- Crash analysis and symbolized triage
- Detection rule authoring (YARA/EDR/SIEM samples)

**Do not** run exploits or PoCs that attempt remote code execution on production or third-party systems.

---

## Lab environment setup (recommended minimal)
- Host with virtualization (VirtualBox/VMware/KVM)
- Victim VM: Windows 10/11 or Linux with Chrome/Chromium debug symbols
- Attacker VM: Kali/Ubuntu (analysis tools)
- Instrumentation VM (optional): symbol server, debug tooling
- Tools: Chrome debug builds, WinDbg/gdb, procmon, symbol packages, Node/V8 tools, ELK or SIEM for logging

Snapshot before each exercise.

---

## Mitigations & detection (practical)
- **Patch promptly**: apply vendor updates as soon as they are available.
- **Enable site and process isolation** in browsers.
- **Use content-filtering** and JS execution policies for untrusted content.
- **EDR/SIEM rules**: alert on repeated renderer crashes with similar stacks, anomalous JS payload patterns, unusual post-visit behaviors.
- **Monitor network**: watch browser-originated outbound connections to suspicious domains.

---

## Responsible disclosure & ethics
- Always obtain authorization before testing systems.
- Use isolated lab networks for research.
- If you discover a vulnerability, follow a responsible disclosure process (vendor security teams, coordinated disclosure).
- Do **not** publish weaponized exploit code.

---

## Contributing
Contributions welcome (labs, defensive rules, detection content, documentation). Rules:
- No public exploit PoCs that enable RCE.
- Submissions limited to benign demos, defensive content, lab instructions, slides and writeups.
- Open a PR with reproducible steps and lab environment details.

---

## Repository layout (suggested)
```
/slides/         # lecture slides and pptx
/labs/           # lab guides and scripts (non-exploit)
/detection/      # YARA, Sigma, EDR rules, SIEM dashboards
/references/     # vendor advisories, CVEs, reports
/legal/          # code of conduct, responsible disclosure templates
```

---

## Quick start (examples)
```bash
# Save this repo folder to your workstation, run labs in isolated VMs.
# Take snapshots before each lab.

# Example: open a crash dump in WinDbg (Windows)
windbg -z C:\dumps\chrome_renderer.dmp
```

---

## License
MIT License — educational use only. See `LICENSE` file for details.

---

*Prepared by: Nihal MP — Offenso Hackers Academy*
