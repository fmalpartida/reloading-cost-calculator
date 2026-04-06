# Reload Cost Calculator — User Guide

Reload Cost Calculator is an application that helps you compare the true cost of reloading your own ammunition against buying factory-loaded rounds. It accounts for component prices, taxes, fixed fees, and one-time equipment purchases to give you a clear picture of your real savings or costs.

[Try it out](https://fmalpartida.github.io/reloading-cost-calculator)

---

## Table of Contents

1. [Overview](#1-overview)
2. [My Ammo](#2-my-ammo)
   - [Adding a Reload Entry](#21-adding-a-reload-entry)
   - [Adding a Factory Ammo Entry](#22-adding-a-factory-ammo-entry)
   - [Managing Entries](#23-managing-entries)
   - [Default Taxes & Fees](#24-default-taxes--fees)
3. [My Inventory](#3-my-inventory)
   - [Adding a Component](#31-adding-a-component)
   - [Managing Components](#32-managing-components)
   - [Linking Inventory to Loads](#33-linking-inventory-to-loads)
4. [Cost Comparison](#4-cost-comparison)
5. [Cost Analysis (Break-Even)](#5-cost-analysis-break-even)
   - [Load Selection](#51-load-selection)
   - [Equipment Costs](#52-equipment-costs)
   - [Reading the Chart & Stats](#53-reading-the-chart--stats)
6. [Guided Tour](#6-guided-tour)
7. [Import & Export](#7-import--export)
8. [Tips & Notes](#8-tips--notes)

---

## 1. Overview

The application has three main tabs accessible from the navigation bar at the top:

| Tab | Purpose |
|-----|---------|
| **My Ammo** | Library of all your ammo entries — reloads and factory |
| **Cost Comparison** | Side-by-side cost breakdown for selected reload and factory entries |
| **Cost Analysis** | Break-even chart showing when reloading pays off after equipment investment |
| **My Inventory** | Global catalog of reloading components — powders, primers, bullets, and brass |

A fifth **Editor** tab appears automatically whenever you are adding or editing an ammo entry.

There is also a built-in **Tour** button in the top navigation bar. It launches a guided walkthrough of the main areas of the application, including My Ammo, My Inventory, Cost Comparison, and the break-even analysis workflow.

![Reload Cost Calculator — main application and navigation tabs](./images/header-tabs.png)

---

## 2. My Ammo

The **My Ammo** tab is where you build and maintain your ammunition library. Entries are grouped by type — reloads first, then factory ammo — and sorted cheapest to most expensive within each group.

![Screenshot: My Ammo tab showing reload and factory cards](./images/my-ammo.png)

### 2.1 Adding a Reload Entry

Click **Add Ammo** in the top-right corner of the My Ammo tab. The Editor tab will open. Set the **Load Type** to **Reload** and fill in the following sections:

**Ammo Information**
- **Name** - to for the cartridge to identify it. Required.
- **Load Type** - Reload or Factory
- **Caliber** — the cartridge designation (e.g. *9mm Luger*, *.308 Win*). Required.
- **Notes** - Optional free-text field for COAL, dates, lot numbers, or any other reference.

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

Set the **Load Type** to **Factory Ammo**. The form changes to:

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

![Screenshot: Expanded ammo card showing component breakdown](images/ammo-viewer.png)

### 2.4 Default Taxes & Fees

At the top of My Ammo there is a **Default Taxes** panel. Values set here are used to pre-populate the tax fields whenever you create a new entry, saving repetitive data entry.

- **Reload** — sales tax percentage applied to reload component costs.
- **Factory** — sales tax %, excise tax %, fixed fee amount, and the number of rounds that fee covers.

Click **Apply to All** to update every existing entry in your library with the current defaults at once.

![Screenshot: Default Taxes panel](images/default-taxes.png)

You can also reset taxes to defaults on a per-entry basis using the **Reset to defaults** link inside the Editor.

---

## 3. My Inventory

The **My Inventory** tab is a global catalog of reloading components. Instead of typing the same powder name, price, and quantity into every load, you define each component once here and then select it from a dropdown when editing any reload. If a component price changes, update it in the inventory and every linked load updates automatically.

![Screenshot: My Inventory tab showing grouped components with filter tags](./images/my-inventory.png)

Components are organised into four types: **Powder**, **Primer**, **Bullet**, and **Brass**. They are displayed in grouped sections, each with a colored left-border accent that matches the component's icon.

**Filter tags** at the top of the list let you narrow the view to a single type at a glance — click a tag to activate it, click again to clear the filter.

![Screenshot: My Inventory — filter tags and grouped sections](./images/inventory-filter-tags.png)

Use the **Search** box to filter components by name or notes across all groups.

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
When you edit a component in My Inventory (e.g. update a powder price after buying a new jug), every reload that is still linked to that component has its cost recalculated immediately. No manual re-entry is needed.

**Inventory badge in My Ammo:**  
In the expanded card view under My Ammo, any component that originates from the inventory shows a small inventory icon next to its name, so you can tell at a glance which values are managed centrally.

![Screenshot: Expanded ammo card showing inventory link badges on components](./images/inventory-badge-card.png)

---

## 4. Cost Comparison

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

## 5. Cost Analysis (Break-Even)

The **Cost Analysis** tab shows how the cumulative cost of reloading (including your one-time equipment investment) compares to buying factory ammo over time, and at what point reloading becomes cheaper overall.

![Screenshot: Cost Analysis tab — full view](images/cost-analysis.png)

### 5.1 Load Selection

The left column lists all your reload and factory entries.

By default, both reloads and factory ammo use **checkbox selection**. Check the entries you want to include in the averages. If nothing is checked, **all entries of that type are included automatically**.

![Screenshot: Load Selection panel with checkboxes](./images/load-selection.png)

For reloads only, you can also switch to **Rounds** mode using the flip switch at the top of the panel. In this mode:

- Reload entries accept a round count instead of a checkbox.
- The app calculates a **weighted average reload cost** based on the number of rounds entered for each reload.
- Factory ammo remains checkbox-based even in this mode.

![Screenshot: Load Selection panel with costs](./images/load-selection-costs.png)

This is useful when you want the break-even math to reflect your real production mix instead of treating every selected reload equally.

In addition, you can track your reloading journey and keep track of where you stand with respect to your costs or savings.



### 5.2 Equipment Costs

The right column is where you enter your one-time reloading equipment costs (press, dies, tumbler, scale, etc.)

- Type a name and price in the **New item** row and press **Enter** or click **+** to add it.
- Click **✕** to remove an item.
- The running **Total Equipment Cost** is shown at the bottom.

This total is treated as an upfront investment that your per-round savings must recover before reloading becomes net-positive.

This cost can be ignored by switching off the **Include** switch.

![Screenshot: Equipment Costs panel with several items entered](./images/equipment-costs.png)

### 5.3 Reading the Chart & Stats

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
| **Reload Rounds Logged** | Total reload rounds currently entered across all reload recipes |
| **Rounds Remaining** | How many more reload rounds are needed to reach break-even |
| **Total Savings So Far** | Current savings based on the entered reload rounds, optionally net of equipment when **Include** is enabled |

The **chart** below plots two lines:
- **Reload line** — cumulative spend including the equipment investment upfront, declining in slope as per-round costs are cheaper than factory.
- **Factory line** — cumulative spend at factory prices with no upfront cost.

The point where the lines cross is the **break-even point**, marked on the chart. After that point, every round you reload puts money back in your pocket.

In reload **Rounds** mode, the chart also shows your **current position** on the timeline based on the total reload rounds you have entered, making it easier to see how far along you are toward break-even.

If the reload average is higher than the factory average (reloading is more expensive per round), the lines never cross and a warning is shown.

![Screenshot: Break-even chart showing the intersection point](./images/analysis.png)

---

## 6. Guided Tour

Click **Tour** in the top navigation bar to start the built-in walkthrough at any time.

The guided tour highlights the major parts of the application and explains:

- how to add and manage ammo entries
- how to use the inventory and linked components
- how to compare reloads and factory ammo
- how to use the break-even analysis
- how to switch between simple selection and reload round-count analysis
- which values to check in the analysis stats cards

The tour can be dismissed at any time and is designed to help first-time users get oriented quickly.

---

## 7. Import & Export

Your entire library — ammo entries, tax defaults, equipment costs, load selections, **and your full component inventory** — can be saved to a single JSON file and restored later or shared with another computer.

**Exporting**  
Click **Export** in the top navigation bar. A `.json` file will be downloaded to your machine.

**Importing**  
Click **Import** and select a previously exported `.json` file. All data in the file will replace the current library.

> WARNING: Import overwrites your current data. Export first if you want to keep your existing entries.

![Screenshot: Export and Import buttons in the navigation bar](./images/import-export.png)

---

## 8. Tips & Notes

- **All data is stored locally.** No account or internet connection is required. Data is saved automatically in the browser/app storage every time you make a change.
- **Brass reuse count matters.** Setting a realistic reuse count (commonly 5–10 reloads per case) significantly lowers your per-round brass cost. A count of 1 treats every case as single-use.
- **State Excise Tax (SET).** Factory ammunition in some US States is subject to a state excise tax in addition to state and local sales tax. The default value is pre-filled for you.
- **Fix Fee (FF).** Some US States have an additional fix fee (normally associated to a background check) on any ammunition purchases. This is a fixed fee and applied to the entire purchase and its cost is diluded over all the rounds purchased.
- **Accuracy of results.** All costs are estimates based on the prices you enter. Check current component and ammo prices regularly — they fluctuate.
- **Duplicating entries** is a quick way to model variants: duplicate a load, change the powder charge or bullet weight, and compare side by side in the Cost Comparison tab.
- **Equipment costs** only need to be entered once. They persist between sessions and are included in export files.
- **Use the inventory for shared components.** If you load multiple calibers with the same powder or primer, define it once in My Inventory and link it to all relevant loads. A single price update flows through everywhere.
- **Inventory lists are alphabetical.** Components inside each inventory group are ordered by name to make powders, primers, bullets, and brass easier to scan.
- **Powder quantity field.** When entering a powder in the inventory, set the quantity to match how the powder is sold — 1 lb, 4 lb, 8 lb, etc. The app calculates the per-lb rate automatically and uses it when costing a load.
- **Unlinking a component.** Manually editing any field in a linked component section (name, price, quantity) automatically breaks the inventory link. The load keeps the values you typed but is no longer updated when the inventory item changes. Use the **×** on the badge to unlink without changing any values.
- **Deleting an inventory item** does not delete any loads that used it. Those loads retain the component values they had at the time the link was broken.
