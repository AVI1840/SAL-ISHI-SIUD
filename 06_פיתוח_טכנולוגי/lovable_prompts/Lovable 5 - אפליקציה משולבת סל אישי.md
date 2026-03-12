# Lovable פרומפט 5 — אפליקציה משולבת: סל אישי בסיעוד

> אפליקציה אחת עם 4 מודולים נפרדים — לזקנים, למתאמות, לניהול, ולבינה AI.
> כל מודול עצמאי אך משתף Design System, ניווט ונתונים.
> העתק הכל מתחת לקו ל-Lovable.

---

## 🔽 התחל להעתיק מכאן 🔽

---

Build a complete Hebrew RTL web application: **"סל אישי — מערכת רפורמת סיעוד לביטוח לאומי"**

A unified platform with 4 modules for Israel's nursing care reform. Each module serves a different user type but shares the same design system, data layer, and navigation shell. The app has a module switcher that lets users move between modules.

**The 4 modules:**
1. **סל אישי** — Marketplace for elderly citizens and families. Browse services, build personalized basket, view providers.
2. **מתאמת** — Care coordinator dashboard. Manage patients, build baskets, monitor deterioration (RDI/SDI), coordinate providers.
3. **מנהל** — Management dashboard. National overview, municipalities, providers, KPIs, reform timeline.
4. **בינה** — AI platform. Chat assistant, document analysis, data insights, 12 AI tools, knowledge base.

**The story:** Israel's nursing care system gives elderly people mostly personal care hours. 44.6% of those who deteriorated at care level 1 received ZERO additional services. This reform introduces a personalized service basket across 6 life dimensions (functional, social, health, cognitive, technological, environmental), with care coordinators, AI tools, and a management layer. The pilot runs in Jerusalem ("עכשיו אני"), expanding to 3-5 municipalities.

---

## DESIGN SYSTEM — BTL (ביטוח לאומי, מינהל גמלאות)

### Identity
- Organization: ביטוח לאומי — המוסד לביטוח לאומי
- Department: מינהל גמלאות
- Credit: "אביעד יצחקי, מינהל גמלאות"
- Logo: Circle with "ב"ל" text + "ביטוח לאומי / מינהל גמלאות"

### Colors
- Primary: #0c3058 (darkest blue — headings, headers)
- Secondary: #0368b0 (action blue — buttons, links)
- Tertiary: #266794 (medium blue — secondary text)
- Accent: #e8a020 (gold — highlights, badges, CTAs)
- Background: #f5f9ff (light blue-white)
- Surface: #ffffff
- Text: #0c3058
- Muted: #6b7a8d
- Success: #1a7a4e
- Warning: #cc7a00
- Error: #c0392b
- Info background: #e8f3ff
- Border: rgba(6, 77, 173, 0.1)

### Typography
- Font: 'Heebo', sans-serif (Google Fonts: weights 300,400,500,600,700,800)
- Direction: RTL. Language: Hebrew (all UI text)
- h1: 28px/800, h2: 22px/700, h3: 18px/700, Body: 14px/400, Small: 12px/400

### Layout
- Max content width: 1200px centered
- Card radius: 12px, Button radius: 8px (pill: 9999px)
- Shadow: 0 2px 8px rgba(6,77,173,0.1)

