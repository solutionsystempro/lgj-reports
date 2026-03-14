# Value Case Study Redesign Spec
**Date:** 2026-03-13
**File:** `Ian_Kirk_Value_Case_March2026.html`
**Deployed:** https://solutionsystempro.github.io/lgj-reports/Ian_Kirk_Value_Case_March2026.html

---

## Goal

Redesign the single-page HTML value case study to communicate the full value Ian Kirk brings to a company or team. Reframe from "sales closer portfolio" to "Growth Operator value case." This is a warm handoff document (Ian sends it after meeting someone) so it must reinforce the conversation, build trust, and drive one action: booking a call.

---

## Audience

People Ian has already met (at events, via DMs, referrals). Also linked from ianryankirk.com for warm traffic. Decision-makers at coaching orgs, speaker agencies, and high-ticket offer businesses looking for someone who can sell AND build systems.

---

## Core Reframe

Ian is not just a sales closer. He is a **Growth Operator**: someone who brings sales execution, AI-powered systems, team leverage, and 25+ years of pattern recognition to double revenue for influencers, coaches, and consultants.

---

## Copy Rules

- No em dashes anywhere on the page. Use periods, commas, colons, or hyphens instead.
- Keep numbers consistent: $550K total, 218 clients, 30%+ close rate, 300 calls, 14 years in the mountains, $81.4K peak month.

---

## Page Title and Meta

```html
<title>Ian Kirk -- Growth Operator | Value Case | 2026</title>
<meta name="description" content="Ian Kirk: $550K closed in 12 months, 218 clients, 30%+ close rate. Sales execution, AI systems, and 25+ years of pattern recognition. Book a call." />
```

---

## Design Approach: Two-Track Hero

Hero section presents identity and proof on the left, photo and story on the right. Remainder of the page tells the full story with proof woven throughout. Single CTA throughout: book a call at `https://leadgenjay.com/book-ian`.

---

## Images

Copy both files from the IRK Website into the Value Case Study IRK repo root (same directory as the HTML file):

| Source | Destination | HTML src attribute |
|--------|-------------|-------------------|
| `/c/Users/ensan/Dev/IRK Website/public/ian-kirk.jpg` | `/c/Users/ensan/Dev/Value Case Study IRK/ian-kirk.jpg` | `src="ian-kirk.jpg"` |
| `/c/Users/ensan/Dev/IRK Website/public/ian-adventure.jpg` | `/c/Users/ensan/Dev/Value Case Study IRK/ian-adventure.jpg` | `src="ian-adventure.jpg"` |

---

## Page Structure

### Section 1: Hero (Two-Track)

**Left column:**
- Badge: "Growth Operator" with animated green live dot
- H1: "I Build Revenue. Then Build the Systems Around It."
- Subtext: "25+ years of building, losing, and coming back stronger. Now applying every lesson."
- 4 animated KPI counter cards:
  - $550K -- Closed in 12 Months
  - 218 -- Clients Transformed
  - 30%+ -- Close Rate (300 calls, Feb 2025 to Feb 2026)
  - $81.4K -- Peak Month (Feb 2026)
- "Book a Call" CTA button linking to `https://leadgenjay.com/book-ian`

**Right column:**
- `ian-kirk.jpg` styled with rounded corners, subtle indigo border glow
- Story card beneath (no em dashes):

  > "Built a business from cold calls and VHS tapes. Watched $10M vanish overnight. Built a 2,500-rep empire and lost it the same way. Spent 14 years in the mountains. Now back, applying every lesson."

**Mobile behavior (single column, stacked):**
- Photo stacks ABOVE the H1 on mobile (face first, then identity, then KPIs, then CTA)
- Photo: full width, max-height 320px, object-fit cover on mobile
- KPI cards: 2x2 grid on mobile

---

### Section 2: The Journey (3 Acts)

Three act cards animate in on scroll using the existing `.section` + `.visible` scroll-observer pattern.

**Act 1 -- The Builder (1999-2012)**
Content:
- Cold calls, wakeboarding school, real estate top producer
- MLM empire: 2,500 reps, $500K+ MRR
- Closing line: "Then a single executive dispute made it disappear. Twice."

Transition between Act 1 and Act 2:
- A full-width divider element with the text: "Then it was gone overnight."
- Style: centered text, muted color, smaller font, with a thin horizontal rule on each side
- On scroll into view: the divider fades in at opacity 0 to 1 over 0.8s (CSS transition triggered by the existing IntersectionObserver adding `.visible`)
- No JavaScript beyond what already exists

**Act 2 -- The Mountains (2012-2024)**
- `ian-adventure.jpg` displayed inline (full width of card, rounded, max-height 260px, object-fit cover)
- Content:
  - Professional tandem pilot (flew paying passengers)
  - Snowboard instructor
  - Airbnb arbitrage (covered all living expenses)
  - Lyft and Uber when weather grounded flights
  - Key line: "When the conditions didn't let me fly people for money, I drove people for money. I always found a way to cash flow."
  - Closing insight: "The entrepreneurs who outlast everyone understand who they are before they sell anything."

**Act 3 -- Growth Operator (2024-Now)**
Content:
- All of those lessons applied to a single year
- $550K closed. 218 clients. AI tools built from scratch.
- Closing line: "Not just closing. Building the whole machine."

---

### Section 3: What I Bring to a Team (3 Pillars)

**Pillar 1: Sales Execution**

Preserve the existing animated bar chart from the current HTML (section `#s1`). Data points to keep exactly as-is:

