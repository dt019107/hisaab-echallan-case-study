# Hisaab (ChallanOS) — Design Specification & Architectural System

Authoritative, human-designed specification for the **Hisaab Fleet Compliance OS** enterprise portal. Built for commercial vehicle fleet operators and vehicle leasing enterprises (*Apex Fleet Pvt Ltd* & *Zoom Leasing Co.*).

---

## 1. Core Visual Principles (Zero AI-Slop Enforcement)

This portal adheres strictly to human enterprise software design standards, explicitly eliminating the five telltale formulas of generated templates:

| AI Slop Formula | Replaced With Authentic Human Alternative |
| :--- | :--- |
| **1. The Italic Serif Accent Word** | **Single Typographic Voice (`Archivo`):** Headings use a single, confident, heavy grotesque typeface (`font-black tracking-tight`). Zero intrusion of decorative italic serif words. |
| **2. The Ubiquitous Eyebrow Pill** | **Clean Editorial Headings:** Sections stand on their own with numbered, authoritative titles (`01. Problem, Scope & Approach`) and a descriptive subtitle. Zero tiny pill badges perched above headings. |
| **3. The Bento Grid for Everything** | **Structured Tables & Divided Strips:** Replaced forced rounded bento boxes with high-density specification strips, two-column comparison tables, and formal token tables. |
| **4. Glassmorphism Overuse** | **Solid Surfaces & 1px Borders:** All content cards, modals, and preview containers use solid opaque surfaces (`#FFFFFF` and `#0B132B`) with crisp 1px borders (`#CDD7E5`). Only the sticky header uses backdrop blur. |
| **5. Fake Window Chrome** | **Direct Product Framing:** Dropped toy browser URL address bars, fake navigation arrows, and macOS traffic-light dots. Real screenshots and interactive production interfaces speak directly. |

---

## 2. Color System & Token Architecture

All neutrals are tinted with 4% of the brand cobalt hue to ensure cohesive brand harmony and eliminate stock gray palettes.

### 2.1 Core Palette

| Role | Token | Hex Code | Purpose & Accessibility |
| :--- | :--- | :--- | :--- |
| **Brand Primary** | `--brand-600` | `#1E51D4` | Primary brand accent, primary CTA buttons, active tabs |
| **Brand Hover** | `--brand-700` | `#1740AD` | Interactive hover state for brand actions |
| **Brand Light** | `--brand-50` | `#F0F4FE` | Subtle brand chips and active filter pills |
| **Canvas** | `--surface-canvas` | `#EEF2F7` | Cool-tinted page background (non-stock slate) |
| **Card Surface** | `--surface-card` | `#FFFFFF` | Primary container cards, modal bodies, table rows |
| **Subtle Surface** | `--surface-subtle` | `#F7F9FC` | Table headers, secondary toolbars, read-only areas |
| **Primary Border** | `--border-primary` | `#CDD7E5` | Structural 1px boundary lines and card outlines |
| **Ink Text (Headings)** | `--text-ink` | `#0B132B` | 15:1 WCAG AAA high-contrast primary text |
| **Ink Text (Body)** | `--text-body` | `#33415C` | 7.5:1 WCAG AAA secondary text and descriptions |
| **Muted Text** | `--text-muted` | `#5C6B84` | Captions, timestamps, and table column headers |

### 2.2 Calibrated Status Lifecycle Tokens

Pills and badges are strictly reserved for state machine statuses and never used for decorative filler.

| Status | Text Hex | Background Hex | Border Hex | Meaning in State Machine |
| :--- | :--- | :--- | :--- | :--- |
| **Unassigned** | `#B42318` | `#FEF3F2` | `#FECDCA` | Violation detected without driver or lease attribution |
| **Assigned** | `#1E51D4` | `#EFF4FE` | `#C7D9FB` | Liability attributed via contract clause or shift roster |
| **Pending** | `#B45309` | `#FFFBEB` | `#FDE68A` | Payment initiated or pending gateway acknowledgement |
| **Paid** | `#15803D` | `#F0FDF4` | `#BBF7D0` | Settled on MoRTH portal with verified official receipt |
| **Disputed** | `#6D28D9` | `#FAF5FF` | `#E9D5FF` | Contested with traffic authority with GPS & dashcam proof |
| **Virtual Court** | `#0369A1` | `#F0F9FF` | `#BAE6FD` | Judicial summons issued; online settlement or contestation |
| **Failed** | `#B42318` | `#FEF3F2` | `#FECDCA` | Banking decline or transaction timeout; retry queue |

---

## 3. Typography Architecture

Dual-type system pairing a robust industrial grotesque with a highly legible interface workhorse.

```
Headings & Display:  Archivo (Weights: 700 Bold, 800 ExtraBold, 900 Black)
Body & Interface:    Inter (Weights: 400 Regular, 500 Medium, 600 SemiBold)
Data & Telemetry:    JetBrains Mono (Weights: 400 Regular, 600 SemiBold, 700 Bold)
```

- **Headings (`Archivo`):** Clean, architectural, and authoritative. Designed for commercial transport and logistics utility. Letter-spacing: `-0.025em`.
- **Body (`Inter`):** High legibility at small sizes (12px–14px), generous line-height (`1.6`), zero stylistic gimmicks.
- **Tabular Numerals (`JetBrains Mono`):** All financial figures (`₹12,45,71,375`), Indian HSRP registration numbers (`MH 12 QR 2284`), VINs, and challan hash codes use tabular figures (`font-variant-numeric: tabular-nums`).

---

## 4. Geometric Scale & Radius Rules

Visual clutter is eliminated through strict radius discipline:

- `--radius-panel: 20px` — Workspace containers, major specification cards, and modal dialogs.
- `--radius-card: 14px` — Standard content containers, preview boxes, and child blocks.
- `--radius-control: 8px` — Buttons, form inputs, search fields, and dropdown triggers.
- `--radius-chip: 6px` — Small data tags, role indicators, and code snippets.
- `--radius-pill: 9999px` — **Strictly reserved for lifecycle status badges.**