### Components
- Buttons: bg-[#0368b0] text-white rounded-lg px-4 py-2.5 font-semibold hover:bg-[#025a8f] focus-visible:ring-2 focus-visible:ring-[#0068f5] focus-visible:ring-offset-2
- Cards: bg-white border border-black/10 rounded-xl shadow-sm p-5
- Inputs: border border-[#0368b0]/30 rounded-lg px-3 py-2.5 text-[#0c3058] focus:border-[#0068f5] focus:ring-2 focus:ring-[#0068f5]/20
- Badges: inline-flex px-3 py-1 rounded-full text-xs font-bold
- Header: bg-[#0c3058] text-white
- Footer: bg-[#0c3058] text-white/80 text-sm py-4

### Accessibility (MANDATORY)
- lang="he" dir="rtl" on html
- Skip navigation link as first focusable element
- All form inputs: visible Hebrew label + aria-label
- Color contrast: min 4.5:1 normal, 3:1 large
- Focus indicators: visible 2px outline on ALL interactive elements
- Keyboard navigation: Tab/Enter/Space/Arrows
- Semantic HTML: heading hierarchy, landmarks
- Touch targets: min 44x44px mobile
- No content conveyed by color alone

### Tech Stack
- React 18+ TypeScript, Vite, Tailwind CSS, shadcn/ui, Heebo font, Recharts, Lucide React icons
- All state in React hooks, mock data inline, no API calls
- React Router for navigation between modules and pages

### Footer
"אביעד יצחקי, מינהל גמלאות | ביטוח לאומי | v1.0 | מרץ 2026"

### RULES
- ALL UI text Hebrew. Zero English in interface.
- ALL layout RTL. No exceptions.
- Government/Professional tone. Clean, trustworthy.
- Every interactive element: focus-visible styles.
- Labels above inputs. Required fields: asterisk.
- Never light text on light backgrounds.

---

## APP SHELL — MODULE SWITCHER

### Top Header (fixed, bg-[#0c3058] text-white, h-16)
- Right side: Logo "ב"ל" circle + "סל אישי" text
- Center: Module switcher — 4 tabs/buttons:
  - 🛒 סל אישי (marketplace)
  - 👩‍⚕️ מתאמת (coordinator)
  - 📊 מנהל (management)
  - 🧠 בינה (AI)
- Active module: bg-white/20 rounded-lg px-4 py-1.5 font-bold
- Left side: user avatar + name + role dropdown

### Module-specific sidebar (RIGHT side, RTL)
Each module has its own sidebar navigation (see below). Sidebar collapses on tablet/mobile.

---

## MODULE 1: סל אישי — מרקטפלייס לאזרח הוותיק

**User persona:** רחל כהן, 82, רמת גמלה 3, ירושלים. אלמנה, בן אחד בעיר.
**Sidebar navigation:**
🏠 דף הבית | 🔍 חיפוש שירותים | 🛒 הסל שלי | ⭐ ספקים | 👤 הפרופיל שלי | 📞 צור קשר

### Page 1.1: דף הבית — "הסל האישי שלך"
- Hero: gradient #0c3058→#0368b0, "סל אישי — שירותים מותאמים במיוחד עבורך", CTA gold "צפה בסל המומלץ שלך"
- 6 dimension cards (2x3): תפקודי (#0368b0, Heart, 3 שירותים), חברתי (#e8a020, Users, 2), בריאותי (#1a7a4e, Stethoscope, 2), קוגניטיבי (#8b5cf6, Brain, 1), טכנולוגי (#266794, Smartphone, 2), סביבתי (#cc7a00, Home, 1). Click → filtered catalog.
- Radar chart (6 dimensions from assessment) + summary: 11 שירותים, 6/6 ממדים, SDI 72, "הסל שלך מגוון ✅"
- "מה חדש" — 3 cards: new services, seasonal activities, community events

### Page 1.2: חיפוש שירותים
- Search + filters: ממד, אזור, זמינות toggle, מיון (מומלץ/דירוג/מרחק/חדש)
- 24 service cards (4 per dimension) in grid. Each: dimension badge, name, provider, ⭐ rating + reviews, availability badge (זמין/רשימת המתנה/לא זמין), "הוסף לסל"/"בסל שלך ✓", "פרטים נוספים"
- Mock services: טיפול אישי יומי (משען ⭐4.5), ליווי חברתי (חברים לדרך ⭐4.8), פיזיותרפיה בבית (תנועה חופשית ⭐4.9), כפתור מצוקה (ערנות 24/7 ⭐4.8), התאמות דיור (בית בטוח ⭐4.6), הפעלה קוגניטיבית (מוח פעיל ⭐4.4), etc.

### Page 1.3: דף שירות (detail)
- Service name + dimension badge + rating. תיאור, מה כולל (bullets), למי מתאים (care level badges), ספק card, זמינות, 3 חוות דעת
- Sidebar sticky: "הוסף לסל" + match score "מתאים לפרופיל שלך: 92%" + 3 similar services

### Page 1.4: הסל שלי
- Header: "הסל האישי שלך — רחל כהן" + stats bar (11 שירותים, 6/6 ממדים, SDI 72, מאושר ✅)
- Services grouped by dimension (accordion). Each: name, provider, status badge, start date, frequency. Actions: הסר, החלף ספק, פרטים
- Bottom: 3 recommended services not in basket + "עדכן סל" + "שתף עם המתאמת" + "הורד PDF"

### Page 1.5: ספקים
- Search + filter by ממד, אזור, דירוג. 8 provider cards: name, logo circle, dimension badges, ⭐ rating, areas, service count, "צפה בשירותים"

### Page 1.6: הפרופיל שלי
- Personal info card + radar chart (6 dimensions) + care team (מתאמת, רופאה, בן) + activity log (5 items)

---

## MODULE 2: מתאמת — ניהול מטופלים וסלים

**User persona:** שרה ישראלי, מתאמת שירות, פיילוט ירושלים. מנהלת 28 מטופלים.
**Sidebar navigation:**
🏠 דשבורד | 👥 מטופלים | ➕ קליטה חדשה | 📊 הדרדרות | 🤝 ספקים ותיאום | 📋 דוחות | ⚙️ הגדרות

### Page 2.1: דשבורד
- 5 stat cards: המטופלים שלי (28), התראות פתוחות (5, accent), ממתינים לסל (3), SDI ממוצע (24.3), ביקורים השבוע (7)
- Left column: "דורשים תשומת לב" — 5 patients sorted by urgency (לאה שמעון RDI 1.52 🔴, שרה אברהם RDI 1.49 SDI 0 🔴, etc.)
- Right column: "לוח משימות היום" — 6 checklist items with times
- Bottom: bar chart "התפלגות מטופלים לפי רמת גמלה"

### Page 2.2: רשימת מטופלים
- Search + filters. Table: שם, גיל, מגדר, רמה, RDI (color-coded), SDI (color-coded), שירותים בסל, מעקב אחרון, סטטוס, פעולות
- 12 mock patients with real-feeling data. RDI colors: green <1.2, yellow 1.2-1.5, red >1.5. SDI: red 0, yellow 1-17, green >17

### Page 2.3: כרטיס מטופל (5 tabs)
- Tab פרופיל: personal details 2-column
- Tab הערכה: radar chart (6 dimensions, 1-4 scale) + 6 detail cards + assessment history
- Tab סל אישי: basket by dimension (accordion), each service with provider/status/date. "ערוך סל", SDI indicator, missing recommendations
- Tab מעקב: vertical timeline of follow-ups + "הוסף מעקב" modal
- Tab מדדים: RDI line chart (6 months) + SDI line chart + RDI×SDI matrix position + alert history

### Page 2.4: קליטה חדשה (4-step wizard)
- Step 1 פרטים אישיים: form with name, ID, DOB, gender, address, phone, emergency contact, care level, family status
- Step 2 הערכה תפקודית: 6 sections with sliders (1-4) per sub-item. Live radar chart updating
- Step 3 המלצת סל: auto-generated services based on level+scores. Checkboxes grouped by dimension. Live SDI
- Step 4 סיכום: all data + basket + "אשר וצור תיק"

### Page 2.5: ספקים ותיאום
- Section 1: provider table (8 providers with dimensions, area, rating, active patients, status)
- Section 2: open coordinations table (5 pending: patient, service, provider, status, date, actions)

### Page 2.6: דוחות
- 4 report cards: דוח שבועי, דוח הדרדרות (RDI×SDI scatter + demographics), דוח SDI (donut + bar by level), דוח KPIs פיילוט (6 KPI cards)

### Page 2.7: דשבורד הדרדרות
- Stats: RDI>1.3 count, SDI=0 count, RDI average
- Main: RDI×SDI scatter chart (each dot = patient, colored zones red/yellow/green)
- Below: filtered table of red-zone patients
- Bottom: 2 bar charts — "RDI לפי מגדר וגיל" (6 bars, real data) + "SDI לפי רמת גמלה" (5 bars, real data)

---

## MODULE 3: מנהל — פאנל ניהול רפורמה

**User persona:** אביעד יצחקי, מנהל רפורמת סל אישי, מינהל גמלאות.
**Sidebar navigation:**
🏠 דשבורד ארצי | 🏛️ רשויות מקומיות | 🏢 ספקי שירות | 📊 מדדים ו-KPIs | 📋 דוחות | ⚙️ הגדרות

### Page 3.1: דשבורד ארצי
- Hero: "רפורמת סל אישי — מבט על" + phase indicator "שלב 1: פיילוט ירושלים" (65%)
- 6 stat cards: רשויות פעילות (1/5), ספקים (24), מתאמות (5), מטופלים (28), SDI ממוצע (24.3), RDI ממוצע (1.14)
- Reform timeline (horizontal stepper, 9 milestones, 5 completed, 1 in progress, 3 pending)
- Left: pilot map (5 cities with status pins). Right: 4 mini KPI charts

### Page 3.2: רשויות מקומיות
- Table: 5 municipalities (ירושלים 🟢 פעיל, ת"א 🟡 בתכנון, חיפה 🟡 בתכנון, באר שבע ⚪ ממתין, נצרת ⚪ ממתין)
- Click Jerusalem → detail: stats, coordinators list, top providers, KPIs vs targets, activity timeline

### Page 3.3: ספקי שירות
- Search + filters. Table: 12 providers with dimensions, areas, rating, active patients, services, status
- Click → detail: contact, services, coverage, reviews, performance
- Bottom: "התפלגות ספקים לפי ממד" bar chart

### Page 3.4: מדדים ו-KPIs
- 8 KPI cards (2x4): זמן בניית סל (25 דק), שביעות רצון (4.2/5), SDI ממוצע (24.3), שימוש במערכת (85%), דיוק המלצות (73%), התראות <48h (91%), SDI=0 (3.6%), שיעור הדרדרות (12%)
- Multi-line trend chart + pilot vs control comparison bar chart

### Page 3.5: דוחות
- 4 report types: סטטוס רפורמה, הדרדרות ארצי, ספקים, פיילוט ירושלים. Each with "צור דוח" + "הורד PDF"

### Page 3.6: הגדרות
- Profile, user management (5 users table), system settings (RDI/SDI thresholds, report frequency), version info

---

## MODULE 4: בינה — פלטפורמת AI

**User persona:** אביעד יצחקי (same as מנהל, but AI-focused workspace).
**Sidebar navigation:**
🏠 דף הבית | 💬 עוזר AI | 📄 ניתוח מסמכים | 📊 תובנות נתונים | 🧰 ארגז כלים | 📚 בסיס ידע | ⚙️ הגדרות

### Page 4.1: דף הבית
- Hero: "שלום, אביעד 👋" + Hebrew date + "מה תרצה לעשות היום?"
- 3 quick-action cards: "שאל את הבינה" (gold border), "נתח מסמך", "צפה בתובנות"
- 4 stat cards: שיחות AI (142), מסמכים שנותחו (38), תובנות (17), כלים בשימוש (8)
- Recent activity timeline (8 items with icons + relative time)
- Quick tools grid (6 cards)

### Page 4.2: עוזר AI
- Chat interface. Header: "בינה — עוזר AI" + context dropdown (כללי, סל אישי, מדדי הדרדרות, רגולציה, פיילוט ירושלים)
- Bot messages: bg-[#e8f3ff] right-aligned. User: bg-[#0368b0] white left-aligned.
- Mock conversation: bot greets → user asks about RDI women 85+ → bot responds with data table (RDI=1.49, benchmark 27 months) → user asks about SDI → bot responds (44.6% SDI=0, reform context, caveat about control group)
- Input: text + send + attachment + mic. 4 suggested chips above input.

### Page 4.3: ניתוח מסמכים
- Upload zone (dashed border, PDF/DOCX/XLSX/PPTX)
- Split view: left 40% doc preview ("נייר מדיניות סל תפקוד אישי 1.2025", 18 pages), right 60% with 5 tabs: סיכום (3 paragraphs), נקודות מפתח (6 bullets), נתונים (6-row table), המלצות (4 items), שאלות (5 clickable questions)
- Recent documents table (5 entries)

### Page 4.4: תובנות נתונים
- 3 insight cards: מגמת הדרדרות (line chart RDI 6 months, 🔴), מגוון שירותים (donut SDI distribution, 🟡), פיילוט ירושלים (progress 65%, 🟢)
- Full-width stacked area chart: care levels over 6 months
- "תובנות AI אחרונות" — 5 cards with severity badges

### Page 4.5: ארגז כלים
- 12 tool cards (3x4 grid): סיכום ישיבה, כתיבת מסמך, תבנית דוח, ניתוח נתונים, השוואת מסמכים, יצירת גרפים, תרגום מסמך, כתיבת מכתב, תמלול ישיבה, ניתוח תיק סיעוד, אפיון מערכת, תכנית עבודה
- Click "הפעל" → modal with input (textarea or file upload) + "הפעל כלי" + mock output

### Page 4.6: בסיס ידע
- Search + category tabs (הכל, מדיניות, מחקר, רגולציה, פיילוטים, טכנולוגיה)
- 10 knowledge cards (2 columns): doc icon by type, title, category badge, date, description, "פתח"

### Page 4.7: הגדרות
- Profile (read-only + edit), AI preferences (style, length, language, context), notifications (3 toggles), version info

---

## SHARED DATA LAYER

All modules share the same mock data objects so cross-references work:

**patients[]** — 12 patients used in Module 1 (רחל כהן's perspective) and Module 2 (coordinator view)
**providers[]** — 12 providers appearing in all modules
**services[]** — 24 services across 6 dimensions
**metrics** — RDI/SDI data from real research (RDI women 85+ = 1.49, SDI=0 at 44.6% level 1, etc.)
**documents[]** — 10 knowledge base entries used in Module 4
**kpis** — 8 KPIs used in Modules 2, 3, 4

---

## IMPLEMENTATION NOTES

1. **Module switcher** in top header persists across all pages. Active module highlighted.
2. **Sidebar** changes per module. Each module has its own route prefix: /marketplace/*, /coordinator/*, /management/*, /ai/*
3. **Recharts** for all charts. **Lucide React** for all icons.
4. **All dates** Hebrew format: "15 במרץ 2026"
5. **Responsive:** Desktop 1200px, tablet 768px (sidebar collapses), mobile (sidebar = Sheet from right)
6. **shadcn/ui** components: Tabs, Select, Dialog, Sheet, Switch, Toast, Skeleton, Table, Badge, Button, Input, Textarea
7. **Toast** notifications for all actions
8. **Loading skeletons** on page transitions
9. **Cross-module links:** clicking a patient in Module 3 can navigate to Module 2's patient card. Clicking a document in Module 4 insights can open in Module 4 document analysis.
10. **No API calls.** All data is mock, inline, in TypeScript files.

## 🔼 סוף הפרומפט 🔼
