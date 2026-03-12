# פרומפט ל-Lovable — פלטפורמת AI מותאמת לביטוח לאומי

> העתק את כל מה שמתחת לקו ל-Lovable.

---

## 🔽 התחל להעתיק מכאן 🔽

---

Build a complete Hebrew RTL web application: **"בינה — פלטפורמת AI לביטוח לאומי"**

A professional AI-powered platform for the Israeli National Insurance Institute. Unified hub for AI tools, document analysis, data insights, and smart assistants for government social services — elderly care, nursing benefits, welfare.

---

## DESIGN SYSTEM — BTL

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
- Direction: RTL
- Language: Hebrew (all UI text)
- h1: 28px/800, h2: 22px/700, h3: 18px/700
- Body: 14px/400, Small: 12px/400

### Layout
- Max content width: 1200px centered
- Card radius: 12px, Button radius: 8px (pill: 9999px)
- Spacing: 4, 8, 12, 16, 20, 24, 32, 40, 48
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

### Footer
"אביעד יצחקי, מינהל גמלאות | ביטוח לאומי | v1.0 | מרץ 2026"

### RULES
1. ALL UI text Hebrew. Zero English in interface.
2. ALL layout RTL. No exceptions.
3. Government/Professional tone. Clean, trustworthy.
4. Every interactive element: focus-visible styles.
5. Labels above inputs. Required fields: asterisk.
6. Never light text on light backgrounds.

---

## APPLICATION — 7 PAGES

### Navigation (Sidebar RIGHT side — RTL)
Collapsible sidebar:
1. 🏠 דף הבית
2. 💬 עוזר AI
3. 📄 ניתוח מסמכים
4. 📊 תובנות נתונים
5. 🧰 ארגז כלים
6. 📚 בסיס ידע
7. ⚙️ הגדרות


---

### PAGE 1: דף הבית

**Hero:** "שלום, אביעד 👋" + Hebrew date. Subtitle: "מה תרצה לעשות היום?"

3 quick-action cards in a row:
- "שאל את הבינה" → Chat (icon: MessageSquare, gold accent border)
- "נתח מסמך" → Document Analyzer (icon: FileSearch)
- "צפה בתובנות" → Data Insights (icon: TrendingUp)

**Stats row — 4 cards:**
- שיחות AI החודש: 142 (MessageSquare)
- מסמכים שנותחו: 38 (FileSearch)
- תובנות שנוצרו: 17 (Lightbulb)
- כלים בשימוש: 8 (Wrench)

**Recent activity** — timeline list, 8 items with icon + description + relative time:
- "ניתוח נייר מדיניות סל אישי" — לפני שעתיים
- "שיחה: מדדי הדרדרות RDI" — לפני 5 שעות
- "יצירת סיכום ישיבה" — אתמול
- "ניתוח 3 תיקי סיעוד" — אתמול
- "השוואת מודלים בינלאומיים" — לפני יומיים
- "כתיבת טיוטת קול קורא" — לפני 3 ימים
- "ניתוח נתוני SDI לפי רמות" — לפני 4 ימים
- "תרגום מאמר OECD" — לפני שבוע

**Quick tools grid — 6 cards:**
סיכום ישיבה (ClipboardList), כתיבת מסמך מדיניות (FileText), ניתוח נתונים (BarChart3), תרגום מסמך (Languages), יצירת מצגת (Presentation), השוואת מסמכים (GitCompare)

---

### PAGE 2: עוזר AI

Chat interface — messages area + input bottom.

**Header:** "בינה — עוזר AI" + context dropdown: כללי | סל אישי בסיעוד | מדדי הדרדרות | רגולציה וחקיקה | פיילוט ירושלים

