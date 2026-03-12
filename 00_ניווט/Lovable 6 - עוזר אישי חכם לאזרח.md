# Lovable פרומפט 6 — עוזר אישי חכם לאזרח הוותיק

> אפליקציית עוזר אישי חכם (AI) לאזרחים ותיקים ומשפחותיהם.
> מתחיל בסיעוד/הזדקנות, מורחב בהמשך לשיקום, אבטלה ועוד.
> העתק הכל מתחת לקו ל-Lovable.

---

## 🔽 התחל להעתיק מכאן 🔽

---

Build a complete Hebrew RTL web application: **"שלי — העוזר האישי החכם של ביטוח לאומי"**

A smart personal assistant for elderly citizens and their families in Israel. The assistant helps navigate the complex world of nursing care benefits, understand their rights, find services, manage their care basket, communicate with their care coordinator, and get answers to any question about their situation — all in simple, warm, accessible Hebrew.

**The vision:** Today, an 82-year-old woman in Jerusalem doesn't know what services she's entitled to, can't navigate the bureaucracy, and has no one to ask. "שלי" (literally "mine" in Hebrew) is her personal AI companion — always available, always patient, always in her language. It explains her rights, helps her choose services, reminds her of appointments, and connects her to her care coordinator. In the future, "שלי" will expand to serve people in rehabilitation, unemployment, and other National Insurance domains.

**Design philosophy:** This is NOT a tech product for young people. It's designed for elderly users (70-95 years old) and their adult children (40-65). Everything must be:
- Extra large text (minimum 16px body, 20px for key info)
- High contrast (WCAG AAA where possible)
- Simple navigation (max 2 levels deep)
- Warm, personal tone (not bureaucratic)
- Voice-input friendly (large mic button)
- Touch-friendly (large tap targets, 48px minimum)

---

## DESIGN SYSTEM — BTL (ביטוח לאומי) — Accessible Edition

### Identity
- App name: "שלי" (with heart icon ❤️)
- Tagline: "העוזר האישי שלך מביטוח לאומי"
- Organization: ביטוח לאומי — המוסד לביטוח לאומי
- Credit: "אביעד יצחקי, מינהל גמלאות"

### Colors
- Primary: #0c3058 (headings, headers)
- Secondary: #0368b0 (buttons, links)
- Tertiary: #266794 (secondary text)
- Accent: #e8a020 (gold — highlights, important info, CTAs)
- Background: #ffffff (pure white — easier for elderly eyes)
- Surface: #f8fafc (very light gray for cards)
- Text: #1a1a2e (near-black for maximum readability)
- Muted: #4a5568 (darker muted for accessibility)
- Success: #1a7a4e
- Warning: #cc7a00
- Error: #c0392b
- Warm: #fef3e2 (warm cream for assistant messages)
- Border: rgba(0, 0, 0, 0.12)

### Typography
- Font: 'Heebo', sans-serif (Google Fonts: weights 300,400,500,600,700,800)
- Direction: RTL. Language: Hebrew (all UI text)
- h1: 32px/800 (larger than standard for elderly)
- h2: 24px/700
- h3: 20px/700
- Body: 16px/400 (minimum — larger than standard 14px)
- Large body: 18px/400 (for key information)
- Small: 14px/400 (only for metadata)
- Line height: 1.6 (extra spacing for readability)

### Layout
- Max content width: 900px centered (narrower for focus)
- Card radius: 16px (softer, friendlier)
- Button radius: 12px (pill: 9999px)
- Spacing: generous — 8, 16, 20, 24, 32, 40, 48, 64
- Shadow: 0 4px 12px rgba(0,0,0,0.08)

