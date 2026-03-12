# Lovable פרומפט 3 — ניהול קהילה, ספקים ורשויות

> אפליקציה למנהלי הרפורמה — ניהול ספקים, רשויות, KPIs, דוחות ארציים.
> העתק הכל מתחת לקו ל-Lovable.

---

## 🔽 התחל להעתיק מכאן 🔽

---

Build a complete Hebrew RTL web application: **"מנהל סל אישי — פאנל ניהול רפורמת סיעוד"**

This is the management dashboard for the national nursing care reform in Israel. Used by reform managers, regional directors, and National Insurance executives. It provides a bird's-eye view of all pilots, providers, municipalities, KPIs, and the reform's progress. This is the command center.

**The story:** Israel's nursing care reform ("סל אישי") is rolling out in phases — starting with a Jerusalem pilot, expanding to 3-5 municipalities, then nationwide. This dashboard tracks everything: which municipalities joined, which providers are active, how many elderly are served, deterioration metrics across the system, and whether the reform is actually working.

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

### Typography: Heebo, RTL, Hebrew. h1:28px/800, h2:22px/700, h3:18px/700, Body:14px/400

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

## APPLICATION — 6 PAGES

### Navigation (Sidebar RIGHT)
User: "אביעד יצחקי, מנהל רפורמה"
1. 🏠 דשבורד ארצי
2. 🏛️ רשויות מקומיות
3. 🏢 ספקי שירות
4. 📊 מדדים ו-KPIs
5. 📋 דוחות
6. ⚙️ הגדרות

---

### PAGE 1: דשבורד ארצי

**Top hero:** "רפורמת סל אישי — מבט על" + reform phase indicator: "שלב 1: פיילוט ירושלים" (progress bar 65%)

**Stats row — 6 cards:**
- רשויות פעילות: 1 (יעד: 5)
- ספקים רשומים: 24
- מתאמות שירות: 5
- מטופלים בפיילוט: 28
- SDI ממוצע ארצי: 24.3
- RDI ממוצע ארצי: 1.14

**Reform timeline (horizontal stepper):**
- ✅ נייר מדיניות (1.2025)
- ✅ מחקר EY (12.2024)
- ✅ סדנת עיצוב (11.2024)
- ✅ אפיון MVP (3.2026)
- 🔵 פיילוט ירושלים (בתהליך)
- ⬜ לוח ח-2 (טיוטה)
- ⬜ קול קורא (גרסה 2)
- ⬜ הרחבה ל-5 רשויות
- ⬜ הטמעה ארצית

**Two columns:**

Left — "מפת פיילוטים": Stylized Israel map (simplified SVG or just a list with location pins):
- 📍 ירושלים — פעיל (28 מטופלים, 5 מתאמות)
- 📍 תל אביב — בתכנון
- 📍 חיפה — בתכנון
- 📍 באר שבע — ממתין לקול קורא
- 📍 נצרת — ממתין לקול קורא

Right — "KPIs מרכזיים": 4 mini charts:
- SDI trend (line, 6 months)
- RDI trend (line, 6 months)
- Patients enrolled (bar, 6 months, growing)
- Provider satisfaction (gauge, 4.2/5)

---

### PAGE 2: רשויות מקומיות

**Table:**
| רשות | אזור | סטטוס | מתאמות | מטופלים | SDI ממוצע | תאריך הצטרפות | פעולות |

Mock 5 rows:
1. ירושלים | מרכז | 🟢 פעיל | 5 | 28 | 24.3 | 10.2025 | "צפה"
2. תל אביב | מרכז | 🟡 בתכנון | 0 | 0 | — | — | "פרטים"
3. חיפה | צפון | 🟡 בתכנון | 0 | 0 | — | — | "פרטים"
4. באר שבע | דרום | ⚪ ממתין | 0 | 0 | — | — | "הזמן"
5. נצרת | צפון | ⚪ ממתין | 0 | 0 | — | — | "הזמן"

Click "צפה" on Jerusalem → detail page:
- Summary stats: 5 מתאמות, 28 מטופלים, 24 ספקים, SDI 24.3
- Coordinators list: 5 names with patient count
- Top providers in area
- KPIs vs targets (bar chart)
- Recent activity timeline

---

### PAGE 3: ספקי שירות

**Top:** Search + filters (ממד, אזור, דירוג, סטטוס)

