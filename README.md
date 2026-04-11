# Reloading Tracker — User Guide

Reloading Tracker is an application that helps you log your reloading sessions, compare the true cost of reloading your own ammunition against buying factory-loaded rounds, and track your progress toward break-even. It accounts for component prices, taxes, fixed fees, one-time equipment purchases, and your actual reloading history to give you a clear picture of your real savings over time.

[Try it out](https://fmalpartida.github.io/reloading-cost-calculator)

---

## Table of Contents

1. [Overview](#1-overview)
   - [Recommended Workflow](#recommended-workflow)
   - [Tabs at a Glance](#tabs-at-a-glance)
2. [My Ammo](#2-my-ammo)
   - [Adding a Reload Entry](#21-adding-a-reload-entry)
   - [Adding a Factory Ammo Entry](#22-adding-a-factory-ammo-entry)
   - [Managing Entries](#23-managing-entries)
   - [Default Taxes & Fees](#24-default-taxes--fees)
3. [My Components](#3-my-components)
   - [Adding a Component](#31-adding-a-component)
   - [Managing Components](#32-managing-components)
   - [Linking Inventory to Loads](#33-linking-inventory-to-loads)
4. [Reloading Journal](#4-reloading-journal)
   - [Logging a Session](#41-logging-a-session)
   - [Managing Journal Entries](#42-managing-journal-entries)
   - [Printing a Lot Label](#43-printing-a-lot-label)
   - [Journal Statistics](#44-journal-statistics)
5. [Cost Comparison](#5-cost-comparison)
6. [Cost Analysis (Break-Even)](#6-cost-analysis-break-even)
   - [Load Selection](#61-load-selection)
   - [Equipment Costs](#62-equipment-costs)
   - [Reading the Chart & Stats](#63-reading-the-chart--stats)
7. [Guided Tour](#7-guided-tour)
8. [Settings & About](#8-settings--about)
9. [Import & Export](#9-import--export)
10. [Tips & Notes](#10-tips--notes)

---

## 1. Overview

### Recommended Workflow

Reloading Tracker is built around a natural progression that mirrors the way reloading actually works. Following this workflow will give you the most accurate results and make the analysis meaningful from the start.

![Reloading Tracker — main application and navigation tabs](./images/header-tabs.png)

**Step 1 — Define your ammo**

Before you can log sessions or compare costs, the application needs to know what you are reloading and what it costs. You have two ways to do this:

- **Direct entry in My Ammo.** Open the Editor tab and enter your component prices manually for each load. This is the fastest way to get started. The cost per round is calculated in real time as you type.
- **Build a component library first (recommended).** Go to **My Components** and add your powders, primers, bullets, and brass with their current prices. Then, when you create a load in My Ammo, select each component from the inventory instead of typing values by hand. Any future price change — a new jug of powder, a bulk primer buy — only needs to be updated in one place, and every load that uses that component recalculates automatically.

> **Accuracy starts here.** The cost analysis, the break-even chart, and the savings figures are only as good as the prices you enter. Use the actual prices you paid, including shipping if it meaningfully affects the per-unit cost. Update component prices when you buy a new batch. The closer your entries are to real-world costs, the more the numbers you see will reflect your true reloading economics — not a rough estimate.

Do the same for **factory ammo**: add at least one factory entry (with its box price, taxes, and any fixed fees) so the comparison and break-even analysis have a meaningful baseline to work against.

**Step 2 — Log your sessions in the Journal**

Every time you sit down at the press, open the **Journal** tab and add an entry: select the load, enter the date and the number of rounds you produced. The application assigns a unique, incrementing lot number automatically.

This is where the application starts working for you over time. Each session builds your production history, and the cumulative round counts feed directly into the Cost Analysis so you can see your real progress toward break-even — not a theoretical projection, but based on what you have actually made.

**Step 3 — Print lot labels**

After logging a session, click the **Print** button on the journal entry. The label dialog opens with the lot number and quantity already filled in from the session. Review the label — load name, caliber, components, COAL — and print. Attach it to the ammo box before it goes on the shelf. Every box in your storage is now traceable back to a specific lot in the journal.

**Step 4 — Review your costs and track break-even**

With sessions accumulating in the journal, open **Cost Analysis** and switch to **Rounds** mode. Your journal rounds are automatically added to your reload entries. Watch the break-even chart as your position on the reload line advances toward the intersection with factory costs. The stats panel shows you exactly how many rounds remain until your equipment pays for itself, and how much you have already saved.

Use **Cost Comparison** at any time to see side-by-side which of your loads is the most economical, or to check whether a specific factory ammo purchase would have been cheaper than your reload for that caliber.

---

The more consistently you follow this workflow, the more the application rewards you. A single session logged is interesting. A year of sessions is a genuine financial picture of what reloading costs — and saves — you.

---

### Tabs at a Glance

The application has five main tabs accessible from the navigation bar at the top:

| Tab | Purpose |
|-----|---------|
| **My Ammo** | Library of all your ammo entries — reloads and factory |
| **My Components** | Global catalog of reloading components — powders, primers, bullets, and brass |
| **Journal** | Log reloading sessions with auto-incrementing lot numbers, dates, quantities, and notes |
| **Cost Analysis** | Break-even chart showing when reloading pays off after equipment investment |
| **Cost Comparison** | Side-by-side cost breakdown for selected reload and factory entries |

A sixth **Editor** tab appears automatically whenever you are adding or editing an ammo entry.

There are also built-in **Tour**, **About**, and **Settings** controls in the top navigation area. Tour launches a guided walkthrough of the main areas of the application, About shows application/version/author/license information, and Settings lets you adjust display preferences such as theme behavior, currency symbol, and cost precision.

![Reloading Tracker — main application and navigation tabs](./images/header-tabs.png)

---

## 2. My Ammo

The **My Ammo** tab is where you build and maintain your ammunition library. Entries are grouped by type — reloads first, then factory ammo (sorted cheapest to most expensive within each group). Each group has a colored section header with a **+** button to add a new entry of that type directly.

![Screenshot: My Ammo tab showing reload and factory cards](./images/my-ammo.png)

### 2.1 Adding a Reload Entry

Click **Add Ammo** in the top-right corner of the My Ammo tab, or click the **+** button in the **Reloads** section header. The Editor tab will open with **Reload** pre-selected as the load type. Fill in the following sections:

**Ammo Information**
- **Name** — to identify the cartridge. Required.
- **Load Type** — Reload or Factory.
- **Caliber** — the cartridge designation (e.g. *9mm Luger*, *.308 Win*). Required.
- **Notes** — Optional free-text field for COAL, dates, or any other reference.

**Powder**
- Powder name, measurement system (Imperial grains or Metric grams), price per lb/kg, and charge weight per round.

**Primers**
- Primer name, price, and the quantity that price covers (default 100).

**Bullets / Projectiles**
- Bullet description, price, and quantity (default 100).

**Brass / Cases**
- Brass description, price, quantity, and how many times each case will be reloaded before replacement. The cost per round is divided by this reuse count.

**Sales Tax**
- The sales tax percentage applied to your total component cost.

A **Live Preview** panel on the right updates in real time as you type, showing the per-round cost breakdown and totals for 50, 100, and 1000 rounds.

![Screenshot: Load editor — Reload Data form with live preview](./images/load-editor.png)

Click **Save Load** or **Update Load** when done. The entry appears immediately in My Ammo and becomes available in Cost Comparison and Cost Analysis.

### 2.2 Adding a Factory Ammo Entry

Click **Add Ammo** or the **+** button in the **Factory** section header. The Editor opens with **Factory Ammo** pre-selected. The form shows:

**Base Factory Price**
- Price per box and rounds per box.

**Factory Taxes**
- Sales tax (%), State excise tax (%).

**Additional Fixed Cost**
- A flat fee spread over a number of rounds — useful for background check fees (e.g. $25 over 500 rounds = $0.05/rd extra) if applicable in your State.

![Screenshot: Load editor — Factory Ammo Data form](images/factory-ammo.png)

### 2.3 Managing Ammo Entries

Each ammo card has three action buttons in its top-right corner:

| Button | Action |
|--------|--------|
| ✏️ Edit | Opens the entry in the Editor tab |
| ⧉ Duplicate | Creates a copy of the entry (useful for variants of the same load) |
| 🗑 Delete | Permanently removes the entry |

Click the **▸ / ▾** chevron on the left of the action buttons to expand a card and see the full component cost breakdown.

Use the **Search** box to filter cards by name, caliber, type, or component name.

You can also switch between **Card** and **Table** views using the view toggle next to the search box. Card view shows the familiar expandable cards, while Table view gives you a denser list that is easier to scan when you have many entries.

![Screenshot: Expanded ammo card showing component breakdown](images/ammo-viewer.png)

### 2.4 Default Taxes & Fees

At the top of My Ammo there is a **Default Taxes** panel. Values set here are used to pre-populate the tax fields whenever you create a new entry, saving repetitive data entry.

- **Reload** — sales tax percentage applied to reload component costs.
- **Factory** — sales tax %, excise tax %, fixed fee amount, and the number of rounds that fee covers.

Click **Apply to All** to update every existing entry in your library with the current defaults at once.

![Screenshot: Default Taxes panel](images/default-taxes.png)

You can also reset taxes to defaults on a per-entry basis using the **Reset to defaults** link inside the Editor.

---

## 3. My Components

The **My Components** tab is a global catalog of reloading components. Instead of typing the same powder name, price, and quantity into every load, you define each component once here and then select it from a dropdown when editing any reload. If a component price changes, update it in the inventory and every linked load updates automatically.

![Screenshot: My Components tab showing grouped components with filter tags](./images/my-inventory.png)

Components are organised into four types: **Powder**, **Primer**, **Bullet**, and **Brass**. They are displayed in grouped sections, each with a colored left-border accent that matches the component's icon.

**Filter tags** at the top of the list let you narrow the view to a single type at a glance; click a tag to activate it, click again to clear the filter.

![Screenshot: My Components — filter tags and grouped sections](./images/inventory-filter-tags.png)

Use the **Search** box to filter components by name or notes across all groups.

Like My Ammo, My Components also supports **Card** and **Table** views through the view toggle near the search box.

### 3.1 Adding a Component

Click **Add Component** in the top-right corner, or click the small **+** button in any group header to pre-select that component type.

**Component Type**  
Choose one of the four types using the selector buttons at the top of the form. Once a component is saved the type cannot be changed — duplicate it and delete the original if you need a different type.

**Name / Description** *(required)*  
A descriptive label, e.g. *Titegroup*, *CCI 500 Small Pistol*, *124gr FMJ RN*, *Mixed once-fired 9mm*.

**Price** *(required)*  
The price you paid for the component. For powders this is the price per pound (Imperial) or per kilogram (Metric). For all other types it is the total price for the quantity below.

**Quantity / Weight** *(required)*  
- *Powder* — the weight the price covers (lbs or kg). A 1 lb jug entered at $28.99/1 lb stores as $28.99/lb; a 4 lb jug entered at $89.99/4 lb also resolves to the correct per-lb rate when used in a load.
- *Primer, Bullet, Brass* — the number of units the price covers (e.g. 100 primers for $15.99).

**Measurement System** *(powder only)*  
Select **Imperial (lb)** or **Metric (kg)**. This carries through to any load that links to this powder.

**Times Reloaded** *(brass only)*  
How many reloads each case is expected to survive before replacement. This amortises the brass cost across that many rounds.

**Notes**  
Optional free-text field for lot numbers, suppliers, or any other reference.

Click **Save** to add the component. The card appears immediately in its group.

![Screenshot: Add/Edit component form panel](./images/inventory-add-form.png)

Each component card shows:
- Component name and type icon
- **Price** — the raw price as entered (e.g. *$89.99 / 4 lb*)
- **Per unit** — the derived cost per lb/kg or per single primer/bullet/case (e.g. *$22.50/lb*)
- Brass **Reloads** count (brass cards only)
- Notes (if any)

![Screenshot: Inventory card showing price and per-unit fields](./images/inventory-card.png)

### 3.2 Managing Components

Each component card has three action buttons:

| Button | Action |
|--------|--------|
| ✏️ Edit | Opens the component in the form panel for editing. The type selector is disabled — type cannot be changed after creation. |
| ⧉ Duplicate | Creates a copy with *(copy)* appended to the name — useful when a component comes in multiple package sizes. |
| 🗑 Delete | Permanently removes the component from the catalog. Loads that were linked to it retain their last-known values but lose the live link. |

![Screenshot: Inventory card action buttons](./images/inventory-card-actions.png)

### 3.3 Linking Inventory to Loads

When editing or creating a reload in the **Editor** tab, each component section (Powder, Primers, Bullets, Brass) has a **Select from inventory** dropdown above the manual input fields. Choosing an item from that dropdown fills all the related fields automatically and marks the component with a **linked badge**.

![Screenshot: Load editor with inventory dropdown and linked badge](./images/inventory-link-badge.png)

**What the linked badge means:**  
A small inventory icon appears next to the component name to indicate the values are driven by the inventory. If you manually edit any field in that section the link is broken automatically and the badge disappears — the load then stores its own independent copy of those values.

You can also click the **×** on the badge to unlink intentionally without editing any field.

**Auto-update behaviour:**  
When you edit a component in My Components (e.g. update a powder price after buying a new jug), every reload that is still linked to that component has its cost recalculated immediately. No manual re-entry is needed.

**Inventory badge in My Ammo:**  
In the expanded card view under My Ammo, any component that originates from the inventory shows a small inventory icon next to its name, so you can tell at a glance which values are managed centrally.

![Screenshot: Expanded ammo card showing inventory link badges on components](./images/inventory-badge-card.png)

---

## 4. Reloading Journal

The **Journal** tab is your session log. Every time you sit down at the press, add an entry with the load you reloaded, the quantity you produced, and the date. Each entry automatically receives a unique, incrementing **lot number** that you can print on an ammo box label.

![Screenshot: Journal tab showing the session list, add row at the bottom, and the summary panel](./images/journal-overview.png)


### 4.1 Logging a Session

The **add row** at the bottom of the session list always shows the next available lot number. Fill in:

| Field | Description |
|-------|-------------|
| **Date** | The date of the session (defaults to today) |
| **Load** | Select from your reload entries |
| **Qty** | Number of rounds produced |
| **Notes** | Optional — store a powder lot, seating depth, or any other reference |

Click **+** or press **Enter** in any field to save the entry. It appears at the top of the list and the lot number advances automatically.

**Starting lot number**  
At the top right of the Journal page you can set the **Starting lot #**. This controls the lot number assigned to the very first entry. Subsequent entries always increment from the highest existing lot, so changing this value only affects a brand-new journal. Use it to align with a lot series you were already tracking elsewhere.

### 4.2 Managing Journal Entries

Each entry row has three action buttons on the right:

| Button | Action |
|--------|--------|
| ✏️ Edit | Edits all fields inline — lot number is fixed and cannot be changed |
| 🖨 Print | Opens the label print dialog pre-filled with the lot number and quantity |
| 🗑 Delete | Permanently removes the entry |

Use the **Search** box at the top of the page to filter entries by lot number, date, load name, caliber, or notes.

### 4.3 Printing a Lot Label

Click the **Print** button on any journal entry to open the label print dialog. The **LOT** and **QTY** fields are pre-filled from the entry — you only need to confirm and print.

The label dialog lets you review and adjust every field on the label before committing:

- **Load name and caliber** — taken from the linked reload entry
- **LOT** — pre-filled with the entry's lot number
- **QTY** — pre-filled with the number of rounds logged
- All other label fields (powder, primer, bullet, brass, COAL, notes) are pulled from the load definition

You can also open the print dialog from any ammo card in **My Ammo** using the print button on that card, without a pre-filled lot number.

![Screenshot: print label dialog showing LOT and QTY pre-filled from a journal entry.](./images/label-print.png)

### 4.4 Journal Statistics

The **summary panel** on the right of the Journal tab shows:

- **Rounds by Load** — total rounds produced for each reload, sorted by volume
- **Total cost** per load — rounds × cost per round for that load
- **Grand total rounds** and **grand total cost** across all entries

These figures accumulate automatically as you add entries. The cost per round used in the calculation is always the current cost from your load definition.

---

## 5. Cost Comparison

The **Cost Comparison** tab lets you select any combination of reload and factory entries and compare their costs side by side.

![Screenshot: Cost Comparison tab with entries selected](./images/comparison-selection.png)

**Selecting entries**  
Click any entry in the selection list to toggle it on or off. Selected entries are highlighted — green for reloads, amber for factory ammo. You can select multiple reloads and multiple factory entries simultaneously.

**Reading the comparison**  
Once entries are selected, the view shows:

- A **bar chart** of cost per round for every selected entry.
- A **cost table** with totals for 50, 100, and 1,000 rounds for each entry.
- A **Difference** section (visible when at least one reload and one factory entry are selected) showing how much cheaper your reload is per round, per 50, per 100, and per 1,000 rounds.

Use the **Search** box above the selection list to filter by name, caliber, type, or component.

![Screenshot: Cost Comparison — bar chart and difference table](./images/cost-comparison.png)
![Screenshot: Cost Comparison — difference table](./images/cost-break-down.png)

---

## 6. Cost Analysis (Break-Even)

The **Cost Analysis** tab shows how the cumulative cost of reloading (including your one-time equipment investment) compares to buying factory ammo over time, and at what point reloading becomes cheaper overall.

> 📷 **IMAGE NEEDS REVIEW** — `cost-analysis.png` — the title/subtitle area is now sticky and stays visible while scrolling. The stats card and chart also remain fixed while the load selection and equipment columns scroll independently.

![Screenshot: Cost Analysis tab — full view](images/cost-analysis.png)

### 6.1 Load Selection

The left column lists all your reload and factory entries.

By default, both reloads and factory ammo use **checkbox selection**. Check the entries you want to include in the averages. If nothing is checked, **all entries of that type are included automatically**.

![Screenshot: Load Selection panel with checkboxes](./images/load-selection.png)

For reloads only, you can also switch to **Rounds** mode using the flip switch at the top of the panel. In this mode:

- Reload entries accept a round count instead of a checkbox.
- The app calculates a **weighted average reload cost** based on the number of rounds entered for each reload.
- Factory ammo remains checkbox-based even in this mode.

![Screenshot: Load Selection panel with costs](./images/load-selection-costs.png)

**Journal integration in Rounds mode**

The round counts you log in the **Journal** tab are automatically reflected here. The number shown next to each reload's input is its *effective total*: the value you manually entered (your pre-journal baseline) plus the rounds logged in the journal.

This is designed for reloaders who were already pressing ammo before starting the journal. Enter your historical round count in the input as a baseline; the journal adds to it going forward. If you start fresh, leave the input at zero and the journal fills it in automatically.

### 6.2 Equipment Costs

The right column is where you enter your one-time reloading equipment costs (press, dies, tumbler, scale, etc.)

- Type a name and price in the **New item** row and press **Enter** or click **+** to add it.
- Click **✕** to remove an item.
- The running **Total Equipment Cost** is shown at the bottom.

This total is treated as an upfront investment that your per-round savings must recover before reloading becomes net-positive.

This cost can be ignored by switching off the **Include** switch.

![Screenshot: Equipment Costs panel with several items entered](./images/equipment-costs.png)

### 6.3 Reading the Chart & Stats

The **stats bar** across the middle column shows the main values used in the break-even calculation:

| Stat | Meaning |
|------|---------|
| **Avg Reload Cost** | Average cost per round across selected reload entries |
| **Avg Factory Cost** | Average cost per round across selected factory entries |
| **Savings per Round** | Factory average minus reload average |
| **Break-Even Point** | Number of rounds until cumulative savings cover total equipment cost |

When **Rounds** mode is enabled for reloads, additional progress values appear:

| Stat | Meaning |
|------|---------|
| **Reload Rounds Logged** | Total effective rounds (manual baseline + journal) across all reload recipes |
| **Rounds Remaining** | How many more reload rounds are needed to reach break-even |
| **Total Savings So Far** | Current savings based on the effective reload rounds, optionally net of equipment when **Include** is enabled |

The **chart** below plots two lines:
- **Reload line** — cumulative spend including the equipment investment upfront, declining in slope as per-round costs are cheaper than factory.
- **Factory line** — cumulative spend at factory prices with no upfront cost.

The point where the lines cross is the **break-even point**, marked on the chart. After that point, every round you reload puts money back in your pocket.

In reload **Rounds** mode, the chart also shows your **current position** on the timeline based on the total effective reload rounds, making it easier to see how far along you are toward break-even.

If the reload average is higher than the factory average (reloading is more expensive per round), the lines never cross and a warning is shown.

![Screenshot: Break-even chart showing the intersection point](./images/analysis.png)

---

## 7. Guided Tour

Click **Tour** in the top navigation bar to start the built-in walkthrough at any time.

The guided tour highlights the major parts of the application and explains:

- how to add and manage ammo entries
- how to use the inventory and linked components
- how to log reloading sessions in the Journal and assign lot numbers
- how to compare reloads and factory ammo
- how to use the break-even analysis
- how to switch between simple selection and reload round-count analysis
- which values to check in the analysis stats cards

The tour can be dismissed at any time and is designed to help first-time users get oriented quickly.

---

## 8. Settings & About

The top-right area of the header includes both an **About** button and a **Settings** button.

**Settings**
- **Follow Time Of Day** — automatically uses the light theme during the day and dark theme in the evening
- **Currency Symbol** — changes the currency shown across cards, tables, and analysis views
- **Cost Per Round Decimals** — controls how many decimal places are shown for per-round costs

![Screenshot: Settings showing the configuration of the application](./images/app-settings.png)

The application still defaults to the **dark theme** on first launch. If you enable **Follow Time Of Day**, the app will switch themes automatically based on the time of day. You can still use the theme toggle in the header to return immediately to manual light/dark mode.

---

## 9. Import & Export

Your entire library — ammo entries, tax defaults, equipment costs, load selections, component inventory, **and your full reloading journal** — can be saved to a single JSON file and restored later or shared with another computer.

**Exporting**  
Click **Export** in the top navigation bar. A `.json` file will be downloaded to your machine.

**Importing**  
Click **Import** and select a previously exported `.json` file. All data in the file will replace the current library.

> WARNING: Import overwrites your current data. Export first if you want to keep your existing entries.

> 📷 **IMAGE NEEDS REVIEW** — `header-tabs.png` — used here to show the Export/Import buttons; needs retaking with the updated navigation.

![Screenshot: Export and Import buttons in the navigation bar](./images/header-tabs.png)

---

## 10. Tips & Notes

- **All data is stored locally.** No account or internet connection is required. Data is saved automatically in the browser/app storage every time you make a change.
- **Brass reuse count matters.** Setting a realistic reuse count (commonly 5–10 reloads per case) significantly lowers your per-round brass cost. A count of 1 treats every case as single-use.
- **State Excise Tax (SET).** Factory ammunition in some US States is subject to a state excise tax in addition to state and local sales tax. The default value is pre-filled for you.
- **Fix Fee (FF).** Some US States have an additional fix fee (normally associated to a background check) on any ammunition purchases. This is a fixed fee and applied to the entire purchase and its cost is diluted over all the rounds purchased.
- **Accuracy of results.** All costs are estimates based on the prices you enter. Check current component and ammo prices regularly — they fluctuate.
- **Duplicating entries** is a quick way to model variants: duplicate a load, change the powder charge or bullet weight, and compare side by side in the Cost Comparison tab.
- **Equipment costs** only need to be entered once. They persist between sessions and are included in export files.
- **Use the inventory for shared components.** If you load multiple calibers with the same powder or primer, define it once in My Components and link it to all relevant loads. A single price update flows through everywhere.
- **Inventory lists are alphabetical.** Components inside each inventory group are ordered by name to make powders, primers, bullets, and brass easier to scan.
- **Powder quantity field.** When entering a powder in the inventory, set the quantity to match how the powder is sold — 1 lb, 4 lb, 8 lb, etc. The app calculates the per-lb rate automatically and uses it when costing a load.
- **Unlinking a component.** Manually editing any field in a linked component section (name, price, quantity) automatically breaks the inventory link. The load keeps the values you typed but is no longer updated when the inventory item changes. Use the **×** on the badge to unlink without changing any values.
- **Deleting an inventory item** does not delete any loads that used it. Those loads retain the component values they had at the time the link was broken.
- **Journal lot numbers never repeat.** Deleting an entry does not reuse its lot number — the next entry always increments from the highest existing lot. This ensures labels are always unique.
- **Journal baseline for existing reloaders.** If you were reloading before you started using the journal, enter your historical round count as the manual baseline in Cost Analysis Rounds mode. The journal will add to it going forward, keeping your break-even progress accurate.
- **Label printing from the journal.** The quickest way to print a box label is directly from the Journal — the lot number and quantity are already filled in. You only need to confirm and print.