### Components
- Buttons: bg-[#0368b0] text-white rounded-xl px-6 py-3.5 text-lg font-bold hover:bg-[#025a8f] focus-visible:ring-4 focus-visible:ring-[#0068f5] focus-visible:ring-offset-2 min-h-[48px]
- Large CTA buttons: bg-[#e8a020] text-[#0c3058] rounded-xl px-8 py-4 text-xl font-bold min-h-[56px]
- Cards: bg-[#f8fafc] border border-black/10 rounded-2xl shadow-sm p-6
- Inputs: border-2 border-[#0368b0]/40 rounded-xl px-4 py-3.5 text-lg text-[#1a1a2e] focus:border-[#0068f5] focus:ring-4 focus:ring-[#0068f5]/20 min-h-[48px]
- Header: bg-[#0c3058] text-white
- Footer: bg-[#0c3058] text-white/80 text-base py-6

### Accessibility (CRITICAL — elderly users)
- lang="he" dir="rtl" on html
- Skip navigation link as first focusable element
- All form inputs: visible Hebrew label (16px, bold) + aria-label
- Color contrast: min 7:1 for body text (WCAG AAA), 4.5:1 for large text
- Focus indicators: visible 4px outline on ALL interactive elements (thicker than standard)
- Keyboard navigation: Tab/Enter/Space/Arrows
- Semantic HTML: heading hierarchy, landmarks, aria-live for dynamic content
- Touch targets: min 48x48px (larger than standard 44px)
- No content conveyed by color alone — always text + icon
- Reduced motion: respect prefers-reduced-motion
- Text resizable up to 200% without breaking layout
- aria-live="polite" on chat messages for screen readers

### Tech Stack
- React 18+ TypeScript, Vite, Tailwind CSS, shadcn/ui, Heebo font, Recharts, Lucide React icons
- All state in React hooks, mock data inline, no API calls
- React Router for navigation

### Footer
"שלי — העוזר האישי שלך | ביטוח לאומי | אביעד יצחקי, מינהל גמלאות | v1.0 | מרץ 2026"

### RULES
- ALL UI text Hebrew. Zero English in interface.
- ALL layout RTL. No exceptions.
- Warm, personal, simple tone. NOT bureaucratic. Like talking to a kind friend.
- Every interactive element: thick focus-visible styles (4px).
- Labels above inputs, large and bold.
- Never light text on light backgrounds.
- Never use jargon without explanation.
- Always offer "הסבר לי" (explain to me) option next to complex terms.

---

## APPLICATION — 6 PAGES

### Navigation (Bottom tab bar — mobile-first, like a phone app)

Bottom navigation bar (fixed, bg-white, border-t, shadow-up):
5 large tabs with icon + label (14px bold):

| Icon (Lucide) | Label | Page |
|---------------|-------|------|
| Home | בית | דף הבית |
| MessageCircle | שלי | שיחה עם שלי |
| ShoppingBag | הסל שלי | הסל האישי |
| Bell | התראות | התראות ותזכורות |
| User | אני | הפרופיל שלי |

Active tab: text-[#0368b0], icon filled. Inactive: text-[#6b7a8d].
Each tab icon: 28px. Label: 14px/600. Total tab height: 64px.
On desktop (>768px): tabs move to top horizontal navbar.

---

" section:**
- Simple visual: 6 colored circles with icons and counts
- Total: "11 services in 6 domains"

**History section:**
- 7.3.26 — added weekly companion
- 1.3.26 — emergency button installed
- 15.2.26 — home visit by coordinator
- 1.2.26 — updated assessment
- 15.1.26 — added nutrition counseling

**Bottom:** "Talk to Sheli" CTA

---

### PAGE 6: Accessibility Settings

**Section 1 — Text Size:**
3 large buttons: regular | large | extra-large. Live preview. Default: large.

**Section 2 — Contrast:**
Toggle: high contrast (default OFF). When ON: AAA level.

**Section 3 — Notifications:**
Toggles: appointment reminders (ON), basket updates (ON), daily tips (OFF).
Select: reminder timing — 1 hour / 2 hours / 1 day before.

**Section 4 — Voice:**
Toggle: read bot messages aloud (OFF).
Select: speech speed — slow / normal / fast.

**Section 5 — Info:**
Version 1.0. Contact support button.

---

## FUTURE EXPANSION — MULTI-DOMAIN

Domain switcher (in settings): Nursing/Aging (active), Rehabilitation (coming soon), Unemployment (coming soon), Children (coming soon), Disability (coming soon).

Each domain has own: service catalog, FAQ, chat context, notifications.
Shared: user profile, design system, chat interface, notification system.
The assistant adapts personality and knowledge per domain.

Build the domain switcher UI now with "coming soon" badges on inactive domains.

---

## MOCK USER PROFILE
- Name: Rachel Cohen, Age: 82, Female, Care level 3
- Address: Herzl 15, Jerusalem. Widow, 1 son (David) in city.
- Coordinator: Sarah Israeli. Services: 11. SDI: 72. RDI: 1.12.

---

## IMPLEMENTATION NOTES
1. Mobile-first (375px). Bottom tabs mobile, top navbar desktop.
2. Min font 16px, min touch 48px, generous padding.
3. Prominent mic button every page (56px floating, gold).
4. Warm cream (#fef3e2) for bot messages, not cold blue.
5. Simple language for 80-year-olds. No English, no jargon.
6. Recharts only for simple donut. Lucide icons 24-32px.
7. shadcn/ui with larger sizes. Toast 5 seconds display.
8. No skeleton loaders (confusing). Simple loading text instead.
9. aria-live on chat. prefers-reduced-motion support.
10. React Router for pages. useState + useContext for state.

## End of Prompt
