# Lovable פרומפט 2 — מתאמת שירות: ניהול מטופלים וסלים

> אפליקציה למתאמת השירות — ניהול מטופלים, בניית סלים, מעקב הדרדרות, תיאום ספקים.
> העתק הכל מתחת לקו ל-Lovable.

---

## 🔽 התחל להעתיק מכאן 🔽

---

Build a complete Hebrew RTL web application: **"מתאמת — מערכת ניהול סל אישי בסיעוד"**

This is the care coordinator's (מתאמת שירות) professional dashboard — the core deliverable of the Osprint process with Strauss Strategy (March 2026). She manages 25-40 elderly care recipients, builds personalized service baskets, coordinates with providers, monitors deterioration indicators (RDI/SDI), and ensures each person gets the right services. This is the operational heart of Israel's nursing care reform.

**The story:** A care coordinator today works with paper forms, no digital tools, no deterioration alerts. This system transforms her work — digital profiles, rule-based recommended baskets, real-time deterioration monitoring, provider coordination, and outcome tracking. The pilot runs in Jerusalem ("עכשיו אני") with 286 participants across care levels 1-3, and is expanding to 3-5 municipalities nationwide.

**Osprint decisions (March 2026):**
- Scope: coordinator tool ONLY — not the marketplace or provider recruitment
- Matching engine: simple dichotomous filtering first (area, care level, hard parameters) — NOT AI
- Data infrastructure: every coordinator decision is logged for future learning engine
- Generic architecture: the tool must serve other NII departments (disability, rehabilitation, unemployment)
- Design partners: the care coordinators themselves are co-designers of this system

---

## DESIGN SYSTEM — BTL (ביטוח לאומי, מינהל גמלאות)

### Identity
- Organization: ביטוח לאומי — המוסד לביטוח לאומי
- Department: מינהל גמלאות
- Credit: "אביעד יצחקי, מינהל גמלאות"
- Logo: Circle with "ב"ל" text + "ביטוח לאומי / מינהל גמלאות"

### Colors
- Primary: #0c3058, Secondary: #0368b0, Tertiary: #266794, Accent: #e8a020
- Background: #f5f9ff, Surface: #ffffff, Text: #0c3058, Muted: #6b7a8d
- Success: #1a7a4e, Warning: #cc7a00, Error: #c0392b, Info bg: #e8f3ff
- Border: rgba(6, 77, 173, 0.1)

### Typography: Heebo, RTL, Hebrew. h1:28px/800, h2:22px/700, h3:18px/700, Body:14px/400

### Layout: Max 1200px, Card radius 12px, Button radius 8px, Shadow: 0 2px 8px rgba(6,77,173,0.1)

