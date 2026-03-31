# Brand

## Strategy and Messaging

### Vision

The foundation for competitive gaming intelligence.

### Tagline

From gameplay to ground truth.

#### Alternative Taglines (Product / Campaign Exclusive)

##### Research-Facing

- Built for researchers. Respected by players.
- Don’t interpret the game. Measure it.

##### Competitive-Facing

- Master the game behind the game.
- Study the Rift. Then break it.
- Data to dominate the Rift.
- No more coinflips.
- For those who'd rather know than hope.
- Clairvoyance is back.

### One-Liner

Not a tool for playing. A system for understanding.

### Long Version

The open data and intelligence stack for those who’d rather know than hope.

### Mission

Build the open data and intelligence stack for understanding competitive games.

### Marketing Guidance

- If it sounds like marketing → cut it;
- If it sounds like Reddit → refine it;
- If it sounds like a high-elo analyst → keep it.

### Core Personality Traits

#### Unyielding Precision

Every number matters. Every conclusion holds up.

GPTilt operates at the level where small differences change outcomes. No rounding away uncertainty. No hiding behind averages. No “close enough.”

If it’s shown, it’s defensible. If it’s uncertain, it’s explicit.

**Standard:**

- Quantified, reproducible, exact;
- Clear about confidence and limits;
- Never trades accuracy for simplicity.

#### Open Intelligence

Knowledge compounds when it’s shared.

GPTilt is built as an open system—data, tools, and models that others can inspect, extend, and build on.
No black boxes. No gatekeeping.

The goal isn’t to outperform alone. It’s to raise the level of understanding for everyone serious about the game.

**Standard:**

- Transparent by default;
- Designed for reuse and extension;
- Treats users as collaborators, not consumers.

#### Composed Authority

Calm, precise, and already proven.

GPTilt speaks like someone who has already run the numbers.
No hype. No forced personality. No over-explaining.

Just clear conclusions, delivered with quiet confidence.

**Standard:**

- Short, direct, and grounded in evidence;
- Never exaggerated or speculative;
- Sounds like analysis, not marketing.

## Visual Identity

### Logo

???

### Colour Palette

**Core Brand Palette = Hexcore Glow**  

- #050A1F Void BG;
- #00E5FF Primary Glow
- #FFCC00 Gold Accent;
- #0F2549 Deep Rift Blue;
- #E2E8F0 Text.

This is the official signature everywhere — GitHub repo, landing page, socials, README headers, Notion/docs sidebar, etc. It’s the “GPTilt blue” people will remember.

Then apply the other two as **light-touch Accent Modes** (only swap 1–2 colors max):

#### **Marketing / Hero Mode**

Use full Core Palette (already perfect for hype — glowing edges and gold frames pop exactly like the logo).

#### **Docs Mode**

- Keep exact same Void BG (#050A1F)  
- Primary stays #00E5FF  
- Swap Gold → #E8B923 (warmer, less flashy for long reads)  
- Swap Deep Rift Blue → #0B1E3A (deeper tactical shade for code blocks, tables & sidebars)

#### **Playground / Dashboard Mode**

- Keep exact same Void BG (#050A1F)  
- Primary stays #00E5FF  
- Swap Gold → #FFEA80 (brighter for live win-probability lines)  
- Swap Deep Rift Blue → #132E5E (futuristic latent-space depth for neural activations & heatmaps)

#### Why this hybrid system wins

- 80 % color consistency = instant brand recognition.
- Still gives each section its own personality (energetic vs mature vs futuristic).
- Looks premium and intentional — exactly like how Riot does Hextech variations across different champions/tools without confusing players.

### Typography

Our typography balances the calculated aggression of competitive gaming with the absolute clarity required for data science.

#### Headings: Rajdhani

Condensed geometric sans with sharp angles and high tension—aggressive yet controlled, like a perfectly executed outplay.

- **Weights:** Bold (700) / ExtraBold (800)
- **Usage:** Hero titles, section headers, model names (e.g., Tilt Predictor v1.2), and marketing graphics.
- **Why it works:** It feels modern-tech and esports-ready without overdoing it. It brings the brand's energy to the forefront.

#### Body & UI: Inter

The gold standard for data and interfaces: tall x-height, open counters, and subtle warmth.

- **Weights:** Regular (400) / Medium (500) / SemiBold (600)
- **Usage:** Dense tables (KDA ratios, win probabilities), documentation paragraphs, UI elements, and dashboard labels.
- **Why it works:** Keeps everything exceptionally readable during long, deep-dive research sessions. High contrast on dark backgrounds and screams premium ML/SaaS.

#### Code & Raw Data: JetBrains Mono (or Fira Code)

Purpose-built for developers, featuring high legibility and beautiful coding ligatures.

- **Weights:** Regular (400) / Medium (500)
- **Usage:** Code blocks, API endpoints, raw JSON outputs, and CLI documentation.
- **Why it works:** Signals "research-grade tooling" immediately to developers. (Note: Ensure coding ligatures like ->, =>, and != are enabled in docs).

#### Typographic Scale & Hierarchy

- **Display (Hero):** Rajdhani ExtraBold • 64px–96px • Tight tracking (-0.02em)
- **H1 / H2 (Section):** Rajdhani Bold • 32px–48px • Normal tracking
- **Body Text:** Inter Regular • 16px • 1.6 Line Height
Caption / Meta: Inter Medium • 13px • 1.4 Line Height • Text color muted (e.g., #94A3B8)
- **Code Blocks:** JetBrains Mono Regular • 14px • 1.5 Line Height

#### Number Styling

This is where the Unyielding Precision trait lives. In GPTilt, every digit must be defensible and clear.

##### Tabular Lining Numerals

- **Usage:** Tables, dashboards, model outputs, comparisons.
- **Rule:** Enable tnum (tabular numerals) in CSS. Every digit has equal width so columns align perfectly. Prevents visual "jumping" when live values update. Feels precise, engineered, and trustworthy.

##### Slashed Zeros

- **Usage:** Code, model parameters, IDs, database keys.
- **Rule:** Enable zero (slashed zero) in CSS/Figma for monospace fonts to avoid any ambiguity between the number 0 and the letter O.

##### Formatting Standards

These rules apply across all documentation, UI, and marketing:

- **Leading Zeros:** Always show them for decimals. (Correct: 0.07. Incorrect: .07).
- **Consistent Precision:** Never mix decimal lengths in the same context. Pick 2 or 3 places and stick to it (e.g., 52.30%, not 52.3% if another row is 49.15%).
- **Thousands Separators:** Use commas for numbers over 9,999 (e.g., 12,450).
- **Percentages:** Keep the symbol attached to the number (Correct: 52.3%. Incorrect: 52.3 %).
- **Latency & Time:** Attached lowercase unit (Correct: 0.01s or 12ms).
