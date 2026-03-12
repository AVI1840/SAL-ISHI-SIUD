# Lovable פרומפט 1 — סל אישי: מרקטפלייס שירותים מותאם

> אפליקציה לאזרח הוותיק ומשפחתו — בחירת שירותים מותאמים אישית מתוך קטלוג.
> העתק הכל מתחת לקו ל-Lovable.

---

## 🔽 התחל להעתיק מכאן 🔽

---

Build a complete Hebrew RTL web application: **"סל אישי — שירותי הזדקנות מיטבית מותאמים אישית"**

This is a service marketplace for elderly citizens and their families in Israel. It's part of a national reform by the Israeli National Insurance Institute (ביטוח לאומי) to replace the one-size-fits-all nursing care model with a personalized service basket. The app lets users browse available services across 6 dimensions, see their personalized recommendation, customize their basket, view providers, and track their care plan.

**The story this app tells:** Today, elderly Israelis receiving nursing care get mostly personal care hours (bathing, dressing). 44.6% of those who deteriorated received ZERO additional services. This app shows the future — a rich marketplace of services across 6 life dimensions, personalized to each person's needs, with real providers and real availability.

---

## DESIGN SYSTEM — BTL (ביטוח לאומי, מינהל גמלאות)

### Identity
- Organization: ביטוח לאומי — המוסד לביטוח לאומי
- Department: מינהל גמלאות
- Credit: "אביעד יצחקי, מינהל גמלאות"
- Logo: Circle with "ב"ל" text + "ביטוח לאומי / מינהל גמלאות"

### Colors
- Primary: #0c3058 (headings, headers)
- Secondary: #0368b0 (buttons, links)
- Tertiary: #266794 (secondary text)
- Accent: #e8a020 (gold — highlights, badges, CTAs)
- Background: #f5f9ff
- Surface: #ffffff
- Text: #0c3058
- Muted: #6b7a8d
- Success: #1a7a4e
- Warning: #cc7a00
- Error: #c0392b
- Info bg: #e8f3ff
- Border: rgba(6, 77, 173, 0.1)

### Typography
- Font: 'Heebo', sans-serif (Google Fonts: 300,400,500,600,700,800)
- RTL, Hebrew, h1: 28px/800, h2: 22px/700, h3: 18px/700, Body: 14px/400

### Layout
- Max 1200px centered, Card radius: 12px, Button radius: 8px
- Shadow: 0 2px 8px rgba(6,77,173,0.1)

