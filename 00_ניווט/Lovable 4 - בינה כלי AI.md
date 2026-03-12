# Lovable פרומפט 4 — בינה: פלטפורמת AI לביטוח לאומי

> כלי AI חכם — צ'אט, ניתוח מסמכים, תובנות נתונים, ארגז כלים, בסיס ידע.
> העתק הכל מתחת לקו ל-Lovable.

---

## 🔽 התחל להעתיק מכאן 🔽

---

Build a complete Hebrew RTL web application: **"בינה — פלטפורמת AI לביטוח לאומי"**

A professional AI-powered platform for the Israeli National Insurance Institute. Unified hub for AI tools, document analysis, data insights, and smart assistants for government social services — elderly care, nursing benefits, welfare.

**The story:** The nursing care reform ("סל אישי בסיעוד") generates hundreds of documents — policy papers, research, metrics, pilot reports, regulations. "בינה" makes all this knowledge instantly accessible through AI. Ask a question about RDI deterioration metrics, upload a policy document for instant analysis, view data insights with charts, or use one of 12 specialized tools to generate summaries, reports, and plans. It's the intelligence layer of the reform — the brain that connects all the data and makes it actionable for policy makers, care coordinators, and reform managers.

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
- ALL UI text Hebrew. Zero English in interface.
- ALL layout RTL. No exceptions.
- Government/Professional tone. Clean, trustworthy.
- Every interactive element: focus-visible styles.
- Labels above inputs. Required fields: asterisk.
- Never light text on light backgrounds.

---

## APPLICATION — 7 PAGES

### Navigation (Sidebar on RIGHT side — RTL)

Collapsible sidebar pinned to the RIGHT of the screen (this is RTL). Top of sidebar: logo circle "ב"ל" + "בינה" text. User avatar + "אביעד יצחקי" below logo. Navigation items:

1. 🏠 דף הבית
2. 💬 עוזר AI
3. 📄 ניתוח מסמכים
4. 📊 תובנות נתונים
5. 🧰 ארגז כלים
6. 📚 בסיס ידע
7. ⚙️ הגדרות

