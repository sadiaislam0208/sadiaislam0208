<div align="center">

```
╔══════════════════════════════════════════════════════════╗
║                                                          ║
║   Hi there, I'm Sadia Islam 👋                          ║
║   Computer Science @ Trent University                    ║
║   Builder · Researcher · Problem Solver                  ║
║                                                          ║
╚══════════════════════════════════════════════════════════╝
```

[![Email](https://img.shields.io/badge/sadiaislam%40trentu.ca-D14836?style=flat-square&logo=gmail&logoColor=white)](mailto:sadiaislam@trentu.ca)
[![Location](https://img.shields.io/badge/Peterborough%2C_Ontario-0A66C2?style=flat-square&logo=google-maps&logoColor=white)](https://maps.google.com/?q=Peterborough,Ontario)
![Pronouns](https://img.shields.io/badge/she%2Fher-8A2BE2?style=flat-square)

</div>

---

## 👩‍💻 About Me

I'm a Computer Science student at **Trent University** with a passion for building systems that actually matter — databases, accessible tech, and data-driven solutions. I care deeply about **inclusive design**: my research explores how AI voice assistants fail users with accents and speech impairments, and what we can do about it.

When I'm not coding, I'm tutoring fellow students, representing off-campus students on college cabinet, or facilitating digital literacy workshops for communities.

- 🎓 **BSc Computer Science**, Trent University *(Jan 2025 – Present)*
- 📊 **GPA: 3.97 / 4.0** — with perfect scores in **Data Science (100)**, **Probability (99)**, **Data Mining (100)**, **Big Data (95)**
- 🏫 **COIS 1020 Student Marker** & **Math Tutor** — helping peers understand complex material
- 🌍 Former **Youth Ambassador**, Bangladesh Internet Governance Forum

---

## 🔬 Research

### 🎙️ Hearing Every Voice: Speech Accessibility in AI Voice Assistants
*Trent University — Human-Computer Interaction (COIS 3560)*

> **How do the limitations of AI voice assistants affect users with speech accessibility needs?**

Co-authored with Amber McLenaghan, Rida Opal, and Krina Vyas. Published in ACM format.

**Key Findings:**
- ASR systems are trained on "standard speech" datasets, causing significantly higher error rates for users with accents, speech impediments (dysarthria, lisps, cleft palate), or non-native pronunciation
- Repeated misrecognition creates a compounding trust problem — users who need these tools most are the most likely to abandon them
- Commercial voice assistants (Alexa, Google Assistant, Siri, Cortana) score high on visual/motor accessibility but **low on speech-impairment support**
- Meaningful progress requires diverse training datasets, impairment-specific evaluation, and accessibility-first design practices

**Research Areas:** `Human-Computer Interaction` · `Accessibility` · `Automatic Speech Recognition` · `Inclusive Design`

---

## 🛠️ Projects

### 🗄️ Trent University Student & Alumni Job Tracking Database
*COIS 3400 — Database Management Systems · Winter 2026*

A fully-featured relational database system that **proactively matches students and alumni with job opportunities** — no manual searching required.

**Architecture Highlights:**
- **13 normalized tables** in Third Normal Form (3NF) — no redundancy, no anomalies
- **7 triggers**: audit logging, data validation, and an auto-recommendation engine that fires on student registration
- **3 stored procedures** for common staff queries
- **2 views** simplifying job and applicant lookups
- **Role-based access control** (read-only / moderator / admin) via MySQL GRANT
- **Full-text search index** on job descriptions (EXPLAIN confirmed: full table scan → indexed lookup)
- **6,302 user accounts** and **6,201 applications** generated with Python + Faker for realistic testing

**Stack:** `MySQL` · `phpMyAdmin` · `Python (Faker)` · `SQL`

**Key Design Decision:** Auto-recommendation trigger `trg_auto_recommend_insert` — when a student registers, the system instantly matches them to open jobs based on department and GPA. No app layer needed.

```sql
-- Auto-match students to jobs on registration
CREATE TRIGGER trg_auto_recommend_on_student_insert
AFTER INSERT ON StudentProfile
FOR EACH ROW
BEGIN
  INSERT IGNORE INTO JobRecommendation (user_id, job_id, recommendation_reason, recommendation_score)
  SELECT NEW.user_id, jp.job_id,
    CONCAT('Auto-matched: department match, min GPA=', COALESCE(jp.min_gpa, 0)),
    CASE
      WHEN jp.min_gpa IS NULL       THEN 70.00
      WHEN NEW.gpa >= jp.min_gpa + 0.5 THEN 90.00
      WHEN NEW.gpa >= jp.min_gpa    THEN 75.00
      ELSE 55.00
    END
  FROM JobPosting jp
  JOIN JobDepartment jd ON jp.job_id = jd.job_id
  WHERE jd.department_id = NEW.department_id
    AND jp.status = 'Open'
    AND (jp.min_gpa IS NULL OR NEW.gpa >= jp.min_gpa - 0.5)
  LIMIT 10;
END
```

---

## 📚 Coursework Highlights

| Course | Grade | Area |
|---|---|---|
| COIS 4400 — Data Mining | **A+ (100)** | Machine Learning & Analytics |
| COIS 1400 — Introduction to Data Science | **A+ (100)** | Data Fundamentals |
| MATH 1550 — Introduction to Probability | **A+ (99)** | Mathematics |
| MATH 1110 — Calculus I | **A+ (99)** | Mathematics |
| MATH 2600 — Discrete Structures | **A+ (97)** | Theoretical CS |
| COIS 4450 — Big Data | **A+ (95)** | Large-Scale Systems |
| COIS 3820 — History & Impact of Computing | **A+ (94)** | Computing & Society |
| COIS 3560 — Human-Computer Interaction | **A (89)** | UX & Accessibility |
| COIS 3400 — Database Management Systems | **A- (84)** | Databases |
| COIS 2300 — Computer Organization | **A (88)** | Systems |

---

## 🧰 Skills & Tools

```
Languages       Python  ·  SQL  ·  Java  ·  HTML/CSS
Databases       MySQL  ·  phpMyAdmin  ·  Relational Design  ·  3NF Normalization
Data            Pandas  ·  Faker  ·  Data Generation  ·  Query Optimization
Tools           Git  ·  PowerPoint  ·  Canva  ·  Microsoft Office
Research        Literature Review  ·  ACM Format  ·  HCI  ·  Accessibility Analysis
Soft Skills     Teaching  ·  Public Speaking  ·  Event Coordination  ·  Leadership
```

---

## 🌱 Leadership & Community

| Role | Organization | Period |
|---|---|---|
| Off-Campus Representative | Otonabee College Cabinet, Trent University | Sep 2025 – Present |
| First Year Representative & Organizer | Hack Trent 2025 | 2025 |
| Student Marker — COIS 1020 | Trent University | Jan – Apr 2026 |
| Math Tutor | Trent University | Jan – Apr 2026 |
| Youth Ambassador | Bangladesh Internet Governance Forum | Oct 2023 – Dec 2024 |
| Teacher (Grade 7 English) | Bacha English Medium School, Dhaka | Sep – Oct 2024 |
| General Member | Trent Active Minds | Jan – Apr 2025 |
| Participant | Collegiate Leadership Competition | Jan – Mar 2025 |
| Volunteer | All College Colors Dance Carnaval | Sep 2025 |

**Hack Trent 2025** — Served as First Year Representative and helped organize Trent University's hackathon, bridging the gap between new students and the broader CS community while contributing to event planning and logistics.

**Bangladesh Internet Governance Forum** — Led workshops on online safety, created educational content using Canva, and collaborated with educators and business owners to promote digital literacy across diverse communities.

**Teaching in Dhaka** — Designed interactive English lessons for Grade 7 students using digital tools; achieved an 80% A-grade student success rate through personalized feedback and progress monitoring.

---

## 📈 What I'm Working On

- 🔍 Exploring applications of **data mining and machine learning** to real-world problems
- 📖 Deepening my understanding of **accessible and inclusive system design**
- 🛠️ Building projects that connect academic theory to practical, scalable solutions
- 🤝 Looking for **internship and research opportunities** in data, software, or HCI

---

## 📬 Let's Connect

I'm always open to collaborating on meaningful projects, discussing research, or just connecting with fellow builders.

**📧** [sadiaislam@trentu.ca](mailto:sadiaislam@trentu.ca) &nbsp;|&nbsp; **📍** Peterborough, Ontario

---

<div align="center">

*"By making light of these kinds of issues, AI voice assistants can move closer to becoming genuinely accessible tools that support independence, convenience, and inclusive participation for everyone."*
— from my HCI research paper

</div>