### Components
- Buttons: bg-[#0368b0] text-white rounded-lg px-4 py-2.5 font-semibold hover:bg-[#025a8f] focus-visible:ring-2 focus-visible:ring-[#0068f5]
- Cards: bg-white border border-black/10 rounded-xl shadow-sm p-5
- Inputs: border border-[#0368b0]/30 rounded-lg px-3 py-2.5 focus:ring-2 focus:ring-[#0068f5]/20
- Header: bg-[#0c3058] text-white
- Footer: bg-[#0c3058] text-white/80 text-sm py-4

### Accessibility (MANDATORY)
- lang="he" dir="rtl", skip nav link, visible labels + aria-label, contrast 4.5:1, focus indicators 2px, keyboard nav, semantic HTML, touch 44x44px, no color-only info

### Tech: React 18+ TypeScript, Vite, Tailwind, shadcn/ui, Heebo, Recharts, Lucide icons, React hooks only, mock data inline

### Footer: "אביעד יצחקי, מינהל גמלאות | ביטוח לאומי | v1.0 | מרץ 2026"

### RULES: Hebrew only, RTL only, government tone, focus-visible on all, labels above inputs, no light-on-light text.

---

## APPLICATION — 6 PAGES

### Navigation (Top navbar + mobile hamburger)
- 🏠 דף הבית
- 🛒 הסל שלי
- 🔍 חיפוש שירותים
- 👤 הפרופיל שלי
- ⭐ ספקים
- 📞 צור קשר

User greeting in header right: "שלום, רחל כהן | רמת גמלה 3"

---

### PAGE 1: דף הבית — "הסל האישי שלך"

**Hero banner:**
- Background: gradient from #0c3058 to #0368b0
- Title: "סל אישי — שירותים מותאמים במיוחד עבורך"
- Subtitle: "על בסיס ההערכה התפקודית שלך, הכנו עבורך סל שירותים מותאם אישית ב-6 ממדי חיים"
- CTA button (gold accent): "צפה בסל המומלץ שלך"

**6 dimension cards in 2x3 grid:**
Each card has: colored icon, dimension name, count of recommended services, short description.

| ממד | צבע | אייקון | שירותים מומלצים | תיאור |
|-----|------|--------|----------------|-------|
| תפקודי | #0368b0 | Heart | 3 | טיפול אישי, עזרה בבית, ליווי |
| חברתי | #e8a020 | Users | 2 | ליווי חברתי, מועדון יום |
| בריאותי | #1a7a4e | Stethoscope | 2 | פיזיותרפיה, ייעוץ תזונתי |
| קוגניטיבי | #8b5cf6 | Brain | 1 | הפעלה קוגניטיבית |
| טכנולוגי | #266794 | Smartphone | 2 | כפתור מצוקה, טלרפואה |
| סביבתי | #cc7a00 | Home | 1 | התאמות דיור |

Click on any card → navigates to filtered service catalog for that dimension.

**"הסל שלך במספרים" section:**
- Radar chart (Recharts RadarChart) showing scores across 6 dimensions (from assessment)
- Next to it: summary card with:
  - סה"כ שירותים בסל: 11
  - ממדים מכוסים: 6/6
  - SDI (מדד מגוון): 72
  - סטטוס: "הסל שלך מגוון ומותאם ✅"

**"מה חדש" section:**
3 cards: new services recently added, seasonal activities, community events.

---

### PAGE 2: חיפוש שירותים (Service Marketplace)

**Top: Search bar** + filter row:
- חיפוש חופשי (text)
- ממד (dropdown: all 6 + "הכל")
- אזור (dropdown: ירושלים, תל אביב, חיפה, באר שבע, פריפריה)
- זמינות (toggle: "זמין עכשיו")
- מיון (dropdown: מומלץ עבורך, דירוג, מרחק, חדש)

**Results: Grid of service cards (2 or 3 columns)**

Each service card:
- Service image placeholder (colored gradient by dimension)
- Dimension badge (colored pill)
- Service name (Hebrew, bold)
- Provider name
- Star rating (1-5) + review count
- Short description (2 lines)
- Availability badge: "זמין" (green) / "רשימת המתנה" (yellow) / "לא זמין באזורך" (gray)
- "הוסף לסל" button (secondary) or "בסל שלך ✓" (success)
- "פרטים נוספים" link

**Mock 24 services (4 per dimension):**

תפקודי:
1. טיפול אישי יומי — חברת "משען" — ⭐4.5 (23 חוות דעת) — זמין
2. עזרה בניהול משק בית — "בית חם" — ⭐4.2 (15) — זמין
3. ליווי לטיפולים רפואיים — "יד ביד" — ⭐4.7 (31) — זמין
4. שירותי הסעות מותאמות — "נתיב זהב" — ⭐4.0 (8) — רשימת המתנה

חברתי:
5. ליווי חברתי שבועי — "חברים לדרך" — ⭐4.8 (42) — זמין
6. מועדון יום לגיל השלישי — מתנ"ס קטמון — ⭐4.3 (19) — זמין
7. קבוצת תמיכה — "לא לבד" — ⭐4.6 (27) — זמין
8. פעילות בין-דורית — "גשר הדורות" — ⭐4.4 (12) — זמין

בריאותי:
9. פיזיותרפיה בבית — "תנועה חופשית" — ⭐4.9 (56) — זמין
10. ריפוי בעיסוק — "ידיים יוצרות" — ⭐4.5 (22) — רשימת המתנה
11. ייעוץ תזונתי — "בריאות בצלחת" — ⭐4.3 (14) — זמין
12. הערכה גריאטרית — קופ"ח כללית — ⭐4.1 (9) — זמין

קוגניטיבי:
13. מרכז יום לדמנציה — "זיכרון בגן" — ⭐4.7 (33) — רשימת המתנה
14. הפעלה קוגניטיבית — "מוח פעיל" — ⭐4.4 (18) — זמין
15. ליווי מותאם דמנציה — "נתיב הזיכרון" — ⭐4.6 (25) — זמין
16. סדנאות זיכרון — "זוכרים יחד" — ⭐4.2 (11) — זמין

טכנולוגי:
17. כפתור מצוקה — "ערנות 24/7" — ⭐4.8 (67) — זמין
18. חיישני נפילה — "שומר הבית" — ⭐4.5 (29) — זמין
19. טלרפואה — "רופא מרחוק" — ⭐4.3 (16) — זמין
20. טאבלט מותאם לגיל השלישי — "קשר קל" — ⭐4.1 (7) — זמין

סביבתי:
21. התאמות דיור — "בית בטוח" — ⭐4.6 (21) — זמין
22. שיפוץ חדר רחצה נגיש — "נגישות פלוס" — ⭐4.4 (13) — רשימת המתנה
23. מעבר לדיור מוגן — "בית שני" — ⭐4.0 (6) — זמין
24. הנגשת כניסה לבניין — "דרך חופשית" — ⭐4.2 (10) — זמין

---

### PAGE 3: דף שירות (Service Detail)

When clicking "פרטים נוספים" on any service card:

**Header:** Service name + dimension badge + rating stars

**Content sections:**
- **תיאור השירות** — 2-3 paragraphs describing the service
- **מה כולל** — bullet list of what's included
- **למי מתאים** — care levels (badges 1-6), conditions
- **ספק** — provider card with: name, logo placeholder, phone, address, website link, rating
- **זמינות** — days/hours, areas served, waiting time
- **חוות דעת** — 3 mock reviews with name (first name only), rating, date, text

**Sidebar (sticky):**
- "הוסף לסל" large button
- "מתאים לפרופיל שלך: 92%" — match score with progress bar
- "שירותים דומים" — 3 small cards

---

### PAGE 4: הסל שלי (My Basket)

**Header:** "הסל האישי שלך — רחל כהן" + last update date

**Basket summary bar:**
- סה"כ שירותים: 11
- ממדים מכוסים: 6/6
- SDI: 72
- סטטוס: "מאושר ✅" (green badge)

**Services grouped by dimension (accordion sections):**
Each dimension section: colored header + count + expand/collapse.
Inside: service cards in list view with: name, provider, status (פעיל/ממתין לאישור/מומלץ), start date, frequency.

**Actions per service:** "הסר מהסל", "החלף ספק", "פרטים"

**Bottom section:**
- "שירותים מומלצים שעוד לא בסל שלך" — 3 cards of recommended services not yet added
- "עדכן את הסל" button
- "שתף עם המתאמת" button
- "הורד PDF" button

---

### PAGE 5: ספקים (Providers)

**Search + filter:** חיפוש שם ספק, סינון לפי ממד, אזור, דירוג מינימלי

**Provider cards grid (2 columns):**
Each card:
- Provider name (bold)
- Logo placeholder (colored circle with initials)
- Category badges (which dimensions they serve)
- Star rating + review count
- Areas served (badges)
- Number of services offered
- "צפה בשירותים" button

**Mock 8 providers:**
1. משען — תפקודי, בריאותי — ⭐4.5 — ירושלים, ת"א — 4 שירותים
2. חברים לדרך — חברתי — ⭐4.8 — ירושלים — 2 שירותים
3. תנועה חופשית — בריאותי — ⭐4.9 — ארצי — 3 שירותים
4. ערנות 24/7 — טכנולוגי — ⭐4.8 — ארצי — 2 שירותים
5. בית בטוח — סביבתי — ⭐4.6 — ירושלים, חיפה — 3 שירותים
6. מוח פעיל — קוגניטיבי — ⭐4.4 — ירושלים, ת"א — 2 שירותים
7. בית חם — תפקודי — ⭐4.2 — ירושלים — 2 שירותים
8. קשר קל — טכנולוגי — ⭐4.1 — ארצי — 1 שירות

---

### PAGE 6: הפרופיל שלי

**Personal info card:** שם, גיל, כתובת, טלפון, איש קשר חירום, רמת גמלה (badge)

**Assessment summary:** Radar chart (6 dimensions) + last assessment date + "בקש הערכה מחודשת" button

**My care team:**
- מתאמת שירות: שרה ישראלי — טלפון — "שלח הודעה"
- רופא/ת משפחה: ד"ר יעל כהן
- איש קשר משפחתי: דוד כהן (בן)

**Activity log:** Last 5 changes to basket with dates

---

### MOCK USER PROFILE
- שם: רחל כהן
- גיל: 82
- מגדר: נקבה
- רמת גמלה: 3
- כתובת: רחוב הרצל 15, ירושלים
- מצב: אלמנה, בן אחד (דוד) בעיר
- Assessment scores: תפקודי 2.5, חברתי 1.8, בריאותי 2.8, קוגניטיבי 3.2, טכנולוגי 1.5, סביבתי 2.0
- SDI: 72
- RDI: 1.12

## 🔼 סוף הפרומפט 🔼