### Components
- Buttons: bg-[#0368b0] text-white rounded-lg px-4 py-2.5 font-semibold hover:bg-[#025a8f] focus-visible:ring-2
- Cards: bg-white border border-black/10 rounded-xl shadow-sm p-5
- Inputs: border border-[#0368b0]/30 rounded-lg px-3 py-2.5 focus:ring-2
- Header: bg-[#0c3058] text-white, Footer: bg-[#0c3058] text-white/80

### Accessibility: lang="he" dir="rtl", skip nav, labels+aria, contrast 4.5:1, focus 2px, keyboard, semantic HTML, touch 44px

### Tech: React 18+ TypeScript, Vite, Tailwind, shadcn/ui, Heebo, Recharts, Lucide icons, hooks only, mock data

### Footer: "אביעד יצחקי, מינהל גמלאות | ביטוח לאומי | v1.0 | מרץ 2026"

### RULES: Hebrew only, RTL only, government tone, focus-visible, labels above inputs, no light-on-light.

---

## APPLICATION — 7 PAGES

### Navigation (Sidebar RIGHT — RTL, collapsible)
User: "שרה ישראלי, מתאמת שירות | פיילוט ירושלים"
1. 🏠 דשבורד
2. 👥 מטופלים
3. ➕ קליטה חדשה
4. 📊 הדרדרות
5. 🤝 ספקים ותיאום
6. 📋 דוחות
7. ⚙️ הגדרות

---

### PAGE 1: דשבורד

**Top stats — 5 cards:**
- המטופלים שלי: 28 (Users icon) — subtitle: "מתוך 286 בפיילוט"
- התראות פתוחות: 5 (AlertTriangle, accent badge)
- ממתינים לסל: 3 (Clock)
- SDI ממוצע: 24.3 (BarChart3)
- ביקורים השבוע: 7 (Calendar)

**Osprint info bar (below stats, full width, bg-[#e8f3ff] rounded-xl p-4):**
- "פיילוט ירושלים — 286 משתתפים | מנוע התאמה: סינון דיכוטומי v1.0 | איסוף דאטה: פעיל"
- Small badge: "Osprint שלב 1" in accent color

**Two columns:**

Left — "דורשים תשומת לב" (sorted by urgency):
Table with 5 rows: שם | גיל | רמה | RDI | SDI | סטטוס (colored badge)
- לאה שמעון, 83, רמה 4, RDI 1.52 🔴, SDI 5 🔴, "דחוף"
- שרה אברהם, 88, רמה 1, RDI 1.49 🔴, SDI 0 🔴, "דחוף"
- אסתר נחום, 87, רמה 3, RDI 1.41 🟡, SDI 11 🟡, "לבדיקה"
- אברהם פרץ, 79, רמה 2, RDI 1.34 🟡, SDI 8 🟡, "לבדיקה"
- מרים דוד, 85, רמה 4, RDI 1.22 🟡, SDI 33 🟢, "מעקב"

Right — "לוח משימות היום":
Checklist with 6 items:
- ☐ ביקור בית — רחל כהן (10:00)
- ☐ שיחת מעקב — משה לוי (11:30)
- ☐ בניית סל — יעקב מזרחי (13:00)
- ☑ הערכה מחודשת — חנה גולדשטיין (בוצע)
- ☐ תיאום ספק — פיזיותרפיה לאסתר נחום (15:00)
- ☐ דוח שבועי (16:00)

**Bottom:** "התפלגות מטופלים לפי רמת גמלה" — bar chart (Recharts)

---

### PAGE 2: רשימת מטופלים

**Top:** Search + filters (רמת גמלה, סטטוס התראה, ממתין לסל)

**Table:**
| שם | גיל | מגדר | רמה | RDI | SDI | שירותים בסל | מעקב אחרון | סטטוס | פעולות |

- RDI: green <1.2, yellow 1.2-1.5, red >1.5
- SDI: red 0, yellow 1-17, green >17
- פעולות: "צפה" → patient card, "מעקב" → new follow-up

**12 mock patients:**
1. רחל כהן, 82, נ, רמה 3, RDI 1.12, SDI 28, 8 שירותים, 2.3.26, פעיל
2. משה לוי, 76, ז, רמה 2, RDI 0.89, SDI 17, 5 שירותים, 28.2.26, פעיל
3. שרה אברהם, 88, נ, רמה 1, RDI 1.49, SDI 0, 1 שירות, 15.2.26, דחוף
4. יעקב מזרחי, 71, ז, רמה 1, RDI 0.74, SDI 12, 3 שירותים, 1.3.26, פעיל
5. מרים דוד, 85, נ, רמה 4, RDI 1.22, SDI 33, 9 שירותים, 5.3.26, מעקב
6. אברהם פרץ, 79, ז, רמה 2, RDI 1.34, SDI 8, 3 שירותים, 20.2.26, לבדיקה
7. חנה גולדשטיין, 91, נ, רמה 5, RDI 1.08, SDI 42, 11 שירותים, 7.3.26, פעיל
8. דוד ביטון, 68, ז, רמה 1, RDI 0.95, SDI 17, 4 שירותים, 25.2.26, פעיל
9. אסתר נחום, 87, נ, רמה 3, RDI 1.41, SDI 11, 4 שירותים, 18.2.26, לבדיקה
10. יוסף חדד, 74, ז, רמה 2, RDI 1.15, SDI 22, 6 שירותים, 3.3.26, פעיל
11. לאה שמעון, 83, נ, רמה 4, RDI 1.52, SDI 5, 2 שירותים, 10.2.26, דחוף
12. חיים רוזנברג, 77, ז, רמה 3, RDI 0.98, SDI 31, 7 שירותים, 6.3.26, פעיל

---

### PAGE 3: כרטיס מטופל (Patient Card)

**Header:** Name + age + care level badge + status badge + "ערוך" button

**5 tabs:**

**Tab 1 — פרופיל:**
Personal details in 2-column layout: שם, ת.ז., גיל, מגדר, כתובת, טלפון, איש קשר, רמת גמלה, מצב משפחתי, רשת תמיכה, תאריך קליטה.

**Tab 2 — הערכה:**
- Last assessment date + "הערכה חדשה" button
- Radar chart (6 dimensions, scores 1-4)
- Below radar: 6 detail cards, each showing dimension name, score, key notes
- Assessment history: table of past assessments with dates and scores

**Tab 3 — סל אישי:**
- Current basket grouped by dimension (accordion)
- Each service: name, provider, status badge (פעיל/ממתין/מומלץ), start date
- "ערוך סל" button → opens basket builder
- "SDI נוכחי: XX" indicator
- "שירותים מומלצים שחסרים" — 2-3 suggestions

**Tab 4 — מעקב:**
- Timeline (vertical) of all follow-ups: date, type icon (ביקור/שיחה/הערכה), summary, coordinator
- "הוסף מעקב" button → modal with: type dropdown, date, notes textarea, "שינוי במצב?" toggle
- Filter by type

**Tab 5 — מדדים:**
- RDI over time — line chart (6 months)
- SDI over time — line chart (6 months)
- RDI×SDI matrix position — highlighted dot on scatter
- Alert history: table of past alerts with dates, type, response
- Decision log: table of last 10 coordinator decisions (what was recommended, what was chosen, what was rejected) — feeds future learning engine

---

### PAGE 4: קליטה חדשה (4-step wizard)

**Stepper at top:** פרטים אישיים → הערכה תפקודית → המלצת סל → סיכום

**Step 1 — פרטים אישיים:**
Form: שם פרטי*, שם משפחה*, ת.ז.*, תאריך לידה*, מגדר* (select), כתובת, טלפון, איש קשר חירום (שם+טלפון+קרבה), רמת גמלה* (select 1-6), מצב משפחתי (select)

**Step 2 — הערכה תפקודית:**
6 sections with sliders (1-4) + description per score:
- תפקודי: רחצה, הלבשה, אכילה, ניידות, שירותים, העברות
- חברתי: בידוד, תמיכה משפחתית, פעילות
- בריאותי: מחלות רקע (multi-select chips), תרופות, כאב
- קוגניטיבי: זיכרון, התמצאות, קבלת החלטות
- טכנולוגי: טלפון, מחשב, טכנולוגיה מסייעת
- סביבתי: נגישות דירה, קרבה לשירותים, מדרגות

Live radar chart updating as scores change.

**Step 3 — המלצת סל:**
Auto-generated services based on SIMPLE DICHOTOMOUS FILTERING (as decided in Osprint):
- Filter 1: area match (patient area == service area)
- Filter 2: care level in service range
- Filter 3: no medical contraindication
- Priority rules: if SDI==0 → prioritize social services; if RDI>1.3 → prioritize deterioration-prevention services; if female 85+ → red flag (RDI=1.49 outlier)

Cards with checkboxes grouped by dimension. Add/remove services. Live SDI indicator.

**Decision logging (Osprint requirement — data infrastructure):**
Every recommendation shown, accepted, rejected, or modified is logged with timestamp and coordinator ID. This data feeds the future learning engine.

**Step 4 — סיכום:**
All data summary + basket + decision log preview + "אשר וצור תיק" button.

---

### PAGE 5: ספקים ותיאום

**Two sections:**

**Section 1 — ספקים:**
Table: שם ספק | ממדים | אזור | דירוג | מטופלים פעילים | סטטוס
8 mock providers with data. Click → provider detail with services list + contact.

**Section 2 — תיאומים פתוחים:**
Table: מטופל | שירות | ספק | סטטוס | תאריך בקשה | פעולות
Mock 5 pending coordinations:
- שרה אברהם — ליווי חברתי — חברים לדרך — ממתין לאישור — 5.3.26
- אברהם פרץ — פיזיותרפיה — תנועה חופשית — מתואם — 3.3.26
- לאה שמעון — כפתור מצוקה — ערנות 24/7 — בהתקנה — 7.3.26
- אסתר נחום — מועדון יום — מתנ"ס קטמון — ממתין למקום — 1.3.26
- יעקב מזרחי — התאמות דיור — בית בטוח — בתהליך — 28.2.26

---

### PAGE 6: דוחות

**4 report cards:**

1. "דוח שבועי" — סיכום פעילות: ביקורים, שינויי סל, התראות שטופלו. "צור דוח" button → shows mock report.

2. "דוח הדרדרות" — RDI×SDI matrix scatter chart + table of at-risk patients. Bar chart: RDI by gender×age group (real data: men <74: 0.74, men 75-84: 1.34, men 85+: 1.03, women <74: 1.21, women 75-84: 0.95, women 85+: 1.49).

3. "דוח SDI" — SDI distribution donut: SDI=0 (44.6%), SDI=17 (41.3%), SDI≥33 (14.1%). Bar chart: average SDI by care level (level 1: 9.4, level 2: 17.9, level 3: 21.0, level 4: 22.2, level 5: 23.0).

4. "דוח KPIs פיילוט" — 6 KPI cards: זמן בניית סל (25 דק, יעד <30), שביעות רצון מתאמות (4.2/5), SDI ממוצע (24.3, יעד >25), שימוש במערכת (85%), דיוק המלצות (73%), התראות שטופלו (91%).

---

### PAGE 7: דשבורד הדרדרות (dedicated page)

**Top stats:** מטופלים עם RDI>1.3: 4 | מטופלים עם SDI=0: 1 | RDI ממוצע: 1.14

**Main: RDI×SDI Scatter Chart**
- X: SDI (0-50), Y: RDI (0.5-2.0)
- Each dot = patient (hover: name + details)
- Background zones: red (RDI>1.5+SDI<17), yellow (RDI 1.2-1.5 or SDI<17), green (rest)
- Legend explaining zones

**Below:** "מטופלים לבדיקה מועדפת" — filtered table of red-zone patients with action buttons.

**Bottom:** Two bar charts side by side:
- "RDI לפי מגדר וגיל" (6 bars with real data)
- "SDI לפי רמת גמלה" (5 bars with real data)

---

### GENERIC ARCHITECTURE — Cross-Department Support (Osprint Requirement)

The system must be built with a generic "domain" parameter so it can serve other NII departments:

**Domain switcher (in settings page):**
- סיעוד/הזדקנות (active — current implementation)
- נכויות (coming soon)
- שיקום (coming soon)
- אבטלה (coming soon)

**What is generic (shared across domains):**
- Workflow: intake → assessment → recommendation → monitoring
- Data model: profile + assessment dimensions + service catalog + follow-up log
- UI: dashboard + patient list + patient card + reports
- Decision logging infrastructure

**What is domain-specific (configured per domain):**
- Assessment dimensions (6 in nursing, different in disability)
- Deterioration metrics (RDI/SDI in nursing, other metrics elsewhere)
- Service catalog
- Matching rules

Build the domain switcher UI now with "coming soon" badges on inactive domains in the settings page.

---

### ADDITIONAL MOCK PATIENTS (expanded for Osprint — 20 total)

Add these 8 patients to the existing 12:

13. נעמי אלון, 90, נ, רמה 1, RDI 1.45, SDI 0, 1 שירות, 8.3.26, דחוף
14. שלמה ברק, 73, ז, רמה 2, RDI 1.18, SDI 19, 5 שירותים, 4.3.26, פעיל
15. רבקה מלכה, 86, נ, רמה 3, RDI 1.33, SDI 14, 4 שירותים, 2.3.26, לבדיקה
16. עזרא כהן, 81, ז, רמה 1, RDI 0.82, SDI 8, 2 שירותים, 6.3.26, פעיל
17. שושנה לוי, 78, נ, רמה 2, RDI 1.28, SDI 22, 6 שירותים, 7.3.26, פעיל
18. יצחק מור, 84, ז, רמה 3, RDI 1.39, SDI 6, 2 שירותים, 1.3.26, לבדיקה
19. פנינה שרון, 92, נ, רמה 4, RDI 1.55, SDI 3, 2 שירותים, 28.2.26, דחוף
20. בנימין עוז, 70, ז, רמה 1, RDI 0.71, SDI 17, 4 שירותים, 5.3.26, פעיל

## 🔼 סוף הפרומפט 🔼