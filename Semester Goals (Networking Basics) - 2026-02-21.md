**Student:** David Hadzhiivanov  
**Program / Semester:** Fontys UAS - Networking Basics (Semester 2)  
**Main learning format:** Practical work + end-to-end **case studies** 
**Tools:** **GNS3** 

---

## Table of Contents
    - [[Semester Goals (Networking Basics) - 2026-02-21#Introduction|Introduction]]
- [[Semester Goals (Networking Basics) - 2026-02-21#Goal 1 - Strengthen core networking fundamentals through real case studies|Goal 1 - Strengthen core networking fundamentals through real case studies]]
    - [[Semester Goals (Networking Basics) - 2026-02-21#Goal (measurable / “done” definition)|Goal (measurable / “done” definition)]]
    - [[Semester Goals (Networking Basics) - 2026-02-21#How I will achieve it (plan)|How I will achieve it (plan)]]
    - [[Semester Goals (Networking Basics) - 2026-02-21#End-of-semester reflection (to fill in later)|End-of-semester reflection (to fill in later)]]
- [[Semester Goals (Networking Basics) - 2026-02-21#Goal 2 — Build a complete working network implementation in GNS3 for the case study|Goal 2 — Build a complete working network implementation in GNS3 for the case study]]
    - [[Semester Goals (Networking Basics) - 2026-02-21#Goal (measurable / “done” definition)|Goal (measurable / “done” definition)]]
    - [[Semester Goals (Networking Basics) - 2026-02-21#How I will achieve it (plan)|How I will achieve it (plan)]]
    - [[Semester Goals (Networking Basics) - 2026-02-21#End-of-semester reflection (to fill in later)|End-of-semester reflection (to fill in later)]]
- [[Semester Goals (Networking Basics) - 2026-02-21#Goal 3 — Become faster and more confident with CLI configuration|Goal 3 — Become faster and more confident with CLI configuration]]
    - [[Semester Goals (Networking Basics) - 2026-02-21#Goal (measurable / “done” definition)|Goal (measurable / “done” definition)]]
    - [[Semester Goals (Networking Basics) - 2026-02-21#How I will achieve it (plan)|How I will achieve it (plan)]]
    - [[Semester Goals (Networking Basics) - 2026-02-21#End-of-semester reflection (to fill in later)|End-of-semester reflection (to fill in later)]]
- [[Semester Goals (Networking Basics) - 2026-02-21#Goal 4 — Improve documentation quality (diagrams, IP plans, and configuration notes)|Goal 4 — Improve documentation quality (diagrams, IP plans, and configuration notes)]]
    - [[Semester Goals (Networking Basics) - 2026-02-21#Goal (measurable / “done” definition)|Goal (measurable / “done” definition)]]
    - [[Semester Goals (Networking Basics) - 2026-02-21#How I will achieve it (plan)|How I will achieve it (plan)]]
    - [[Semester Goals (Networking Basics) - 2026-02-21#End-of-semester reflection (to fill in later)|End-of-semester reflection (to fill in later)]]
- [[Semester Goals (Networking Basics) - 2026-02-21#Goal 5 — Improve teamwork & communication during the ProfTask (real company)|Goal 5 — Improve teamwork & communication during the ProfTask (real company)]]
    - [[Semester Goals (Networking Basics) - 2026-02-21#Goal (measurable / “done” definition)|Goal (measurable / “done” definition)]]
    - [[Semester Goals (Networking Basics) - 2026-02-21#How I will achieve it (plan)|How I will achieve it (plan)]]
    - [[Semester Goals (Networking Basics) - 2026-02-21#End-of-semester reflection (to fill in later)|End-of-semester reflection (to fill in later)]]
    - [[Semester Goals (Networking Basics) - 2026-02-21#End-of-semester overall reflection (summary)|End-of-semester overall reflection (summary)]]


---

## Introduction
For each goal I will:
1. Define what “done” looks like (clear deliverables I can show).
2. Write how I will work toward it during the semester.
3. At the end of the semester, reflect using evidence from my case study and ProfTask.

---

# Goal 1 - Strengthen core networking fundamentals through real case studies

## Goal (measurable / “done” definition)
By the end of the semester, I can **independently design and justify** a small-to-medium network for a realistic client case study (e.g., a library), including:
- an **IP addressing plan** (subnetting decisions explained),
- **VLAN segmentation** aligned with requirements (e.g., staff/guest/servers/management),
- basic **routing** decisions (inter-VLAN routing and default gateways),
- and a short explanation of *why* these choices fit the scenario (security, scalability, manageability).

**Proof / deliverables**
- A complete case study report section that includes: requirements → design decisions → IP/VLAN plan → final design summary.
- A diagram and addressing table that match the final GNS3 build.
- A short “design rationale” page (what I chose and why).

## How I will achieve it (plan)
- **Daily practice (small but consistent):**
  - 20–30 minutes/day reviewing one concept that shows up in designs (subnetting, VLANs, routing, ACL basics, DHCP/DNS basics).
- **Attend workshops regularly:**
  - Actively participate and ask questions when something in my design is unclear.
- **Side learning (structured):**
  - Follow a CCNA-level learning path (Cisco CCNA materials, or a YouTube/Udemy course).
  - For each module I complete, I will write down *one thing I can now apply to my case study design*.
- **Apply immediately to the case study:**
  - Every time I learn a concept, I will update my case study design (even if it’s a draft), so theory always turns into a concrete decision.

## End-of-semester reflection (to fill in later)
- Which concepts became easy to apply in designs?
- Which concepts did I still avoid or misunderstand?
- Did my final design look consistent and professional (requirements → decisions → implementation)?
- What feedback did I receive (teacher/client/company), and what did I change based on it?

---

# Goal 2 — Build a complete working network implementation in GNS3 for the case study

## Goal (measurable / “done” definition)
By the end of the semester, I will have a **fully working GNS3 implementation** of my case study design that demonstrates, at minimum:
- VLANs implemented on switching,
- inter-VLAN routing working end-to-end,
- DHCP working for at least the client VLAN(s) (or static addressing if justified),
- basic security controls applied (e.g., management access separation or ACL rules),
- and successful connectivity tests that match the requirements (what should talk to what, and what should not).

**Proof / deliverables**
- The **GNS3 project** (saved and reproducible).
- Device configs exported/saved (routers/switches).
- A short test plan + results (e.g., ping tests, DHCP lease proof, blocked traffic proof).

## How I will achieve it (plan)
- **Implementation milestones (weekly):**
  1. Build the base topology (devices, links, naming).
  2. Implement the addressing plan (SVIs/subinterfaces, gateways).
  3. Add VLANs + trunking/access ports.
  4. Add routing (inter-VLAN) and verify connectivity.
  5. Add services (DHCP; DNS if needed in the scenario).
  6. Add security rules (ACLs / management separation) and verify “allowed vs blocked”.
- **Verification habit:**
  - After every change, I will run a small set of checks:
    - `show ip interface brief` / `show vlan brief` / `show interfaces trunk` (or equivalent),
    - test client connectivity per VLAN,
    - confirm failures are “expected failures” (security working) rather than mistakes.
- **Keep builds reproducible:**
  - Save configs frequently and maintain a versioned folder (e.g., `week-3`, `week-5`) so I can roll back if I break something.
- **Troubleshooting notes:**
  - When something fails, I will log: symptom → likely layer (L1/L2/L3) → command/tests used → fix. 

## End-of-semester reflection (to fill in later)
- Was my final GNS3 implementation stable and easy to demonstrate?
- Which parts took the most time (VLANs, routing, DHCP, ACLs, etc.) and why?
- Did my test plan catch issues early, or did I find issues late?
- If I rebuilt it from scratch now, what would I do differently?

---

# Goal 3 — Become faster and more confident with CLI configuration

## Goal (measurable / “done” definition)
By the end of the semester, I can configure the core parts of my network **from scratch** on CLI without step-by-step tutorials, using my own checklist:
- baseline device setup (hostname, passwords/SSH if required, management IP),
- VLAN creation + trunk/access configuration,
- inter-VLAN routing configuration,
- DHCP scope configuration (if used),
- and basic ACL rules (if used),

and I can do a “clean rebuild” of my core topology within a reasonable time window (tracked by me), improving over the semester.

**Proof / deliverables**
- A personal CLI checklist (“baseline config”) that I actually used.
- At least 3 tracked rebuild attempts (date + what was configured + rough time + what slowed me down).
- Final configs from the case study showing consistent, readable configuration.

## How I will achieve it (plan)
- Create a **baseline checklist** early and refine it every time I get stuck.
- Do intentional “rebuild practice”:
  - rebuild a small portion (e.g., one router + one switch + two VLANs),
  - then later rebuild the full core.
- When I search/learn a command, I add it to my checklist in my own words (so I stop depending on copy/paste).

## End-of-semester reflection (to fill in later)
- Did I become less dependent on guides?
- What were the top 5 commands/areas I had to relearn repeatedly?
- Did my configs become cleaner and more consistent?

---

# Goal 4 — Improve documentation quality (diagrams, IP plans, and configuration notes)

## Goal (measurable / “done” definition)
By the end of the semester, I can produce **professional, clear documentation** for my case study and/or ProfTask that another student could follow to understand the network:
- topology diagram,
- IP plan / VLAN table,
- device inventory (what each device does),
- key configuration excerpts or summaries,
- and a short test/verification section.

**Proof / deliverables**
- A documentation package included in my case study submission:
  - diagram + IP/VLAN tables + configuration summary + verification results.

## How I will achieve it (plan)
- Use one consistent template for every update (same headings every time).
- Update documentation **at the same time** as I change the GNS3 build (no “I’ll document later”).
- Ask for feedback once mid-semester: “Is my diagram/IP plan understandable without me explaining it?”

## End-of-semester reflection (to fill in later)
- Which documentation parts were strongest (diagram, tables, rationale)?
- What feedback did I get, and what did I improve?
- Could someone reproduce my work from my documentation?

---

# Goal 5 — Improve teamwork & communication during the ProfTask (real company)

## Goal (measurable / “done” definition)
During the ProfTask group project, I will become a more effective teammate by:
- communicating clearly and consistently,
- being more open to other approaches (not only what I already know),
- and contributing reliably to the final deliverable for the real company.

**Proof / deliverables**
- Meeting notes / action items where my tasks are visible.
- At least 2 moments where I explicitly tried a teammate’s idea or approach (and documented the outcome).
- Peer feedback (informal or formal) showing improvement in communication/collaboration.

## How I will achieve it (plan)
- **Weekly team communication habit:**
  - share what I finished, what I’m doing next, and what I’m blocked on.
- **Practice openness to new ideas:**
  - when a new idea is suggested, I will ask clarifying questions and evaluate it before rejecting it.
  - if there are two valid options, I will propose a quick comparison (pros/cons) rather than immediately choosing my default.
- **Be explicit about decisions:**
  - write down team decisions and the reason (helps avoid misunderstandings).

## End-of-semester reflection (to fill in later)
- Did I listen more and collaborate better than at the start?
- Where did I still default to “my way” too quickly?
- What did I learn from teammates that improved the result?

---

## End-of-semester overall reflection (summary)
- Which goal did I achieve best, and why?
- Which goal was hardest, and what will I change next semester?
- What concrete evidence (files, configs, docs, feedback) shows my growth?