**Messages:**
- Bot: bg-[#e8f3ff] rounded-xl p-4, right-aligned
- User: bg-[#0368b0] text-white rounded-xl p-4, left-aligned

**Mock conversation:**

Bot: "שלום! אני בינה, העוזר החכם של ביטוח לאומי. אפשר לשאול אותי על מדיניות סיעוד, מדדי הדרדרות, פיילוטים, או כל נושא אחר. במה אוכל לעזור?"

User: "מה המצב של מדד ה-RDI אצל נשים מעל 85?"

Bot: "לפי הנתונים העדכניים (פברואר 2026):

נשים 85+ ברמת גמלה 1:
• RDI = 1.49 (חריג — מעל סף 1.5)
• שהות ממוצעת: 40.3 חודשים
• Benchmark (חציון רמה 1): כ-27 חודשים

זו הקבוצה עם ה-RDI הגבוה ביותר. המשמעות: נשים מבוגרות שוהות זמן רב ברמה 1 לפני שמזהים הדרדרות.

המלצה: הגברת תדירות הערכות בקבוצה זו."

**Input:** text field + send (Arrow) + attachment (Paperclip) + mic (Mic)

**Suggested chips above input:** "סכם את נייר המדיניות" | "מה הסטטוס של הפיילוט?" | "הסבר את מדד SDI" | "מה הצעדים הבאים?"

---

### PAGE 3: ניתוח מסמכים

**Upload zone:** dashed border, "גרור מסמך לכאן או לחץ להעלאה", formats: PDF/DOCX/XLSX/PPTX

**After upload — split view:**
- Left 40%: document preview (icon + name + "12 עמודים")
- Right 60%: 5 tabs:
  - **סיכום** — 3 Hebrew paragraphs summarizing the policy paper
  - **נקודות מפתח** — 6 bullet points about the reform
  - **נתונים** — table: מדד | ערך | מקור (rows: SDI=0 at 44.6%, RDI women 85+=1.49, etc.)
  - **המלצות** — 4 numbered action items
  - **שאלות** — 5 suggested follow-up questions

**Mock document:** "נייר מדיניות סל תפקוד אישי 1.2025


---

### PAGE 2: עוזר AI

Chat interface — messages area + input bottom.

Header: "בינה — עוזר AI" + context dropdown: כללי | סל אישי בסיעוד | מדדי הדרדרות | רגולציה וחקיקה | פיילוט ירושלים

Bot messages: bg-[#e8f3ff] rounded-xl p-4, right-aligned. User messages: bg-[#0368b0] text-white rounded-xl p-4, left-aligned.

Mock conversation — Bot greets, user asks about RDI for women 85+, bot responds with real data (RDI=1.49, benchmark 27 months, recommendation to increase assessments).

Input: text field + send + attachment + mic buttons. Suggested chips: "סכם את נייר המדיניות", "מה הסטטוס של הפיילוט?", "הסבר את מדד SDI", "מה הצעדים הבאים?"

---

### PAGE 3: ניתוח מסמכים

Upload zone: dashed border drop area, supports PDF/DOCX/XLSX/PPTX.

After upload — split view: Left 40% document preview, Right 60% AI analysis in 5 tabs: סיכום (3 paragraphs), נקודות מפתח (6 bullets), נתונים (stats table), המלצות (4 items), שאלות (5 questions).

Mock analyzed doc: "נייר מדיניות סל תפקוד אישי 1.2025" with realistic Hebrew content about the reform.

Recent documents table below: 5 entries (name, type, date, status).

---

### PAGE 4: תובנות נתונים

3 insight cards top row:

Card 1 "מגמת הדרדרות": Line chart — RDI 6-month trend (slight increase). Text: "עלייה של 8% ב-RDI הממוצע". Badge: 🔴 דורש תשומת לב

Card 2 "מגוון שירותים": Donut chart — SDI=0 (44.6%), SDI=17 (41.3%), SDI>33 (14.1%). Text: "44.6% ללא שירותים מעבר לטיפול אישי". Badge: 🟡 לבדיקה

Card 3 "פיילוט ירושלים": Progress bar 65%. Text: "12 מתוך 20 תיקים הושלמו". Badge: 🟢 בתהליך

Full-width area chart: "התפלגות רמות גמלה לאורך זמן" (6 months, stacked by levels 1-6).

Bottom: "תובנות AI אחרונות" — 5 cards with title, description, source badge, date.

---

### PAGE 5: ארגז כלים

Grid of 12 tool cards (3 columns x 4 rows). Each card: icon, Hebrew name, description, "הפעל" button.

Row 1 — מסמכים:
- 📝 סיכום ישיבה: "הזן פרוטוקול וקבל סיכום מובנה עם משימות"
- 📄 כתיבת מסמך: "צור מסמך מדיניות, נייר עמדה, או דוח"
- 📋 תבנית דוח: "מלא תבנית דוח מנהלים מובנית"

Row 2 — ניתוח:
- 📊 ניתוח נתונים: "העלה Excel וקבל תובנות אוטומטיות"
- 🔍 השוואת מסמכים: "השווה שתי גרסאות ומצא הבדלים"
- 📈 יצירת גרפים: "הפוך נתונים לויזואליזציה ברורה"

Row 3 — תקשורת:
- 🌐 תרגום מסמך: "תרגם מסמך מאנגלית לעברית או להפך"
- ✉️ כתיבת מכתב: "צור מכתב רשמי בשפה ממשלתית"
- 🎤 תמלול ישיבה: "העלה הקלטה וקבל תמלול מובנה"

Row 4 — מתקדם:
- 🧠 ניתוח תיק סיעוד: "נתח תיק מטופל והפק פרסונה"
- 📐 אפיון מערכת: "צור מסמך אפיון טכני מובנה"
- 🎯 תכנית עבודה: "בנה תכנית עבודה עם אבני דרך ולוחות זמנים"

When clicking "הפעל" on any tool — open a modal/sheet with: title, description, input area (textarea or file upload), and "הפעל כלי" button. Show mock output below.

---

### PAGE 6: בסיס ידע

Search bar at top: "חפש בבסיס הידע..."

Categories as tabs: הכל | מדיניות | מחקר | רגולציה | פיילוטים | טכנולוגיה

Grid of knowledge cards (2 columns). Each card:
- Document icon by type (PDF/DOCX/XLSX)
- Title in Hebrew
- Category badge (colored)
- Date
- Short description (1 line)
- "פתח" button

Mock 10 entries:
1. נייר מדיניות סל אישי 1.2025 | מדיניות | ינואר 2025
2. תוצר EY סופי — מחקר שטח | מחקר | דצמבר 2024
3. מדדי הדרדרות — RDI + SDI | מחקר | פברואר 2026
4. טיוטת לוח ח-2 | רגולציה | מאי 2025
5. קול קורא לרשויות מקומיות גרסה 2 | רגולציה | נובמבר 2025
6. הצעת פיילוטים גרסה 6 | פיילוטים | 2025
7. ספר הפעלה עכשיו אני ירושלים | פיילוטים | 2025
8. אפיון MVP מערכת מתאמות | טכנולוגיה | מרץ 2026
9. מסמך דרישות עסקיות | טכנולוגיה | 2025
10. סיכום סדנת עיצוב שירות | מחקר | נובמבר 2024

---

### PAGE 7: הגדרות

Simple settings page with sections:

**פרופיל:** שם, תפקיד, מחלקה (read-only display with edit button)

**העדפות AI:** 
- סגנון תשובות: select (מקצועי / ידידותי / תמציתי)
- אורך תשובות: select (קצר / בינוני / מפורט)
- שפת ברירת מחדל: עברית (disabled)

**התראות:**
- Toggle switches: התראות מייל, התראות במערכת, סיכום יומי

**מידע:**
- גרסה: 1.0
- עדכון אחרון: מרץ 2026
- "אביעד יצחקי, מינהל גמלאות | ביטוח לאומי"

---

### IMPORTANT IMPLEMENTATION NOTES
- Use Recharts for all charts (LineChart, BarChart, DonutChart/PieChart, AreaChart)
- Use Lucide React icons throughout
- Sidebar on RIGHT (RTL layout)
- All dates Hebrew format: "15 במרץ 2026"
- Responsive: desktop 1200px + tablet 768px
- shadcn/ui Sheet for mobile sidebar
- Toast notifications for actions
- Loading skeletons for data sections
- Smooth page transitions

## 🔼 סוף הפרומפט 🔼