| Bar | Label | Value | % height |
|-----|-------|-------|----------|
| 1 | Feb '25 | $10K | 12.3% |
| 2 | Scaling | $24K | 29.5% |
| 3 | Scaling | $36K | 44.2% |
| 4 | Oct '25 | $42K | 51.6% |
| 5 | Jan '26 | $62.3K | 76.6% |
| 6 | Feb '26 (PEAK) | $81.4K | 100% |

Below the chart, 3 inline stats: Close Rate 30%+ / 300 Calls / 218 Clients

**Pillar 2: Systems Building**

4 AI tool cards in a 2x2 grid (dark card style, each with a title, one-line description, and link):

| Tool | Description | Link |
|------|-------------|------|
| Business Clarity Coach | AI strategic diagnostic. Validates offers and maps the simplest path forward. | https://chatgpt.com/g/g-683752da6f10819187d894848e822a2c-ultimate-business-clarity-coach |
| Call Reflekt Agent | Paste a sales call transcript. Get back the exact moment you lost the frame. | https://chatgpt.com/g/g-68bce0888438819185f398e815027b33-call-reflekt-5-0 |
| SLAP Method | The framework that turns ignored DMs into booked calls. | https://slap-method-production.up.railway.app/ |
| Objection Card App | 56 real-world objection reframes. Drillable, pocketable, built for the field. | https://objection-cards-app-production.up.railway.app/ |

Each card: title, description, "Try it free" link (opens in new tab). No pricing shown.

**Pillar 3: Team Leverage**

Use the existing content from sections `#s1b` (The Sales Machine Ian Helped Build) verbatim. Key data to preserve:

- Ian generated $550K personally in 12 months
- His growth created demand that required 4 additional hires: Tyler (original closer), Mason (Sales Director), Daniel (setter), Jonathan (Closer #3)
- 5-step org growth timeline (keep the existing grid): Tyler > Ian joins > Ian becomes closer > Mason + Daniel > Jonathan
- Callout: "Ian didn't just produce revenue. He generated the demand that made four additional hires necessary."

---

### Section 4: What People Say

**Scrolling ticker** (infinite loop, same implementation pattern as existing bar animations):

Use ALL entries from TICKER_WINS in `/c/Users/ensan/Dev/IRK Website/constants.tsx`. Duplicate the array 3x for seamless looping. Style: small caps, muted text, diamond separator between items.

**3 Testimonial cards** (3-column grid on desktop, single column on mobile):

1. **Kim Berthilsson** (initials: KB) -- Community Member
   Result badge: "Best clarity call of all time"
   Quote: "I just had the best clarity call of all time with Ian Kirk! If you're looking to navigate the ins and outs of building your business effectively, you won't want to miss the chance to speak with him. Ian is not just knowledgeable -- he genuinely cares about helping people succeed."

2. **Jesse Murdock** (initials: JM) -- Offer Builder
   Result badge: "Offer confidence unlocked"
   Quote: "I just wanted to write this to thank Ian Kirk for getting me started with my offer. I feel more confident in approaching my ideal client with my database reactivation offer."

3. **Cole TheConnector** (initials: CC) -- Cold Email Specialist
   Result badge: "The call was FIRE"
   Quote: "Last night's Coffee and Clarity call with Ian Kirk was FIRE. Ian's copywriting and cold email insights were absolute gold. Biggest takeaway: email brevity and psychology."

Note: replace any em dashes in quote text with a comma or period.

---

### Section 5: Book a Call (Closing CTA)

Full-width section, dark background with subtle indigo radial glow.
- Headline: "Ready to Add a Growth Operator to Your Team?"
- Subtext: "Sales execution, AI systems, and 25+ years of hard-won pattern recognition. One call to see if there is a fit."
- Large "Book a Call" button linking to `https://leadgenjay.com/book-ian`

---

## Persistent Elements

**Sticky floating CTA button:**
- Bottom-right corner, `position: fixed`, z-index high enough to clear all content
- Text: "Book a Call"
- Links to `https://leadgenjay.com/book-ian`
- iOS Safari note: use `-webkit-transform: translateZ(0)` on the fixed element to avoid iOS scroll jank
- Appears after user scrolls past the hero (JS: add `.show` class once `window.scrollY > heroHeight`)
- On mobile: full-width bar pinned to bottom instead of corner button

**Scroll-reveal animations:** preserve existing IntersectionObserver + `.section` + `.visible` pattern.

**Animated KPI counters:** count up on first scroll into view using the existing `animateNum` function. The "$550K" and "218 clients" cards animate numerically. The "30%+" close rate and "$81.4K" peak month cards display as static text (not animated) since they are strings/formatted values, not plain integers.

---

## Visual Style

- Preserve existing dark theme (`#07090f` background, indigo/blue/green palette)
- Preserve Inter + JetBrains Mono fonts
- Preserve existing CSS variable system
- No new external dependencies (no npm, no CDN additions beyond existing Google Fonts)
- Mobile-first layout throughout

**Sections to remove from current HTML:**
- Standalone "Loyalty Record" section (`#s6`) -- fold any key data into Pillar 3
- Standalone "The Simple Math" section (`#s7`) -- fold into the closing CTA or Pillar 1
- "The Ask" section (`#s8`) -- replaced by Section 5 (Book a Call)
- Top nav (`#snav`) -- replaced by the sticky CTA button

---

## CTA

Single CTA throughout: **Book a Call** at `https://leadgenjay.com/book-ian`

No email list opt-in. No secondary action. One clear next step.

---

## Out of Scope

- No new frameworks or build tools -- stays as a single HTML file
- No backend, no form submissions
- No audio or video embeds
- No changes to ianryankirk.com in this task
- No changes to the IRK Website repo in this task