**Table:**
| ספק | ממדים | אזורים | דירוג | מטופלים פעילים | שירותים | סטטוס | פעולות |

Mock 12 providers:
1. משען | תפקודי, בריאותי | ירושלים, ת"א | ⭐4.5 | 12 | 4 | פעיל
2. חברים לדרך | חברתי | ירושלים | ⭐4.8 | 8 | 2 | פעיל
3. תנועה חופשית | בריאותי | ארצי | ⭐4.9 | 15 | 3 | פעיל
4. ערנות 24/7 | טכנולוגי | ארצי | ⭐4.8 | 22 | 2 | פעיל
5. בית בטוח | סביבתי | ירושלים, חיפה | ⭐4.6 | 6 | 3 | פעיל
6. מוח פעיל | קוגניטיבי | ירושלים, ת"א | ⭐4.4 | 5 | 2 | פעיל
7. בית חם | תפקודי | ירושלים | ⭐4.2 | 9 | 2 | פעיל
8. קשר קל | טכנולוגי | ארצי | ⭐4.1 | 4 | 1 | פעיל
9. יד ביד | תפקודי | ירושלים | ⭐4.7 | 11 | 1 | פעיל
10. נתיב הזיכרון | קוגניטיבי | ירושלים | ⭐4.6 | 3 | 1 | חדש
11. בריאות בצלחת | בריאותי | ירושלים, ת"א | ⭐4.3 | 7 | 1 | פעיל
12. דרך חופשית | סביבתי | ירושלים | ⭐4.2 | 2 | 1 | חדש

Click provider → detail: contact info, services list, coverage areas, patient reviews, performance metrics.

**Bottom:** "התפלגות ספקים לפי ממד" — bar chart (6 bars)

---

### PAGE 4: מדדים ו-KPIs

**Reform KPIs — 8 cards in 2x4 grid:**

| KPI | ערך נוכחי | יעד | סטטוס |
|-----|----------|-----|-------|
| זמן בניית סל | 25 דקות | <30 דקות | 🟢 עומד ביעד |
| שביעות רצון מתאמות | 4.2/5 | >4.0 | 🟢 עומד ביעד |
| SDI ממוצע | 24.3 | >25 | 🟡 קרוב ליעד |
| שימוש במערכת | 85% | >80% | 🟢 עומד ביעד |
| דיוק המלצות | 73% | >70% | 🟢 עומד ביעד |
| התראות שטופלו <48 שעות | 91% | >90% | 🟢 עומד ביעד |
| מטופלים עם SDI=0 | 3.6% | <5% | 🟢 עומד ביעד |
| שיעור הדרדרות בפיילוט | 12% | <15% | 🟢 עומד ביעד |

Each card: KPI name, current value (large), target, progress bar, trend arrow (up/down).

**Below:** 
- "מגמת KPIs לאורך זמן" — multi-line chart (SDI, usage, satisfaction over 6 months)
- "השוואת פיילוט vs ביקורת" — grouped bar chart (mock: deterioration rate pilot 12% vs control 18%, SDI pilot 24.3 vs control 9.4)

---

### PAGE 5: דוחות

**4 report types as cards:**

1. **דוח סטטוס רפורמה** — "סיכום חודשי למנהלים"
   Preview: executive summary with key metrics, milestones, risks
   "צור דוח" → mock PDF-style view

2. **דוח הדרדרות ארצי** — "RDI×SDI לכל המערכת"
   Preview: scatter chart + demographic breakdown + at-risk list
   Real data: RDI by gender×age, SDI by care level

3. **דוח ספקים** — "ביצועי ספקים ואיכות שירות"
   Preview: provider ranking table, satisfaction scores, coverage gaps

4. **דוח פיילוט ירושלים** — "סטטוס ותוצאות"
   Preview: enrollment progress, KPIs, coordinator feedback, lessons learned

Each report: "צור דוח" button, "הורד PDF" button, last generated date.

---

### PAGE 6: הגדרות

- פרופיל: שם, תפקיד, מחלקה
- ניהול משתמשים: table of 5 users (name, role, status, last login)
- הגדרות מערכת: סף RDI להתראה (slider, default 1.3), סף SDI להתראה (slider, default 17), תדירות דוחות (dropdown)
- מידע: גרסה 1.0, מרץ 2026

## 🔼 סוף הפרומפט 🔼