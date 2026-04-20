# Reloading Tracker 2.3.1-beta.1: User Guide

Reloading Tracker is an application for managing your reloading activity. At its core it is a production log: define your loads, record each pressing session with a unique lot number, and print a label for every box on your shelf. If you also want to understand the economics of reloading, the application goes further, comparing the cost of your reloads against factory ammunition, tracking your progress toward break-even, and accounting for component prices, taxes, fixed fees, and one-time equipment purchases.

[Try it out](https://fmalpartida.github.io/reloading-cost-calculator)

## ⚠️ IMPORTANT SAFETY DISCLAIMER ⚠️

> **WARNING: DO NOT USE THE LOAD DATA IN THIS GUIDE.**
>
> Any load recipe shown in this guide (powder charges, bullet weights, COALs, or any other reloading data) is for **illustration purposes only**. These values are **not safe for use** in actual reloading.
>
> **Always build your loads from reliable, published reloading data** from reputable sources such as powder manufacturers, bullet manufacturers, or established reloading manuals. Never copy load data from screenshots, examples, or guides like this one.
>
> Improper reloading can result in serious injury, death, or property damage.

---

## Table of Contents

1. [Overview](#1-overview)
   - [Recommended Workflow](#recommended-workflow)
   - [Tabs at a Glance](#tabs-at-a-glance)
2. [My Ammo](#2-my-ammo)
   - [Adding a Reload Entry](#21-adding-a-reload-entry)
   - [Adding a Factory Ammo Entry](#22-adding-a-factory-ammo-entry)
   - [Managing Entries](#23-managing-entries)
   - [Load Status](#load-status)
   - [Default Taxes & Fees](#24-default-taxes--fees)
   - [Charge Workup (Load Development)](#25-charge-workup-load-development)
3. [My Components](#3-my-components)
   - [Adding a Component](#31-adding-a-component)
   - [Managing Components](#32-managing-components)
   - [Linking Inventory to Loads](#33-linking-inventory-to-loads)
4. [Reloading Journal](#4-reloading-journal)
   - [Logging a Session](#41-logging-a-session)
   - [Managing Journal Entries](#42-managing-journal-entries)
   - [Printing a Lot Label](#43-printing-a-lot-label)
   - [Journal Statistics](#44-journal-statistics)
5. [Range Log](#5-range-log)
   - [Logging a Range Session](#51-logging-a-range-session)
   - [Managing Range Sessions](#52-managing-range-sessions)
   - [Starring Sessions](#53-starring-sessions)
   - [Range Log Statistics](#54-range-log-statistics)
6. [Cost Analysis (Break-Even)](#6-cost-analysis-break-even)
   - [Load Selection](#61-load-selection)
   - [Equipment Costs](#62-equipment-costs)
   - [Reading the Chart & Stats](#63-reading-the-chart--stats)
7. [Cost Comparison](#7-cost-comparison)
8. [Guided Tour](#8-guided-tour)
9. [Settings & About](#9-settings--about)
10. [Import & Export](#10-import--export)
11. [Tips & Notes](#11-tips--notes)

---

## 1. Overview

### Recommended Workflow

Reloading Tracker follows a natural progression that mirrors the way reloading actually works. The first three steps are the core workflow, useful for any reloader regardless of whether you care about costs. Step 4 is for those who also want to track cost and break-even progress.

![Reloading Tracker: main application and navigation tabs](./images/header-tabs.png)

**Step 1: Define your loads**

Before you can log sessions, the application needs to know what you are reloading. You have two ways to add a load:

- **Direct entry in My Ammo.** Open the Editor tab and fill in the load details. This is the fastest way to get started.
- **Build a component library first (recommended).** Go to **My Components** and add your powders, primers, bullets, and brass. Then, when you create a load in My Ammo, select each component from the inventory instead of typing values by hand. Any future price change (a new jug of powder, a bulk primer buy) only needs to be updated in one place, and every load that uses that component recalculates automatically.

> **If you plan to use the cost features**, accuracy starts with the prices you enter. Use the actual prices you paid, including shipping if it meaningfully affects the per-unit cost. Update component prices when you buy a new batch. The closer your entries are to real-world costs, the more the numbers you see will reflect your true reloading economics rather than a rough estimate.

If you use Cost Analysis or Cost Comparison, also add at least one **factory ammo** entry (with its box price, taxes, and any fixed fees) so the comparison and break-even analysis have a meaningful baseline to work against.

**Step 2a (optional): Work up a new load**

If you are developing a new load from scratch, set its status to **In Development** and configure a **Charge Ladder** in the Editor. Then open the **Charge Workup** panel (ladder icon on the load card or table row) to manage the full development cycle — plan charges, batch-log pressing sessions, track velocity and accuracy results from the range, and promote the winning charge to your final load definition when done. See [Charge Workup](#25-charge-workup-load-development) for the full workflow.

**Step 2b: Log your pressing sessions in the Journal**

Every time you sit down at the press, open the **Journal** tab and add an entry: select the load, enter the date and the number of rounds you produced. The application assigns a unique, incrementing lot number automatically.

This is where the application starts working for you over time. Each session builds a complete production history: what you made, when you made it, and how much. That record is valuable on its own as a traceable log of every batch you have ever pressed, and it also feeds directly into Cost Analysis if you want to track your progress toward break-even.

**Step 3: Print lot labels**

After logging a pressing session, click the **Print** button on the journal entry. The label dialog opens with the lot number and quantity already filled in from the session. Review the label (load name, caliber, components, COAL) and print. Attach it to the ammo box before it goes on the shelf. Every box in your storage is now traceable back to a specific lot in the journal. You can also print an additional label for your reloading log book.

**Step 4: Take it to the range and log the session**

After a range trip, open the **Range Log** tab and add a session: choose the firearm you used, the date, the distance you shot, and the lots you burned through. You can record multiple lots in a single outing — each with its own round count, charge weight, COAL, and notes — so each lot tells you exactly how it performed at the range.

Over time the Range Log becomes a searchable field record that connects every range session to the specific lots and load recipes that produced it. Star sessions that produced exceptional results so you can find them later; use the starred filter to pull up only your reference loads when you are at the bench deciding what to reload next.

> **The bench-to-range loop.** The Journal and the Range Log together close the loop on every batch of ammo you press. The Journal tells you what you made and when. The Range Log tells you how each lot performed when it counted. Together, they make it straightforward to decide which loads are worth pressing again and which recipes to refine.

**Step 5 (optional): Review your costs and track break-even**

With pressing sessions accumulating in the journal, open **Cost Analysis** and switch to **Rounds** mode. Your journal rounds are automatically added to your reload entries. Watch the break-even chart as your position on the reload line advances toward the intersection with factory costs. The stats panel shows you exactly how many rounds remain until your equipment pays for itself, and how much you have already saved.

Use **Cost Comparison** at any time to see side-by-side which of your loads is the most economical, or to check whether a specific factory ammo purchase would have been cheaper than your reload for that caliber.

---

The more consistently you log your sessions, the more the application rewards you. A year of journal and range-log entries is both a complete production and performance record of every lot you have ever pressed and, if you use the cost features, a genuine financial picture of what reloading saves you.

---

### Tabs at a Glance

The application has six main tabs accessible from the navigation bar at the top:

| Tab | Purpose |
|-----|---------|
| **My Ammo** | Library of all your ammo entries: reloads and factory |
| **My Components** | Global catalog of reloading components: powders, primers, bullets, and brass |
| **Journal** | Log pressing sessions with auto-incrementing lot numbers, dates, quantities, and notes |
| **Range Log** | Record range sessions: firearm, distance, lots fired, round counts, performance notes |
| **Cost Analysis** | Break-even chart showing when reloading pays off after equipment investment |
| **Cost Comparison** | Side-by-side cost breakdown for selected reload and factory entries |

A seventh **Editor** tab appears automatically whenever you are adding or editing an ammo entry.

There are also built-in **Tour**, **About**, and **Settings** controls in the top navigation area. Tour launches a guided walkthrough of the main areas of the application, About shows application/version/author/license information, and Settings lets you adjust display preferences such as theme behavior, currency symbol, and cost precision.

![Reloading Tracker: main application and navigation tabs](./images/header-tabs.png)

---

## 2. My Ammo

The **My Ammo** tab is where you build and maintain your ammunition library. Entries are grouped by type: reloads first, then factory ammo (sorted cheapest to most expensive within each group). Each group has a colored section header with a **+** button to add a new entry of that type directly.

![Screenshot: My Ammo tab showing reload and factory cards](./images/my-ammo.png)

### 2.1 Adding a Reload Entry

Click **Add Ammo** in the top-right corner of the My Ammo tab, or click the **+** button in the **Reloads** section header. The Editor tab will open with **Reload** pre-selected as the load type. Fill in the following sections:

**Ammo Information**
- **Name**: identifies the cartridge. Required.
- **Load Type**: Reload or Factory.
- **Status**: the development state of the load. See [Load Status](#load-status) below.
- **Caliber**: the cartridge designation (e.g. *9mm Luger*, *.308 Win*). This is added when defining the bullet.
- **COAL**: cartridge overall length for this load. Printed on the lot label.
- **Notes**: optional free-text field for dates or any other reference.

**Powder**
- Powder name, measurement system (Imperial grains or Metric grams), price per lb/kg, and charge weight per round.

**Primers**
- Primer name, price, and the quantity that price covers (default 100).

**Bullets / Projectiles**
- Bullet description, weight, diameter, caliber, price, and quantity (default 100).

**Brass / Cases**
- Brass description, price, quantity, and how many times each case will be reloaded before replacement. The cost per round is divided by this reuse count.

**Sales Tax**
- The sales tax percentage applied to your total component cost.

A **Live Preview** panel on the right updates in real time as you type, showing the per-round cost breakdown and totals for 50, 100, and 1000 rounds.

![Screenshot: Load editor: Reload Data form with live preview](./images/load-editor.png)

Click **Save Load** or **Update Load** when done. The entry appears immediately in My Ammo and becomes available in Cost Comparison and Cost Analysis.

### 2.2 Adding a Factory Ammo Entry

Click **Add Ammo** or the **+** button in the **Factory** section header. The Editor opens with **Factory Ammo** pre-selected. The form shows:

**Base Factory Price**
- Price per box and rounds per box.

**Factory Taxes**
- Sales tax (%), State excise tax (%).

**Additional Fixed Cost**
- A flat fee spread over a number of rounds, useful for background check fees (e.g. $25 over 500 rounds = $0.05/rd extra) if applicable in your State.

![Screenshot: Load editor: Factory Ammo Data form](images/factory-ammo.png)

### 2.3 Managing Ammo Entries

Each ammo card has four action buttons in its top-right corner:

| Button | Action |
|--------|--------|
| ✏️ Edit | Opens the entry in the Editor tab |
| ⧉ Duplicate | Creates a copy of the entry (useful for variants of the same load) |
| 🖨 Print | Opens the label print dialog for this load, without a pre-filled lot number or quantity |
| 🗑 Delete | Permanently removes the entry |

Click the **▸ / ▾** chevron on the left of the action buttons to expand a card and see the full component cost breakdown.

Use the **Search** box to filter cards by name, caliber, type, or component name.

You can also switch between **Card** and **Table** views using the view toggle next to the search box. Card view shows the familiar expandable cards, while Table view gives you a denser list that is easier to scan when you have many entries.

![Screenshot: Expanded ammo card showing component breakdown](images/ammo-viewer.png)

### Load Status

Every ammo entry carries a **status** that describes where it is in your development cycle. The status badge appears on each card and in the table's Status column.

| Status | Meaning |
|--------|---------|
| **Draft** | Entered for cost estimation only; not yet range-verified. Cards show a dashed border as a visual reminder. |
| **In Development** | Actively being worked up at the bench or range. Eligible for Journal logging. Unlocks the **Charge Ladder Setup** section in the Editor and the **Charge Workup** panel on the load card. |
| **Active** | Proven load, ready to press. Eligible for Journal logging. |
| **Retired** | Recipe superseded or no longer in use. Hidden from default views but preserved in all history and journal entries. |

**Changing the status**
- In card view: expand the card (▸) and use the **Status** selector at the top of the expanded body.
- In table view: use the **Status** dropdown in the Status column.
- In the Editor: the Status field appears in the Ammo Information section next to the load type.

![Screenshot: Load Editor showing expanded load status](images/load-editor-status.png) 

**Retired loads**
Retired entries are hidden by default to keep your active library clean. When a section (Reloads or Factory) contains retired entries, a **"N retired"** link appears in that section's header bar next to the count. Click it to reveal retired loads; click **"hide retired"** to collapse them again.

![Screenshot: Ammo card showing expanded load status](images/load-card-status.png)

> **Journal and Range Log entries are never affected by status changes.** A retired load's history is fully preserved; only its visibility in the active library changes.

### 2.5 Charge Workup (Load Development)

The **Charge Workup** panel is the built-in load development workflow. It lets you plan a charge ladder, batch-log pressing sessions directly from the panel, track velocity and group-size results for each step, and promote the winning charge to your final load — all without leaving the application.

#### Setting up a charge ladder

1. Create or edit a reload entry and set **Status** to **In Development**.
2. A **Charge Ladder Setup** section appears at the bottom of the Editor form. Fill in:

| Field | Description |
|-------|-------------|
| **Min charge** | Starting charge in your ladder (e.g. 38.0 gr) |
| **Max charge** | Upper bound of the ladder (e.g. 42.0 gr) |
| **Step size** | Increment between each step (e.g. 0.5 gr) |
| **Rounds per step** | How many rounds to press at each charge weight (e.g. 20) |

3. Save the load. A **ladder icon (⟑)** now appears on the load card and in the table's action column.

<!-- TODO: screenshot — load card with ladder icon visible in the action buttons -->
![Screenshot: load card showing the ladder workup icon in the action buttons](./images/workup-ladder-icon.png)

#### The Charge Workup panel

Click the ladder icon to open the **Charge Workup** panel. It contains three main areas:

**Load info bar**

Shows the load name, caliber, and the configured ladder range (e.g. *38.0–42.0 gr · step 0.5 gr · 20 rds/step*). While the load is In Development, a small pencil button lets you edit the min/max/step/rounds directly in the bar without going back to the Editor. If a charge has been promoted, a green *Promoted: X gr* badge appears.

**Charge ladder table**

Every step in the ladder is listed as a row — planned steps (not yet pressed) and fired steps with accumulated data.

| Column | Description |
|--------|-------------|
| ☐ | Checkbox to include this charge in the next batch log |
| **Charge** | The charge weight; a ✓ badge marks the promoted charge |
| **Lot(s)** | Lot number chips for each journal entry at this charge |
| **Qty** | Total rounds pressed at this charge |
| **Sessions** | Number of range sessions that include these lots |
| **Avg fps** | Average muzzle velocity across all sessions for this charge |
| **Avg SD** | Average standard deviation |
| **Best Group** | Best (smallest) group size recorded at this charge |
| **Promote** | Button to promote this charge as the final load (only shown when data exists and the load is In Development) |

Rows with data but not yet promoted are highlighted with a subtle tint. The promoted row is highlighted in green.

The table scrolls independently of the header, so the column labels remain visible with long ladders.

<!-- TODO: screenshot — workup panel showing the charge ladder table with a mix of planned and fired rows -->
![Screenshot: Charge Workup panel — charge ladder table with planned and fired rows, promoted row highlighted](./images/workup-panel-table.png)

**Logging entries from the workup panel**

All plannable steps are checked by default. Uncheck any step you do not want to press in this session, then click **Log N Entries** in the footer. The application creates one Journal entry per checked charge, all dated today, using the configured rounds per step. A brief confirmation message appears before the panel closes.

> You can also add a **one-off charge** that is outside the configured ladder: type the charge weight in the *Add charge* field below the table and click **Add**. The row appears in the table, checked and ready to include in the next batch log, without immediately writing a journal entry.

**Performance chart**

Once at least two steps have been fired and recorded in the Range Log, a chart appears below the table:

- **Avg fps** (solid blue line, left axis): average muzzle velocity per charge weight.
- **Lot fps** (blue diamonds): individual lot velocity, one diamond per journal entry — shows the spread at each charge when multiple lots have been fired.
- **Best Group** (dashed amber line, right axis, inverted): the best group size at each charge. The axis is inverted so smaller groups (better accuracy) appear higher on the chart.
- **Lot Group** (amber diamonds): individual lot group sizes.

Hover over any line point to see the value; hover over a diamond to see which lot it belongs to. The chart is reactive to the application's light/dark theme.

<!-- TODO: screenshot — workup panel chart showing both fps and group traces with scatter diamonds -->
![Screenshot: Charge Workup panel — performance chart showing velocity and group curves with individual lot markers](./images/workup-panel-chart.png)

#### Promoting a charge

When the data shows a clear node — a charge with consistently good velocity SD and small groups — click **Promote** on that row. A confirmation dialog shows the charge being promoted.

Confirming promotion:
- Sets the load's **powder charge** to the promoted value.
- Changes the load's status to **Active**.
- **Stars** all Journal entries for the promoted charge so they are easy to find in the Journal and Range Log.
- **Unstars** any entries that belonged to a previously promoted charge (on re-promotion).

The load is now an active, proven recipe and the Charge Workup panel switches to a history view showing the full development record.

#### Starting a new development cycle

If you want to refine the load further, open the workup panel and use the **In Dev / Active** toggle in the footer. This returns the load to In Development status without clearing any data. You can then adjust the ladder range, add new steps, or press additional lots at charges of interest.

<!-- TODO: screenshot — workup panel footer showing the In Dev / Active toggle and the Log N Entries button -->
![Screenshot: Charge Workup panel footer — status toggle and Log Entries button](./images/workup-panel-footer.png)

#### Workup data in the printed data sheet

When you print a load's **Data Sheet** from the My Ammo print options, the Charge Workup section is automatically included if development data is present. The printed output shows the ladder summary, the full charge table with the promoted step marked, and a copy of the performance chart as an embedded image.

<!-- TODO: screenshot — printed data sheet showing the Charge Workup section with table and chart -->
![Screenshot: Printed load data sheet — Charge Workup section with charge table and performance chart](./images/workup-datasheet-print.png)

---

### 2.4 Default Taxes & Fees

At the top of My Ammo there is a **Default Taxes** panel. Values set here are used to pre-populate the tax fields whenever you create a new entry, saving repetitive data entry.

- **Reload**: sales tax percentage applied to reload component costs.
- **Factory**: sales tax %, excise tax %, fixed fee amount, and the number of rounds that fee covers.

Click **Apply to All** to update every existing entry in your library with the current defaults at once.

![Screenshot: Default Taxes panel](images/default-taxes.png)

You can also reset taxes to defaults on a per-entry basis using the **Reset to defaults** link inside the Editor.

---

## 3. My Components

The **My Components** tab is a global catalog of reloading components. Instead of typing the same powder name, price, and quantity into every load, you define each component once here and then select it from a dropdown when editing any reload. If a component price changes, update it in the inventory and every linked load updates automatically.

![Screenshot: My Components tab showing grouped components with filter tags](./images/my-inventory.png)

Components are organised into four types: **Powder**, **Primer**, **Bullet**, and **Brass**. They are displayed in grouped sections, each with a colored left-border accent that matches the component's icon.

**Filter tags** at the top of the list let you narrow the view to a single type at a glance; click a tag to activate it, click again to clear the filter.

![Screenshot: My Components: filter tags and grouped sections](./images/inventory-filter-tags.png)

Use the **Search** box to filter components by name or notes across all groups.

Like My Ammo, My Components also supports **Card** and **Table** views through the view toggle near the search box.

### 3.1 Adding a Component

Click **Add Component** in the top-right corner, or click the small **+** button in any group header to pre-select that component type.

**Component Type**  
Choose one of the four types using the selector buttons at the top of the form. Once a component is saved the type cannot be changed; duplicate it and delete the original if you need a different type.

**Name / Description** *(required)*  
A descriptive label, e.g. *Titegroup*, *CCI 500 Small Pistol*, *124gr FMJ RN*, *Mixed once-fired 9mm*.

**Price** *(required)*  
The price you paid for the component. For powders this is the price per pound (Imperial) or per kilogram (Metric). For all other types it is the total price for the quantity below.

**Quantity / Weight** *(required)*  
- *Powder*: the weight the price covers (lbs or kg). A 1 lb jug entered at $28.99/1 lb stores as $28.99/lb; a 4 lb jug entered at $89.99/4 lb also resolves to the correct per-lb rate when used in a load.
- *Primer, Bullet, Brass*: the number of units the price covers (e.g. 100 primers for $15.99).

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
- **Price**: the raw price as entered (e.g. *$89.99 / 4 lb*)
- **Per unit**: the derived cost per lb/kg or per single primer/bullet/case (e.g. *$22.50/lb*)
- Brass **Reloads** count (brass cards only)
- Bullet **caliber**, **diameter** and **weight** (bullets only)
- Notes (if any)

![Screenshot: Inventory card showing price and per-unit fields](./images/inventory-card.png)

### 3.2 Managing Components

Each component card has three action buttons:

| Button | Action |
|--------|--------|
| ✏️ Edit | Opens the component in the form panel for editing. The type selector is disabled; type cannot be changed after creation. |
| ⧉ Duplicate | Creates a copy with *(copy)* appended to the name, useful when a component comes in multiple package sizes. |
| 🗑 Delete | Permanently removes the component from the catalog. Loads that were linked to it retain their last-known values but lose the live link. |

![Screenshot: Inventory card action buttons](./images/inventory-card-actions.png)

### 3.3 Linking Inventory to Loads

When editing or creating a reload in the **Editor** tab, each component section (Powder, Primers, Bullets, Brass) has a **Select from inventory** dropdown above the manual input fields. Choosing an item from that dropdown fills all the related fields automatically and marks the component with a **linked badge**.

![Screenshot: Load editor with inventory dropdown and linked badge](./images/inventory-link-badge.png)

**What the linked badge means:**  
A small inventory icon appears next to the component name to indicate the values are driven by the inventory. If you manually edit any field in that section the link is broken automatically and the badge disappears; the load then stores its own independent copy of those values.

You can also click the **×** on the badge to unlink intentionally without editing any field.

**Auto-update behaviour:**  
When you edit a component in My Components (e.g. update a powder price after buying a new jug), every reload that is still linked to that component has its cost recalculated immediately. No manual re-entry is needed.

> **Tracking cost changes across component batches.** If you want to preserve an accurate cost history when a new batch of a component arrives at a different price, add the new batch as a separate inventory item rather than editing the existing one. Then duplicate the load in My Ammo and link the copy to the new batch. Journal entries logged against the original load retain its original component costs, while the duplicate carries the new batch price going forward. Both loads appear in Cost Analysis, giving you an accurate weighted picture of what you have actually spent across batches.

**Inventory badge in My Ammo:**  
In the expanded card view under My Ammo, any component that originates from the inventory shows a small inventory icon next to its name, so you can tell at a glance which values are managed centrally.

![Screenshot: Expanded ammo card showing inventory link badges on components](./images/inventory-badge-card.png)

---

## 4. Reloading Journal

The **Journal** tab is the heart of the application for session-based reloaders. Every time you sit down at the press, add an entry with the load you reloaded, the quantity you produced, and the date. Each entry automatically receives a unique, incrementing **lot number** that you can print on an ammo box label. Over time, your journal becomes a complete, searchable production history of every batch you have ever pressed.

<!-- TODO: Update screenshot — journal overview showing Log Entry button, Remaining Rounds column, and the summary panel -->
![Screenshot: Journal tab showing the session list, add row at the bottom, and the summary panel](./images/journal-overview.png)


### 4.1 Logging a Session

Click **Log Entry** at the top right of the entries card to open the session dialog. Fill in:

| Field | Description |
|-------|-------------|
| **Date** | The date of the session (defaults to today). Required. |
| **Load** | Select from your Active or In Development reload entries. Required. |
| **Qty** | Number of rounds produced. Required. |
| **Charge override** | Optional. Enter a value only if this batch was loaded at a different charge than the recipe default. Overridden values are highlighted in the journal row. |
| **COAL override** | Optional. Per-lot cartridge overall length if it differs from the recipe. |
| **Brass override** | Optional. Specify which brass was used if it differs from the recipe default. |
| **Notes** | Optional; use for a powder lot number, seating depth, or any other session reference. |

The next available lot number is shown at the top of the dialog and is assigned automatically when you save. Click **Save Entry** to log the session. The new entry appears at the top of the list and the lot counter advances.

<!-- TODO: Update screenshot of journal add/edit dialog showing the charge, COAL, and brass override fields -->

**Starting lot number**  
At the top of the summary panel (visible when the summary is expanded) you can set the **Starting lot #**. The next lot number is always the first unused number at or above this value. If you raise it above your current highest lot (for example to start a new series at 100), the next entry will begin from that number. If the requested number is already in use, the application finds the next free slot automatically, so duplicate lot numbers can never occur. Use this field to align with a lot series you were already tracking elsewhere or to create a meaningful break in your numbering when switching between projects or calibres.

### 4.2 Managing Journal Entries

Each entry row has action buttons on the right:

| Button | Action |
|--------|--------|
| ☆ Star | Marks the entry as a reference lot (starred entries show a coloured accent) |
| ✏️ Edit | Opens the entry for editing; the lot number is fixed and cannot be changed |
| ⧉ Duplicate | Creates a copy of the entry with the next available lot number (useful for pressing additional batches of the same load at the same settings) |
| 🖨 Print | Opens the label print dialog pre-filled with the lot number and quantity |
| 📦 Archive | Moves the entry to the archive so it no longer appears in the main list. Archived entries are preserved in full and can be restored at any time. |
| 🗑 Delete | Permanently removes the entry |

**Remaining Rounds column**
The **Remaining** column shows how many rounds from each lot have not yet been fired. It is calculated automatically from your Range Log: every time you log rounds against a lot in a range session, the remaining count decreases. When all rounds in a lot have been accounted for in the Range Log, the lot is marked **Depleted**. This live link between the journal and the range means you always know exactly how much of each lot is left on the shelf without maintaining a separate inventory.

**Archiving and restoring entries**
Click the **📦 Archive** button to move a lot out of the active list without deleting it. Archived entries remain part of your history and are still counted in the Journal statistics panel. To see archived entries, click the **"N archived"** link that appears in the journal header when any entries are archived. To restore an entry to the active list, expand the archived view and click the **Restore** button on the relevant row.

<!-- TODO: Add screenshot of journal entry row showing all action buttons (star, edit, duplicate, print, archive, delete) and the Remaining Rounds column -->

Use the **Search** box at the top of the page to filter entries by lot number, date, load name, caliber, brass name, or notes.

### 4.3 Printing a Lot Label

Click the **Print** button on any journal entry to open the label print dialog. The **LOT** and **QTY** fields are pre-filled from the entry; just confirm and print.

The label dialog lets you review and adjust every field on the label before committing:

- **Load name and caliber**, taken from the linked reload entry
- **LOT**, pre-filled with the entry's lot number
- **QTY**, pre-filled with the number of rounds logged
- All other label fields (powder, primer, bullet, brass, COAL, notes) are pulled from the load definition

You can also open the print dialog from any ammo card in **My Ammo** using the print button on that card, without a pre-filled lot number.

![Screenshot: print label dialog showing LOT and QTY pre-filled from a journal entry.](./images/label-print.png)

### 4.4 Journal Statistics

The **summary panel** on the right of the Journal tab shows:

- **Rounds by Load**: total rounds produced for each reload, sorted by volume
- **Total cost per load**: rounds multiplied by the cost per round for that load
- **Grand total rounds** and **grand total cost** across all entries

These figures accumulate automatically as you add entries. The cost per round used in the calculation is always the current cost from your load definition.

---

## 5. Range Log

The **Range Log** tab is where you record what happens after the ammo leaves the bench. Every time you go to the range, add a session: choose the firearm, enter the date and the distance, then list each lot you fired along with how many rounds and any per-lot observations. The Range Log supports all three ammo sources: lots from the Reloading Journal, manually entered reload batches, and factory ammunition. Over time it becomes a searchable field record that connects every range trip to the specific lots and load recipes that produced the ammo.

<!-- TODO: Add screenshot of the Range Log tab showing a list of range sessions with expanded lot details -->
![Screenshot: Range Log tab showing session list with expanded session](./images/range-log-overview.png)

### 5.1 Logging a Range Session

Click **+ Log Session** at the top of the Range Log to open the add form. Fill in:

| Field | Description |
|-------|-------------|
| **Date** | The date of the range trip (defaults to today). Required. |
| **Firearm** | Name of the firearm used (e.g. *Glock 17*, *AR-15 18" SPR*). Type a new name or select a previously used firearm. Required. |
| **Distance** | The distance at which you shot, with a unit selector (yd / m) |
| **Temperature / Wind** | Optional session conditions |
| **Notes** | Optional free-text field for range conditions, impressions, or any other reference |

After filling in the session header, add one or more **lots** to the session using the **Lots fired** section. Each lot row has a mode toggle with three options:

| Mode | When to use |
|------|-------------|
| **From Journal** | The ammo was logged at the press in the Reloading Journal. Select the lot from the dropdown; charge and COAL fill in automatically. The rounds field pre-fills with the remaining (unfired) count from the journal, and the form will not let you log more rounds than are available. Depleted lots are hidden from the dropdown so you can never over-log a lot. |
| **Reload** | A reload batch that was not logged in the Journal. Enter an optional lot number, select the reload recipe, and override charge or COAL if needed. |
| **Factory** | Factory ammunition. Select from your defined factory entries. No charge or COAL fields are shown. |

<!-- TODO: Add screenshot of the Range Log add form showing the From Journal / Reload / Factory mode toggle buttons on a lot row -->
![Screenshot: Range Log add/edit form showing the lot mode toggle (From Journal / Reload / Factory) and lot entry fields](./images/range-log-add-form.png)

For every lot, regardless of mode, you can also record per-lot performance data:

| Field | Description |
|-------|-------------|
| **Rounds** | Number of rounds fired from that lot |
| **Avg fps** | Average muzzle velocity |
| **ES** | Extreme spread (fps) |
| **SD** | Standard deviation (fps) |
| **Group** | Group size with unit (in / cm / MOA / MIL) |
| **Shots** | Number of shots in the group |
| **Notes** | Per-lot observations |

Use the **⧉** duplicate button on any lot row to quickly copy it when firing multiple similar lots in the same outing. At least one lot must have an ammo selection before the session can be saved.

Click **Save Session** when done. You can add as many lots as you fired during the outing.

**Velocity unit**
The **fps / m/s** toggle in the page header switches the velocity display unit for all sessions and the add/edit form at once. The preference is saved so the Range Log always opens in your chosen unit. Velocity values are always stored internally in fps; toggling the display never changes your recorded numbers.

<!-- TODO: Add screenshot of the Range Log page header showing the fps/m/s velocity unit toggle button -->

### 5.2 Managing Range Sessions

Sessions are displayed as rows in a list, most recent first. Click any row to **expand** it and see the full per-lot breakdown for that session.

<!-- TODO: Add screenshot of an expanded session row showing lot detail rows beneath it -->
![Screenshot: Range Log — expanded session row showing individual lot entries](./images/range-log-expanded.png)

Each session row has action buttons on the right:

| Button | Action |
|--------|--------|
| ★ Star | Marks the session as a reference (see [Starring Sessions](#53-starring-sessions)) |
| ✏️ Edit | Opens the session for editing — you can change the header fields or add and remove lot entries |
| ⧉ Duplicate | Creates a copy of the session (useful for recurring outings at the same location with the same firearm) |
| 🖨 Print | Opens the print dialog for the session's data sheet |
| 🗑 Delete | Permanently removes the session and all its lot entries |

Use the **Search** box at the top of the page to filter sessions by firearm, date, lot number, or load name.

### 5.3 Starring Sessions

Click the **star button** (☆ / ★) on any session row to mark it as a reference session. Starred sessions display a coloured left-border accent so they stand out in the list.

Starring a range session also **automatically stars all journal lots** that were linked to that session via **From Journal** mode. This means the lots that produced your best results are instantly flagged in the Journal as well, so you can find them quickly at the bench when deciding what to reload next.

Click the **starred filter button** (☆) in the page header to toggle the list to show only starred sessions. This is useful when you are at the bench deciding which loads to press again and want to pull up only the sessions that produced your best results.

<!-- TODO: Add screenshot showing starred sessions in the list with the star filter active, and the corresponding starred lots visible in the Journal -->
![Screenshot: Range Log with starred sessions highlighted and the starred filter button active](./images/range-log-starred.png)

### 5.4 Range Log Statistics

The **statistics panel** at the top of the Range Log gives you an at-a-glance performance summary across all your recorded sessions. Click the bar to expand it.

<!-- TODO: Add screenshot of the Range Log statistics panel expanded, showing KPI tiles and Rounds by Load cards -->
![Screenshot: Range Log statistics panel expanded, showing KPI tiles and Rounds by Load cards with fps, SD, and group data](./images/range-log-stats.png)

The panel has two sections:

**Key Performance Indicators** — a row of summary tiles across the top:

| Tile | Meaning |
|------|---------|
| **Total Sessions** | Number of range sessions logged |
| **Total Rounds** | Total rounds fired across all sessions |
| **Firearms** | Number of distinct firearms used |
| **Avg FPS** | Average muzzle velocity across all lots with velocity data |
| **Best Group** | Smallest group size recorded, normalised to inches |
| **Avg Group** | Average group size across all lots with group data, normalised to inches |

**Rounds by Load** — a scrollable row of cards, one per distinct load or factory entry. Each card shows:

- Load name and total rounds fired
- Average fps and average SD (if velocity data was recorded for that load)
- Average group size and best group size (if group data was recorded for that load)

The cards let you compare performance across different loads at a glance — useful during load development to see which recipes are consistently grouping best or producing the most consistent velocity.

---

## 6. Cost Analysis (Break-Even)

The **Cost Analysis** tab shows how the cumulative cost of reloading (including your one-time equipment investment) compares to buying factory ammo over time, and at what point reloading becomes cheaper overall.

![Screenshot: Cost Analysis tab: full view](images/cost-analysis.png)

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
- **Reload line**: cumulative spend including the equipment investment upfront, declining in slope as per-round costs are cheaper than factory.
- **Factory line**: cumulative spend at factory prices with no upfront cost.

The point where the lines cross is the **break-even point**, marked on the chart. After that point, every round you reload puts money back in your pocket.

In reload **Rounds** mode, the chart also shows your **current position** on the timeline based on the total effective reload rounds, making it easier to see how far along you are toward break-even.

If the reload average is higher than the factory average (reloading is more expensive per round), the lines never cross and a warning is shown.

![Screenshot: Break-even chart showing the intersection point](./images/analysis.png)

---

## 7. Cost Comparison

The **Cost Comparison** tab lets you select any combination of reload and factory entries and compare their costs side by side.

![Screenshot: Cost Comparison tab with entries selected](./images/comparison-selection.png)

**Selecting entries**  
Click any entry in the selection list to toggle it on or off. Selected entries are highlighted: green for reloads, amber for factory ammo. You can select multiple reloads and multiple factory entries simultaneously.

**Reading the comparison**  
Once entries are selected, the view shows:

- A **bar chart** of cost per round for every selected entry.
- A **cost table** with totals for 50, 100, and 1,000 rounds for each entry.
- A **Difference** section (visible when at least one reload and one factory entry are selected) showing how much cheaper your reload is per round, per 50, per 100, and per 1,000 rounds.

Use the **Search** box above the selection list to filter by name, caliber, type, or component.

![Screenshot: Cost Comparison: bar chart and difference table](./images/cost-comparison.png)
![Screenshot: Cost Comparison: difference table](./images/cost-break-down.png)

---

## 8. Guided Tour

Click **Tour** in the top navigation bar to start the built-in walkthrough at any time.

The guided tour highlights the major parts of the application and explains:

- how to add and manage ammo entries
- how to use the inventory and linked components
- how to log pressing sessions in the Journal and assign lot numbers
- how to record range sessions in the Range Log and track lot performance in the field
- how to compare reloads and factory ammo
- how to use the break-even analysis
- how to switch between simple selection and reload round-count analysis
- which values to check in the analysis stats cards

The tour can be dismissed at any time and is designed to help first-time users get oriented quickly.

---

## 9. Settings & About

The top-right area of the header includes both an **About** button and a **Settings** button.

**Settings**
- **Follow Time Of Day**: automatically uses the light theme during the day and dark theme in the evening
- **Currency Symbol**: changes the currency shown across cards, tables, and analysis views
- **Cost Per Round Decimals**: controls how many decimal places are shown for per-round costs

![Screenshot: Settings showing the configuration of the application](./images/app-settings.png)

The application still defaults to the **dark theme** on first launch. If you enable **Follow Time Of Day**, the app will switch themes automatically based on the time of day. You can still use the theme toggle in the header to return immediately to manual light/dark mode.

---

## 10. Import & Export

Your entire library (ammo entries, tax defaults, equipment costs, load selections, component inventory, and your full reloading journal) can be saved to a single JSON file and restored later or shared with another computer.

**Exporting**  
Click **Export** in the top navigation bar. A `.json` file will be downloaded to your machine.

**Importing**  
Click **Import** and select a previously exported `.json` file. All data in the file will replace the current library.

> WARNING: Import overwrites your current data. Export first if you want to keep your existing entries.

![Screenshot: Export and Import buttons in the navigation bar](./images/header-tabs.png)

---

## 11. Tips & Notes

- **All data is stored locally.** No account or internet connection is required. Data is saved automatically in the browser/app storage every time you make a change.
- **Brass reuse count matters.** Setting a realistic reuse count (commonly 5–10 reloads per case) significantly lowers your per-round brass cost. A count of 1 treats every case as single-use.
- **State Excise Tax (SET).** Factory ammunition in some US States is subject to a state excise tax in addition to state and local sales tax. The default value is pre-filled for you.
- **Fix Fee (FF).** Some US States have an additional fix fee (normally associated to a background check) on any ammunition purchases. This is a fixed fee applied to the entire purchase and its cost is diluted over all the rounds purchased.
- **Accuracy of results.** All costs are estimates based on the prices you enter. Check current component and ammo prices regularly, as they fluctuate.
- **Use load status to manage your library lifecycle.** Mark new recipes as **Draft** while you are costing them out, move them to **In Development** once you are working them up at the range, promote to **Active** when proven, and **Retire** recipes that have been superseded. Retired loads disappear from default views without losing any journal history.
- **Duplicating entries** is a quick way to model variants: duplicate a load, change the powder charge or bullet weight, and compare side by side in the Cost Comparison tab.
- **Equipment costs** only need to be entered once. They persist between sessions and are included in export files.
- **Use the inventory for shared components.** If you load multiple calibers with the same powder or primer, define it once in My Components and link it to all relevant loads. A single price update flows through everywhere.
- **Inventory lists are alphabetical.** Components inside each inventory group are ordered by name to make powders, primers, bullets, and brass easier to scan.
- **Powder quantity field.** When entering a powder in the inventory, set the quantity to match how the powder is sold (1 lb, 4 lb, 8 lb, etc.). The app calculates the per-lb rate automatically and uses it when costing a load.
- **Unlinking a component.** Manually editing any field in a linked component section (name, price, quantity) automatically breaks the inventory link. The load keeps the values you typed but is no longer updated when the inventory item changes. Use the **×** on the badge to unlink without changing any values.
- **Deleting an inventory item** does not delete any loads that used it. Those loads retain the component values they had at the time the link was broken.
- **Journal lot numbers never repeat.** Deleting an entry does not reuse its lot number. The next new entry starts from the **Starting lot #** you configured in the Journal header, then increments past any already-used numbers until it finds the next free slot. This means you can lower the starting lot number to fill in historical batches without creating duplicates, and existing entries are never displaced.
- **Journal baseline for existing reloaders.** If you were reloading before you started using the journal, enter your historical round count as the manual baseline in Cost Analysis Rounds mode. The journal will add to it going forward, keeping your break-even progress accurate.
- **Label printing from the journal.** The quickest way to print a box label is directly from the Journal; the lot number and quantity are already filled in. You only need to confirm and print.
- **The bench-to-range loop.** Use the Journal to record what you pressed, then use the Range Log to record how each lot performed at the range. The two tabs together give you a complete picture: production history in the Journal, field performance in the Range Log.
- **Multiple lots in one range session.** A single range session can include several lots — for example if you ran three different powder charges side by side. Add one lot entry per charge weight so each gets its own round count and notes.
- **Range Log notes for load development.** Use the per-lot notes field in the Range Log to record group sizes, point of impact shifts, felt recoil, or function issues. Over time this builds a development log you can cross-reference when adjusting a recipe.
- **Star your reference loads.** Once you find a load that functions and groups well, star that range session. The starred filter gives you a quick shortlist when you are deciding what to press next. Starring a session also stars the linked journal lots automatically, so both records are flagged together.
- **Remaining Rounds keeps your shelf count accurate.** Log rounds against journal lots in the Range Log using **From Journal** mode and the Remaining column updates automatically. Lots that reach zero are marked Depleted and hidden from the From Journal dropdown so you cannot accidentally log against an empty lot.
- **Archive completed lots to keep the journal tidy.** Once a lot is fully fired and you no longer need it in the active list, archive it. The lot stays in your history and still contributes to statistics; it just does not appear in the main journal table. Restore it at any time if you need to reference or reprint the label.
- **Velocity unit preference is global.** The fps / m/s toggle in the Range Log header applies to every session in the list and carries over into the add and edit forms. Switch once; it stays set until you toggle it again.
- **Range Log data is included in export files.** When you export your library, your full range log history is included. Import it on another machine and your field records move with you.
- **Charge workup and the journal are connected.** When you log entries from the Charge Workup panel, they appear in the Journal as normal lot entries. When you later log those lots in the Range Log (select them **From Journal**), the velocity and group data flows back into the workup chart automatically — no extra steps needed.
- **Link range sessions to workup lots using "From Journal" mode.** When adding a lot in the Range Log, select **From Journal** and pick the lot number that the Charge Workup panel created. This is what connects your range data to the workup chart; if you use the Reload or manual mode instead, the lot number may not match and the data will not appear on the chart.
- **The workup chart needs at least two data points.** The velocity and group chart only appears once two or more distinct charges have been fired and recorded in the Range Log. Until then, the table gives you the data in row form.
- **Multiple lots at the same charge show as separate diamonds.** If you pressed and fired two batches at the same charge weight (e.g. two lots of 20 rounds), the chart shows a diamond for each lot alongside the average line, so you can see how consistent your results are across batches.
- **Ad-hoc charges let you test outside the ladder.** Use the *Add charge* field in the workup panel to add a step that falls outside your configured min–max range — for example to test a charge that looks promising based on early data. The entry is held as a pending row in the table until you click Log Entries, so you can still choose to exclude it before logging.
- **Promote unstars the previous winning charge.** If you promote a charge, then later start a new development cycle and promote a different charge, the application automatically removes the star from journal entries for the old charge and stars the new one. Your starred filter in the Journal always reflects the current best load.
- **Workup history is preserved after promotion.** Promoting a charge does not delete the ladder or its data. The full development history remains visible in the workup panel (and on the printed data sheet) even after the load is Active.
