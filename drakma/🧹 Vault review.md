# 🧹 Vault review – 12 Nov 2026

Every note now has two labels in its properties (top of the note):
- **`review`** – `ok`, `review` (check a fact or confirm ❓ items), `update` (rewrite or merge), `delete` (safe to remove; nothing is lost, the facts are elsewhere and Git keeps history).
- **`mode`** – which part of you the note serves: 🧠 **think**, 📚 **learn**, ⚙️ **do**.

**How to use this list:** work top to bottom. When you finish a note, change its `review` property to `ok` (or delete the note). Tell Claude "apply the vault review" and it will do the deletes and merges for you.

## 🗑️ Delete (5)
| Note | Mode | Why |
|---|---|---|
| [[2026-08-06 API7 onboarding]] <br><small>API7 Gateway</small> | ⚙️ Executor | Two lines; the fact (SaaS, usage billing) is in the hub. |
| [[Introduction]] <br><small>API7 Gateway</small> | 📚 Learner | From the August trial; the facts are in the hub. |
| [[2026-08-18 Ranjan]] <br><small>Digital Lending</small> | ⚙️ Executor | Three half-lines; the points are already in the hub. |
| [[Eligibility workflow (top notes)]] <br><small>Digital Lending</small> | 🧠 Thinker | Near-duplicate of [[Product eligibility & customer classification]]; its one extra point (CSE shares only eligibility) is already in the hub. |
| [[Projects app feedback]] <br><small>Ops & Admin</small> | ⚙️ Executor | Every item is crossed out (done). Delete, or move to Archive. |

## ✏️ Update (10)
| Note | Mode | Why |
|---|---|---|
| [[Architecture]] <br><small>API7 Gateway</small> | 📚 Learner | Learning stopped at 'key concepts'. Finish the API7 concepts and add what you learned. |
| [[CRDB – Pre-scoring data sharing (undated)]] <br><small>Digital Lending</small> | ⚙️ Executor | Add the meeting date to the file name. |
| [[LMS Project Scope; tasks and subtasks]] <br><small>Digital Lending</small> | ⚙️ Executor | From August; replaced by the DCP CRs and the LMS v2.0 timelines (9 Nov). Update or move to Archive. |
| [[Customer - 2026-08-27]] <br><small>Digital Lending</small> | ⚙️ Executor | Mostly crossed out. Keep only the open points, or move to Archive (customer service is done). |
| [[AML Raised Issues]] <br><small>GonzaPay AML</small> | ⚙️ Executor | Check which issues are fixed in the live app; AML-007 still to fix. |
| [[Defining the view & underlying table]] <br><small>GonzaPay AML</small> | 📚 Learner | Says 'only successful transactions' – the system now includes failed ones. Update that line. |
| [[Key Notes]] <br><small>GonzaPay AML</small> | ⚙️ Executor | Check the open UI items against the live app; tick what's already fixed. |
| [[MTP integration notes]] <br><small>GonzaPay</small> | 📚 Learner | Short and unstructured; merge the facts into [[Motor Third Party]] and delete, or expand into a proper API reference. |
| [[Interviews]] <br><small>Ops & Admin</small> | ⚙️ Executor | Bottom half is loan-processor eligibility design, not hiring – move it to Digital Lending. Candidate notes are private: keep them out of anything shared. |
| [[Go-live]] <br><small>QRPe</small> | ⚙️ Executor | Overlaps the Stanbic go-live tasks in [[QRPe]]. Keep as the go-live checklist, but sync it with the hub. |

## 👀 Review – confirm facts or ❓ items (15)
| Note | Mode | Why |
|---|---|---|
| [[CPU cache and memory bus]] <br><small>Archive</small> | 📚 Learner | Personal learning, not work – move to your personal vault when it exists. |
| [[API7 Gateway]] <br><small>API7 Gateway</small> | ⚙️ Executor | Confirm the 'from older notes' tasks (MTP docs, Airtel, routing research). |
| [[Security overview for partners]] <br><small>API7 Gateway</small> | 📚 Learner | The last bullets (access reviews, incident response, DR, recovery tests) look like unanswered partner questions – answer or remove. |
| [[Digital Lending]] <br><small>Digital Lending</small> | ⚙️ Executor | Confirm the 'from older notes' tasks and the ❓ architecture review. |
| [[2026-09-04 Customer service review]] <br><small>Digital Lending</small> | ⚙️ Executor | Contains a phone number and an ID – remove them if they belong to a real customer. |
| [[CRDB - LMS data flow & PII]] <br><small>Digital Lending</small> | 🧠 Thinker | Check it matches the answers Drakma sent to Centenary's risk team on 22 Oct. |
| [[service discovery]] <br><small>Digital Lending</small> | 📚 Learner | A list of open questions (Eureka, registry, load balancing). Answer them, or delete if Docker Swarm/Eureka is no longer the plan. |
| [[AML Fraud detection data layout & storage]] <br><small>GonzaPay AML</small> | 🧠 Thinker | Early research (July) with no final decision. Record what was chosen, or move to Archive. |
| [[Data Schema]] <br><small>GonzaPay AML</small> | 🧠 Thinker | Early plan (July). Check against what was built; update or move to Archive. |
| [[Rule Configuration]] <br><small>GonzaPay AML</small> | 🧠 Thinker | Design is open: decide Option A (fixed attributes) or B (user-built conditions). |
| [[Motor Third Party]] <br><small>GonzaPay</small> | ⚙️ Executor | Confirm the 3 ❓ items: 400-response fields, IDD review, solution document review. |
| [[URA Tax Payments]] <br><small>GonzaPay</small> | ⚙️ Executor | Confirm which branch code is right (CNB1 vs the code used on 29 Oct). |
| [[GonzaPay]] <br><small>GonzaPay</small> | ⚙️ Executor | Confirm the ❓ tasks (customer info app, UEDCL messages). |
| [[Ops & Admin]] <br><small>Ops & Admin</small> | ⚙️ Executor | Confirm whether projects.drakma.com certificate was renewed on 3 Nov. |
| [[QRPe]] <br><small>QRPe</small> | ⚙️ Executor | Confirm the 'from older notes' tasks (DB clean-up, mutual TLS, BigQuery). |

## ✅ Everything else is OK
Old meeting notes and the Archive are kept as history.

---

## 🧠📚⚙️ Thinker, learner, executor – how the vault supports each

| | 🧠 **Thinker** | 📚 **Learner** | ⚙️ **Executor** |
|---|---|---|---|
| **Notes** | Design and decision notes (`mode: think`) – 11 notes | Reference and learning notes (`mode: learn`) – 12 notes | Hubs, billers, daily notes, meetings (`mode: do`) – 24 notes |
| **A good note has** | Problem → options → **decision** → open questions | What I know → **what I still want to learn** → sources | Clear tasks with dates, who I'm waiting on |
| **Gap found today** | Several design notes stop before a decision (Rule Configuration, Data Schema, data layout) | Learning notes stop half-way (API7 Architecture "stopped on key concepts", service discovery questions unanswered) | Many tasks marked ❓ – unclear if done |
| **Next step** | A weekly "decisions" check: list think-notes with open questions | A "learning queue": one topic per week with a short quiz | Already running: daily plan, check-ins, wrap-up, weekly review |

Today the daily routine mostly serves the **executor**. Next we can add the **thinker** and **learner** parts to the routine.