Active page: bg-[#0368b0]/10 text-[#0368b0] font-bold with right border accent (4px #0368b0).
Hover: bg-[#f5f9ff].
Collapsed state: icons only, tooltip on hover.
Mobile: shadcn/ui Sheet sliding from right.

---

### PAGE 1: דף הבית

**Hero section:**
- Greeting: "שלום, אביעד 👋" (h1, 28px/800)
- Hebrew date below: "יום ראשון, 8 במרץ 2026" (14px, muted color #6b7a8d)
- Subtitle: "מה תרצה לעשות היום?" (h2, 22px/700)

**3 quick-action cards in a row (equal width, gap-4):**

| Card | Icon (Lucide) | Title | Border |
|------|---------------|-------|--------|
| "שאל את הבינה" | MessageSquare | navigates to עוזר AI | border-r-4 border-[#e8a020] (gold accent) |
| "נתח מסמך" | FileSearch | navigates to ניתוח מסמכים | border-r-4 border-[#0368b0] |
| "צפה בתובנות" | TrendingUp | navigates to תובנות נתונים | border-r-4 border-[#1a7a4e] |

Each card: bg-white, rounded-xl, shadow-sm, p-5, hover:shadow-md transition, cursor-pointer. Icon 32px in colored circle bg. Title 18px/700. Short description below in muted text.

**Stats row — 4 cards (equal width, gap-4):**

| Stat | Value | Icon (Lucide) | Color |
|------|-------|---------------|-------|
| שיחות AI החודש | 142 | MessageSquare | #0368b0 |
| מסמכים שנותחו | 38 | FileSearch | #266794 |
| תובנות שנוצרו | 17 | Lightbulb | #e8a020 |
| כלים בשימוש | 8 | Wrench | #1a7a4e |

Each stat card: bg-white, rounded-xl, p-4. Icon in colored circle (40px). Value in h2 (22px/700). Label below in muted 12px. Subtle +X% change indicator in green/red.

**Recent activity — timeline list, 8 items:**

Vertical timeline with colored dots on the right side (RTL). Each item: icon (16px, in colored circle), description text (14px), relative time (12px, muted, left-aligned).

| # | Icon | Description | Time |
|---|------|-------------|------|
| 1 | FileSearch | "ניתוח נייר מדיניות סל אישי" | לפני שעתיים |
| 2 | MessageSquare | "שיחה: מדדי הדרדרות RDI" | לפני 5 שעות |
| 3 | ClipboardList | "יצירת סיכום ישיבה" | אתמול |
| 4 | FileSearch | "ניתוח 3 תיקי סיעוד" | אתמול |
| 5 | GitCompare | "השוואת מודלים בינלאומיים" | לפני יומיים |
| 6 | FileText | "כתיבת טיוטת קול קורא" | לפני 3 ימים |
| 7 | BarChart3 | "ניתוח נתוני SDI לפי רמות" | לפני 4 ימים |
| 8 | Languages | "תרגום מאמר OECD" | לפני שבוע |

**Quick tools grid — 6 cards (3x2 grid, gap-4):**

| Icon (Lucide) | Name | Description |
|---------------|------|-------------|
| ClipboardList | סיכום ישיבה | "הזן פרוטוקול וקבל סיכום מובנה" |
| FileText | כתיבת מסמך מדיניות | "צור מסמך מדיניות מקצועי" |
| BarChart3 | ניתוח נתונים | "העלה נתונים וקבל תובנות" |
| Languages | תרגום מסמך | "תרגם מאנגלית לעברית או להפך" |
| Presentation | יצירת מצגת | "הפוך תוכן למצגת מובנית" |
| GitCompare | השוואת מסמכים | "השווה גרסאות ומצא הבדלים" |

Each card: bg-white, rounded-xl, p-4, hover:shadow-md, cursor-pointer. Icon 24px in muted circle. Name 14px/600. Description 12px muted. Click navigates to ארגז כלים with that tool pre-selected.

---

### PAGE 2: עוזר AI

**Header bar:** Title "בינה — עוזר AI" (h2, right side). Left side: context dropdown (shadcn/ui Select):
- כללי (default)
- סל אישי בסיעוד
- מדדי הדרדרות
- רגולציה וחקיקה
- פיילוט ירושלים

**Chat area (flex-grow, scrollable):**

Messages layout:
- Bot messages: bg-[#e8f3ff] rounded-xl p-4, aligned to RIGHT (RTL). Small bot avatar circle (ב) on the right edge.
- User messages: bg-[#0368b0] text-white rounded-xl p-4, aligned to LEFT. Small user avatar circle on the left edge.
- Timestamp below each message: 12px, muted, "14:32" format.

**Mock conversation (render all these messages on load):**

**Bot message 1:**
"שלום! אני בינה, העוזר החכם של ביטוח לאומי. אפשר לשאול אותי על מדיניות סיעוד, מדדי הדרדרות, פיילוטים, או כל נושא אחר. במה אוכל לעזור?"

**User message 1:**
"מה המצב של מדד ה-RDI אצל נשים מעל 85?"

**Bot message 2:**
"לפי הנתונים העדכניים (פברואר 2026):

נשים 85+ ברמת גמלה 1:
• RDI = 1.49 (חריג — מעל סף 1.5)
• שהות ממוצעת: 40.3 חודשים
• Benchmark (חציון רמה 1): כ-27 חודשים

זו הקבוצה עם ה-RDI הגבוה ביותר בכל הרמות. המשמעות: נשים מבוגרות שוהות זמן רב משמעותית ברמה 1 לפני שמזהים הדרדרות.

המלצה: הגברת תדירות הערכות בקבוצה זו ושילוב מעקב טכנולוגי (חיישנים, טלרפואה)."

Render this bot message with a small inline table inside the message bubble:

| מדד | ערך | סטטוס |
|-----|-----|-------|
| RDI | 1.49 | 🔴 חריג |
| שהות ממוצעת | 40.3 חודשים | ⚠️ גבוה |
| Benchmark | 27 חודשים | — |

**User message 2:**
"ומה לגבי SDI?"

**Bot message 3:**
"מדד SDI (מגוון שירותים) ברמה 1:
• 44.6% מהזכאים שהידרדרו — SDI = 0 (אפס שירותים מעבר לטיפול אישי)
• SDI ממוצע רמה 1: 9.4 מתוך 100
• לשם השוואה: רמה 5 SDI ממוצע = 23.0

הנתון הזה הוא הלב של הרפורמה — כמעט מחצית מהזכאים ברמה 1 לא מקבלים שום מעטפת שירותים. הסל האישי נועד לשנות את זה.

⚠️ סייג חשוב: אין עדיין קבוצת ביקורת. לא ניתן לקבוע סיבתיות בין SDI נמוך להדרדרות."

**Input area (fixed bottom):**
- Text input: full width, rounded-lg, placeholder "שאל את בינה...", border-[#0368b0]/30
- 3 icon buttons on the left of the input (inside the input row):
  - Send: ArrowUp icon in bg-[#0368b0] circle (primary action)
  - Attachment: Paperclip icon (muted)
  - Voice: Mic icon (muted)

**Suggested chips (above input, horizontal scroll):**
4 pill buttons (bg-[#e8f3ff] text-[#0368b0] rounded-full px-4 py-2 text-sm):
- "סכם את נייר המדיניות"
- "מה הסטטוס של הפיילוט?"
- "הסבר את מדד SDI"
- "מה הצעדים הבאים?"

Clicking a chip fills the input with that text.

---

### PAGE 3: ניתוח מסמכים

**Initial state — Upload zone:**
- Centered dashed border box (border-2 border-dashed border-[#0368b0]/30 rounded-xl p-12)
- Upload icon (Upload, 48px, muted)
- Title: "גרור מסמך לכאן או לחץ להעלאה" (16px/600)
- Subtitle: "PDF, DOCX, XLSX, PPTX — עד 25MB" (12px, muted)
- "בחר קובץ" button (secondary style)
- Drag-and-drop highlight state: border-[#0368b0] bg-[#e8f3ff]

**After upload — Split view (show this as default mock state):**

**Left panel (40% width):**
- Document preview card:
  - File icon (FileText, 48px, colored by type — blue for DOCX)
  - Document name: "נייר מדיניות סל תפקוד אישי 1.2025" (16px/700)
  - File info: "DOCX • 18 עמודים • 2.4MB" (12px, muted)
  - Upload date: "הועלה: 8 במרץ 2026, 10:15" (12px, muted)
  - Progress bar: "ניתוח הושלם ✅" (green, 100%)
  - "הורד מקור" button (ghost style)
  - "נתח מחדש" button (ghost style)

**Right panel (60% width) — 5 tabs (shadcn/ui Tabs):**

**Tab 1: סיכום**
3 Hebrew paragraphs:

"נייר המדיניות מציג את רפורמת הסל האישי בסיעוד — מעבר ממודל אחיד של שעות טיפול אישי למודל מותאם אישית הכולל שירותים ב-6 ממדי חיים: תפקודי, חברתי, בריאותי, קוגניטיבי, טכנולוגי וסביבתי.

המסמך מבוסס על מחקר שטח מקיף של חברת EY שכלל ראיונות עם 120 בעלי עניין, סדנת עיצוב שירות עם 45 משתתפים, וניתוח נתוני הדרדרות חדשים באמצעות מדדי RDI (מדד שהייה יחסי) ו-SDI (מדד מגוון שירותים).

הרפורמה מתוכננת בשלושה שלבים: פיילוט בירושלים (תכנית 'עכשיו אני' — 20 תיקים), הרחבה ל-3-5 רשויות מקומיות, והטמעה ארצית. לוח הזמנים המוצע: 2026-2028."

**Tab 2: נקודות מפתח**
6 bullet points (each with colored dot icon):
- 🔵 44.6% מזכאי רמה 1 שהידרדרו קיבלו אפס שירותים נוספים (SDI=0)
- 🔵 נשים 85+ הן קבוצת הסיכון הגבוהה ביותר עם RDI=1.49
- 🔵 המודל החדש כולל 6 ממדי חיים במקום ממד תפקודי בלבד
- 🔵 מתאמת שירות אישית תלווה כל מטופל — תפקיד חדש במערכת
- 🔵 תקציב הפיילוט: 2.5 מיליון ₪ ל-20 תיקים בירושלים
- 🔵 יעד: הפחתת שיעור הדרדרות ב-15% תוך שנה

**Tab 3: נתונים**
Table (shadcn/ui Table, striped rows):

| מדד | ערך | מקור |
|-----|-----|------|
| SDI=0 ברמה 1 | 44.6% | ניתוח נתוני ביטוח לאומי 2026 |
| RDI נשים 85+ | 1.49 | מדדי הדרדרות v2 |
| שהות ממוצעת רמה 1 | 40.3 חודשים | ניתוח אורך |
| SDI ממוצע רמה 1 | 9.4/100 | מדדי הדרדרות v2 |
| תיקים בפיילוט | 20 | תכנית עכשיו אני |
| רשויות מתוכננות | 3-5 | קול קורא 2025 |

**Tab 4: המלצות**
4 numbered action items (each in a card with number badge):
1. להרחיב את תדירות ההערכות התפקודיות לנשים 85+ מפעם בשנה לפעם ברבעון
2. לשלב חיישנים טכנולוגיים (נפילות, דפוסי שינה) כחלק מסל ברירת המחדל ברמות 1-2
3. להקים צוות מתאמות שירות ייעודי (יחס 1:25) לפני ההרחבה הארצית
4. לבנות מערכת מדידה שוטפת עם דשבורד RDI/SDI בזמן אמת

**Tab 5: שאלות**
5 suggested follow-up questions (each as a clickable chip/button):
- "מה ההבדל בין המודל הנוכחי למודל המוצע?"
- "אילו שירותים נכללים בממד הטכנולוגי?"
- "מה לוח הזמנים להרחבה הארצית?"
- "כמה מתאמות שירות נדרשות לפיילוט?"
- "מה התקציב המוערך להטמעה מלאה?"

Clicking a question sends it to the עוזר AI page as a new chat message.

**Recent documents table (below the split view):**

Table with 5 rows:

| שם מסמך | סוג | תאריך ניתוח | סטטוס |
|---------|-----|-------------|-------|
| נייר מדיניות סל תפקוד אישי 1.2025 | DOCX | 8 במרץ 2026 | ✅ הושלם |
| מדדי הדרדרות RDI+SDI v2 | PDF | 5 במרץ 2026 | ✅ הושלם |
| קול קורא לרשויות מקומיות גרסה 2 | DOCX | 1 במרץ 2026 | ✅ הושלם |
| הצעת פיילוטים גרסה 6 | DOCX | 25 בפברואר 2026 | ✅ הושלם |
| תוצר EY סופי — מחקר שטח | PDF | 20 בפברואר 2026 | ✅ הושלם |

Each row clickable — loads that document's analysis in the split view above.

---

### PAGE 4: תובנות נתונים

**3 insight cards (top row, equal width, gap-4):**

**Card 1: "מגמת הדרדרות"**
- Badge: 🔴 "דורש תשומת לב" (bg-red-50 text-red-700 rounded-full)
- Line chart (Recharts LineChart): RDI average over 6 months
  - X axis: אוקטובר, נובמבר, דצמבר, ינואר, פברואר, מרץ
  - Y axis: 1.0 to 1.6
  - Data: [1.31, 1.33, 1.35, 1.38, 1.42, 1.49]
  - Line color: #c0392b, strokeWidth: 2, dot: true
  - Reference line at y=1.5 (dashed, label "סף חריג")
- Text below chart: "עלייה של 8% ב-RDI הממוצע בחצי השנה האחרונה" (14px, text-[#c0392b])
- Card: bg-white, rounded-xl, shadow-sm, p-5

**Card 2: "מגוון שירותים"**
- Badge: 🟡 "לבדיקה" (bg-yellow-50 text-yellow-700 rounded-full)
- Donut chart (Recharts PieChart with innerRadius):
  - SDI = 0: 44.6% — color #c0392b (red)
  - SDI = 1-17: 41.3% — color #e8a020 (gold)
  - SDI ≥ 33: 14.1% — color #1a7a4e (green)
  - Center text: "SDI" in bold
  - Legend below chart with colored dots
- Text below: "44.6% ללא שירותים מעבר לטיפול אישי" (14px, text-[#cc7a00])
- Card: bg-white, rounded-xl, shadow-sm, p-5

**Card 3: "פיילוט ירושלים"**
- Badge: 🟢 "בתהליך" (bg-green-50 text-green-700 rounded-full)
- Progress bar: 65% filled (bg-[#1a7a4e])
  - Label above: "12 מתוך 20 תיקים הושלמו"
  - Percentage on the right: "65%"
- Mini stats below progress:
  - תיקים פעילים: 12
  - ממתינים: 5
  - הושלמו: 3
- Text: "הפיילוט מתקדם לפי לוח הזמנים" (14px, text-[#1a7a4e])
- Card: bg-white, rounded-xl, shadow-sm, p-5

**Full-width area chart (below the 3 cards):**
- Title: "התפלגות רמות גמלה לאורך זמן" (h3)
- Recharts AreaChart, stacked:
  - X axis: 6 months (אוקטובר — מרץ)
  - 6 areas stacked (one per care level):
    - רמה 1: #0368b0
    - רמה 2: #266794
    - רמה 3: #e8a020
    - רמה 4: #1a7a4e
    - רמה 5: #8b5cf6
    - רמה 6: #c0392b
  - Mock data showing slight increase in levels 1-2 over time
  - Legend at bottom
  - Tooltip on hover showing exact values
- Card: bg-white, rounded-xl, shadow-sm, p-5, full width

**Bottom section: "תובנות AI אחרונות"**
- Title: "תובנות AI אחרונות" (h3)
- 5 insight cards in a list (vertical stack, gap-3):

| # | Title | Description | Source Badge | Date |
|---|-------|-------------|-------------|------|
| 1 | "עלייה חדה ב-RDI נשים 85+" | "זוהתה עלייה של 14% ב-RDI בקרב נשים 85+ ברמה 1 ברבעון האחרון" | 🔴 קריטי | 8 במרץ 2026 |
| 2 | "ירידה ב-SDI ברמה 2" | "SDI ממוצע ברמה 2 ירד מ-15.2 ל-12.8 — ייתכן שמשקף צמצום שירותים" | 🟡 לבדיקה | 6 במרץ 2026 |
| 3 | "פיילוט ירושלים — שיפור ראשוני" | "ב-3 תיקים שהושלמו נמדד שיפור ממוצע של 12% ב-SDI" | 🟢 חיובי | 4 במרץ 2026 |
| 4 | "פער מגדרי במדדי הדרדרות" | "RDI ממוצע לנשים: 1.38, לגברים: 1.21 — פער של 14%" | 🟡 לבדיקה | 1 במרץ 2026 |
| 5 | "ריכוז גיאוגרפי של הדרדרות" | "3 אזורים מרכזים 45% מכלל ההדרדרויות: ירושלים, חיפה, באר שבע" | 🔵 מידע | 27 בפברואר 2026 |

Each card: bg-white, rounded-xl, p-4, border-r-4 (color matches badge severity). Click opens detail view.

---

### PAGE 5: Toolbox

Page title: "ארגז כלים" (h1). Grid 3x4 gap-4. Each card: bg-white rounded-xl shadow-sm p-5. Icon 32px, name 16px/700, description 13px, "הפעל" button.

Row 1 Documents: ClipboardList "סיכום ישיבה", FileText "כתיבת מסמך", FileSpreadsheet "תבנית דוח"
Row 2 Analysis: BarChart3 "ניתוח נתונים", GitCompare "השוואת מסמכים", LineChart "יצירת גרפים"
Row 3 Communication: Languages "תרגום מסמך", Mail "כתיבת מכתב", AudioLines "תמלול ישיבה"
Row 4 Advanced: Brain "ניתוח תיק סיעוד", Ruler "אפיון מערכת", Target "תכנית עבודה"

Click "הפעל" opens Dialog modal with input (textarea or file upload) + "הפעל כלי" button + mock output.

---

### PAGE 6: Knowledge Base

Search + category tabs (הכל/מדיניות/מחקר/רגולציה/פיילוטים/טכנולוגיה). 10 document cards in 2-column grid. Each: icon, title, category badge, date, "פתח" button.

---

### PAGE 7: Settings

Profile (read/edit), AI preferences (style/length/language/context selects), notifications (3 toggles), version info.

---

## IMPLEMENTATION NOTES

Recharts for charts. Lucide icons. Sidebar RIGHT RTL. Hebrew dates. Responsive 1200/768/mobile. shadcn/ui Toast + Skeleton. React Router. useState + useContext.

## End of prompt
