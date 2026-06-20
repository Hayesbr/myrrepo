# Diversifi Knowledge Center — Updated Sections

This doc walks the Knowledge Center in order, article by article.

- **✅ No change needed** — the article is accurate as-is; leave it alone.
- **✏️ Updated** — copy the text **inside the gray code box** (not the ``` fences) and paste it into the matching GitBook page. The note above each box explains what changed and is **not** meant to be pasted.

Sources used: new Knowledge Center export (6/19/26), Monday notetaker call summaries, Google Drive, Monday, and local source files.

---

## Getting Started

**✏️ Updated** — Step 3 (Connect Your WMS): supported WMS list corrected to **Extensiv, ShipHero, ShipStation** (was "Extensiv, ShipStation, Vox, and more"; "Vox" is a reseller/invoice source, not a WMS), and nav path updated to **Integrations (top-level left nav)** (was "Settings → Integrations"). Everything else unchanged.

```markdown
# Getting Started

Welcome to Diversifi. This guide will walk you through everything you need to get up and running on the platform. Most 3PLs are fully set up within their first week.

## What You'll Need Before You Begin

Before logging in for the first time, make sure you have the following ready:

- Your carrier rate sheets — you'll need these to load your cost rates into the platform
- Your WMS login credentials — to connect your warehouse management system
- Your team's email addresses — to invite the people who will be using the platform

## Step 1 — Set Up Your Account

When you receive your invite email from Diversifi, click the link to create your account. You'll be asked to set your name, password, and timezone.

Once you're in, go to Settings → Account to complete your company profile including your company name and address.

## Step 2 — Invite Your Team

Go to Settings → Users and invite the team members who will be using the platform. Diversifi has three user roles:

- **Owner** — full access including user management, warehouse setup, integrations, and billing settings
- **Manager** — full access to all platform features
- **Regular** — can run bids, manage billing records, and view reports. Cannot manage users or integrations.

At least one person on your team should be set to Owner. We recommend having two Owners so there is always a backup administrator.

## Step 3 — Connect Your WMS

Go to Integrations in the left navigation and connect your warehouse management system. Diversifi supports Extensiv, ShipHero, and ShipStation.

Connecting your WMS allows Diversifi to automatically pull in your shipment data, order data, and customer information — which is the foundation for both BidBoost and Billing.

Note: If you are setting up carrier integrations as well, do not use both email invoice ingest and a carrier integration for the same carrier at the same time. Use one or the other to avoid duplicate invoice records.

## Step 4 — Load Your Carrier Cost Rates

Go to Carriers → Cost Rates and enter your negotiated rates for each carrier. This is the foundation of BidBoost — the platform uses your cost rates to calculate proposed rates for prospects.

You'll enter rates using the spreadsheet-style grid. For each carrier and service you'll need:

- Weight breaks and corresponding rates per zone
- Effective date range for the rate set
- A nickname to identify the rate set (useful if you have multiple rate sets for the same carrier)

Once your rates are in you can assign them to specific warehouses so the right rates are always used in the right bid.

For full details on loading and managing cost rates, see Cost Rates in the BidBoost section.

## Step 5 — Run Your First Bid

Go to Sales → Bid Center and click New Bid. You'll be guided through:

1. Selecting or adding a prospect
2. Choosing your bid type — PLD (shipment file), SKU, or No Data
3. Selecting your carriers and services
4. Applying your markup
5. Exporting your rate card

Your first bid should take about 10 minutes once your cost rates are loaded.

## Step 6 — Set Up Billing

Go to Billing and create your first billing cycle. Add your customers to a period, ingest your carrier invoices, apply your billing rules, and generate your first bill.

If you are new to Diversifi billing, start by connecting your carrier integrations or setting up email invoice ingest so invoices flow in automatically.

## Your First 30 Days — Checklist

Use this checklist to make sure you have everything set up correctly in your first month:

- Account profile complete
- Team invited with correct roles assigned
- WMS connected and syncing
- Carrier cost rates loaded for all active carriers
- Cost rates assigned to warehouses
- First bid created and exported
- Carrier invoices connected via integration or email ingest
- First billing cycle created
- Billing rules configured in Owlfred
- First bill generated and reviewed

## Need Help?

If you get stuck at any point use the search bar at the top of this page — our AI will find the answer from our documentation instantly.

You can also reach your Diversifi account manager directly at support@diversifi.ai
```

---

# BidBoost

Articles below are in Knowledge Center order.

## BidBoost (Overview)

**✅ No change needed.**

## Running a Bid

**✅ No change needed.**

## Cost Rates

**✅ No change needed.** (Includes the newer Warehouse-Level Additional Fees / Commission content — reviewed and accurate.)

## Markups & Surcharges

**✏️ Updated** — Rewrote the **Residential Surcharge** section to remove internal developer notes and database field names (`carrier_services.delivery_type`, `carrier_services.transport_mode`) and "we will add…" engineering phrasing; the real behavior is preserved. No other content changes.

```markdown
# Markups & Surcharges

This article explains everything you need to know about how markups work and how to use the markups screen effectively.

## How Markups Work

The markups screen is one of the most important parts of BidBoost. It is where you set your margin, compare carriers, and make sure you are pricing competitively before sending a rate card to a prospect.

A markup is the percentage or dollar amount you add on top of your cost rates to produce the rate you charge the prospect. For example, if your cost rate for a 5 lb FedEx Ground shipment to zone 4 is $8.50 and you apply a 20% markup, the prospect sees $10.20.

Your actual cost rates are never visible to the prospect. They only ever see the rate after your markup has been applied.

**The markup formula**

For every weight and zone combination, Diversifi calculates the proposed rate using the following logic:

1. Start with the base rate from your cost rates.
2. Add any applicable surcharges — fuel, residential, additional handling.
3. Apply your markup percentage to the total.
4. Compare against your minimum dollar markup if one is set.
5. Whichever is greater — the markup percentage result or the minimum dollar amount — becomes the proposed rate.

## The Speed Tier View

Your shipments are organized into speed tier groups on the markups screen. Each group shows you where the packages from the prospect's file went and what the average cost per package is for each carrier and service in that group.

Speed tier groups:

- **Next Day** — shipments where a next day service wins
- **2–3 Day** — shipments where a 2 to 3 day service wins
- **4–5+ Day** — shipments where a slower ground service wins
- **Unrated** — shipments where a speed tier could not be determined. Shown at the bottom for visibility but excluded from rated results.

Every package in the file is accounted for. If you submitted 1,000 packages you will see the exact count in each bucket.

## The Winning Carrier Badge

Each speed tier group shows a badge identifying the winning carrier and service — the one with the lowest average cost per package after all markups are applied. This badge updates in real time as you adjust your markups. As you increase the markup on one carrier, another carrier may become cheaper and take the winning badge. This is intentional — it shows you the exact point where your pricing decisions affect which carrier wins the business.

Use the winning badge to:

- Confirm your preferred carrier is winning before you export
- Identify whether your markup on one carrier is too high and pushing shipments to a competitor
- Make sure your pricing strategy produces the outcome you expect for the prospect

## Adjusting Markups

**Individual carrier and service markups**

Use the slider next to each carrier and service to set the markup for that specific service. As you move the slider the average cost per package updates immediately so you can see the impact in real time.

The slider takes precedence over any carrier-wide markup you have set. If you set a carrier-wide markup of 15% and then move an individual slider to 20%, that service will use 20%.

**Carrier-wide markup**

Enter a percentage in the carrier-wide markup input field to apply the same markup across all services for that carrier at once. The carrier-wide markup field updates to reflect the weighted average across all services if you subsequently adjust individual sliders.

**Quick Actions**

For blanket markups across all carriers or all services at once, use the Quick Actions panel. Options include:

- Apply a percentage markup to all carriers
- Apply a percentage markup to all services within a speed tier
- Apply AI recommendations — see the AI Recommendations section below

Quick Actions are useful when you want to start with a baseline markup across everything and then fine-tune individual carriers or services.

## Pricing Limits

Your account Owner can configure pricing limits that set a floor on how low your markups can go. Pricing limits protect your margin by preventing a sales rep from accidentally pricing below cost or below your minimum acceptable margin.

**How pricing limits work**

If you enter a markup that would result in a rate below the pricing limit you will see a warning identifying which services are affected. You can review the warning and either adjust your markup or confirm you want to proceed.

Pricing limits can be set as:

- A minimum markup percentage
- A minimum dollar amount per package

If both are set the platform uses whichever produces the higher rate.

## Fuel Surcharge

The fuel surcharge is a percentage added on top of the base rate to account for carrier fuel costs. Toggle fuel surcharge on to include it in the prospect's proposed rates.

The fuel surcharge percentage is configured in your carrier configuration settings. When toggled on it applies to all carriers selected in the bid that have a fuel surcharge configured.

**Important:** Fuel surcharge applies to the base rate before your markup is calculated. The full formula is:

(Base rate + Fuel surcharge) × Markup percentage = Proposed rate

## Residential Surcharge

The residential surcharge is an additional fee carriers charge for deliveries to residential addresses. Toggle residential surcharge on if the prospect's shipments include residential deliveries and you want to include this fee in the proposed rates.

Not all carriers charge the same residential surcharge. The amount is configured per rate set in your carrier configuration settings.

When the residential surcharge toggle is on, Diversifi adds the surcharge to all applicable rates. Services that are already priced as residential delivery are excluded, because the residential cost is already built into their base rates.

Carriers charge different residential surcharges for Ground and Air services, so you enter a separate Ground and Air residential rate for each rate set in the carrier configuration screen. Diversifi automatically applies the correct rate based on whether each service is Ground or Air.

## Additional Handling

Additional handling fees apply to packages that exceed certain size or weight thresholds. Toggle additional handling on if the prospect's file includes oversized packages and you want to include this fee in the proposed rates.

## Minimum Dollar Markup

In addition to a percentage markup you can set a minimum dollar amount per package. This ensures that even on very low cost shipments you always make at least a minimum dollar margin.

For example, if your minimum dollar markup is $2.00 and your percentage markup on a $5.00 shipment would only produce $1.00 of margin, the platform will use $2.00 instead.

The minimum dollar markup is configured by your account Owner in the pricing limits settings.

## AI Recommendations

The AI recommendation feature suggests a markup level for each carrier and service based on market data. The recommendation is calculated as 5% above your cost or 5% below market rates — whichever produces the higher proposed rate.

To apply AI recommendations, click Quick Actions and select Apply AI Recommendations. You can apply them to all carriers at once or review and apply them individually.

AI recommendations are a starting point — review them before exporting and adjust based on your knowledge of the prospect and the competitive situation.

## Restore to Default

Click Restore to Default to reset all markups back to their default state. If a minimum pricing limit is configured the default will be set to that minimum rather than 0%. If no pricing limit is set the default is 0%.

## Common Questions

**Why is a carrier winning that I didn't expect?** Check the average cost per package for each carrier in that speed tier. The winning carrier is always the one with the lowest average cost per package after all markups are applied. If a carrier you don't want to win is winning, try increasing its markup until your preferred carrier takes the winning badge.

**Why is my carrier-wide markup not updating after I move a slider?** When you move an individual slider it takes precedence for that service. The carrier-wide markup field updates to show the weighted average across all services for that carrier, reflecting the mix of your carrier-wide markup and any individual slider adjustments.

**Can I lock a carrier out of winning?** Not directly — but you can increase the markup on a carrier high enough that it never wins any speed tier group. The winning badge will move to the next cheapest carrier.

**What does it mean when a service shows in the Unrated group?** Unrated shipments are ones where Diversifi could not determine a speed tier from the data in the prospect's file. This can happen when carrier or zone data is missing for a particular shipment. Unrated shipments are shown for visibility but do not affect the rated results above them.

**Why do my KPI totals not add up to my full file?** Check the Unrated count at the bottom of the screen. Unrated shipments are excluded from the KPI calculations since they do not have a confirmed rate. The rated shipment count plus the unrated count should equal your total file size.
```

## Carrier Configuration

**✅ No change needed.**

## Exports

**✏️ Updated** — Fixed the "RASIF" typo → **RAS**. Removed internal database references (`rates`/`fuel`/`carrier_configs`/`markups` tables, the raw `SUM(...)` formula, and the `speed_tier`/`carrier_services` column references) and replaced them with the plain-language formula used elsewhere. Replaced the "in-platform cell debugger" aside with a reference to the Validation View. Rewrote the **Validation View** section from an internal voice into customer-facing language.

**⚠️ Confirm before publishing:** Is the **Validation View** a customer-facing feature? If it's internal-only, delete that section from the box below before pasting.

```markdown
# Exports

BidBoost produces three export types. Each serves a different use case and audience. All exports are Excel (.xlsx) files delivered directly to the prospect or brand.

## Bid Types and Export Availability

The bid type selected at the start of the bid determines what exports are available and which surcharge toggles apply.

**PLD / Shipment File** — Requires a shipment file upload. All three export types are available. This is the only bid type that supports the DAS (Delivery Area Surcharge) toggle — DAS does not appear on SKU or No Data bids. Fuel, residential, and other surcharge toggles are all available.

**SKU** — Requires box dimensions and weights entered per SKU. No shipment file is needed. Net Rates and Blended Rate Card exports are available — Shipment File is not, since there is no historical shipment data to re-rate. The DAS toggle is not available on SKU bids. All other surcharge toggles apply. The Net Rates export follows the SKU-specific format: one tab per rate set + carrier + service, with separate line items per box per rate set.

**No Data** — No file upload or SKU dimensions required. Rates are calculated against market rate benchmarks using a default of 7 lb Zone 4, which the user can override. Net Rates and Blended Rate Card exports are available — Shipment File is not. The DAS toggle is not available. All other surcharge toggles apply. Because there is no shipment data, rates reflect what the 3PL would offer at the selected weight and zone rather than a re-rate of actual shipments.

| Bid type | Net Rates | Blended Rate Card | Shipment File |
|----------|:---------:|:-----------------:|:-------------:|
| PLD / Shipment File | ✓ | ✓ | ✓ |
| SKU | ✓ | ✓ | — |
| No Data | ✓ | ✓ | — |

## Surcharges

Surcharges are additional fees applied on top of base carrier rates. In BidBoost, surcharges are toggled on or off during bid creation and are applied before the markup calculation. The surcharges available depend on the bid type selected — some surcharges require actual shipment destination data and are only available on PLD bids where that data exists.

Surcharges shown as — are not available for that bid type and the toggle will be disabled in the platform.

| Surcharge | PLD / Shipment File | SKU | No Data |
|-----------|:---:|:---:|:---:|
| Fuel | ✓ | ✓ | ✓ |
| Residential | ✓ | ✓ | ✓ |
| Additional Handling / Oversize | ✓ | ✓ | ✓ |
| RAS | ✓ | ✓ | ✓ |
| DAS (Delivery Area Surcharge) | ✓ | — | — |
| EDAS (Extended Delivery Area Surcharge) | ✓ | — | — |

**Fuel** — Applied as a percentage on top of the base rate. Diversifi handles the carrier's weekly fuel surcharge automatically — you enter your negotiated fuel discount percentage in carrier configuration and Diversifi applies it against the carrier's current weekly rate to calculate your effective fuel cost. Toggling fuel on includes it in all three export types where applicable.

**Residential** — Applied when a shipment is delivered to a residential address. On PLD bids this is calculated from the actual destination addresses in the shipment file — only shipments with residential destinations are charged the residential surcharge. On SKU and No Data bids a residential surcharge estimate is applied based on the residential surcharge amount configured in your carrier configuration, since no actual destination addresses are available.

**Additional Handling / Oversize** — Applied to packages that exceed standard size or weight thresholds as defined in your carrier configuration. Toggling this on applies it across all qualifying shipments in the bid.

**RAS (Remote Area Surcharge)** — Applied to shipments destined for specific carrier-defined remote areas. Carriers maintain their own lists of qualifying zip codes which are updated periodically. If none of the shipments in the bid file have destination zip codes that fall within the carrier's RAS list, the surcharge will not appear in the export even if the toggle is on — this is expected behavior, not a bug. Behavior and qualifying zip codes vary by carrier.

**DAS (Delivery Area Surcharge)** — Available on PLD bids only; the toggle is disabled on SKU and No Data bid types. DAS is determined by the destination zip code of each shipment. Carriers maintain published lists of zip codes that qualify for DAS fees, which are updated periodically. On PLD bids DAS is applied per shipment where the destination zip code falls within the carrier's designated DAS zone. Because SKU and No Data bids do not contain actual shipment destination zip codes, DAS cannot be calculated on those bid types.

**EDAS (Extended Delivery Area Surcharge)** — Available on PLD bids only; the toggle is disabled on SKU and No Data bid types. EDAS applies to a broader set of extended delivery area zip codes beyond the standard DAS coverage area. Like DAS, whether EDAS applies to a given shipment is determined entirely by the destination zip code — carriers maintain their own lists of zip codes that qualify for EDAS fees. On PLD bids both DAS and EDAS are evaluated per shipment based on the destination zip code, with each shipment falling into whichever zone the carrier has designated for that zip code.

**How surcharges interact with markup**

Surcharges are included in the rate calculation before markup is applied. The formula is:

(Base rate + applicable surcharges) × markup % vs. minimum amount — whichever is greater

This means markups are applied to the full loaded cost including all surcharges, not to the base rate alone.

## Net Rates

**What it is** — A spreadsheet listing every carrier and service a 3PL can offer, with the full weight and zone rate table for each. Rates shown are cost plus markup only — the brand's actual price to use the 3PL for each carrier and service. No underlying cost data is exposed. This export goes directly to the brand, generated by the 3PL sales rep during the bid process.

**When to use it** — When the 3PL wants to show a prospect a complete, transparent picture of every available carrier and service option with full rate visibility.

**Input**

- Carriers and services selected during bid creation
- Cost rates loaded for those carriers on that account
- Markup % or $ amount entered on the markup screen
- Any surcharges toggled on: fuel, residential, RAS, additional handling, oversize, or others
- Bid type (PLD, SKU, or No Data) — determines how rates are sourced

**Rate formula (applies to all bid types)**

For every weight and zone cell, Diversifi calculates the proposed rate as:

(Base rate + applicable surcharges) × markup %, compared against your minimum dollar markup — whichever is greater.

Applicable surcharges include residential, additional handling / oversize, and fuel where toggled on. The larger of the markup-percentage result or your minimum dollar amount becomes the final rate shown in the export.

**Output**

- One tab per carrier/service combination
- Each tab is a weight × zone matrix showing cost + markup rates
- File named: ProspectName_NickName_NetRates
- Tab order: Ground services first, then Air services, grouped by carrier. Example: UPS Ground → UPS Air → FedEx Ground → FedEx Air → UniUni Ground, etc.
- Weights: Show ounces first, then pounds. All weights are based on DIM weight. If DIM weight does not apply for a shipment, normal weight is used. DIM weight is never shown as a separate column.
  - DIM weight applies only when a package exceeds 1,728 cubic inches (greater than 1 cubic foot). A package that is exactly 1,728 cubic inches is not subject to DIM weight — actual weight is used.
- Zones: Zone 0 and Zone 9 are removed from the output.

**Multiple rate sets for the same carrier/service** — If a user has two rate sets loaded for the same carrier and service, the export shows one tab for that carrier/service. The rate per cell is calculated as the minimum value between the two rate sets, then the greater of that minimum vs. the markup minimum amount. An internal sheet is included in the export with a legend showing which rate set each cell's rate came from.

If rate sets have different DIM divisors, DIM weight is calculated per rate set, then per service type (Ground vs. Air), since each can carry a different divisor. The rate-set-specific carrier config takes priority over the account-level default config. The default config exists only to pre-populate the rate-set-specific one and is not used in rate calculations when a rate-set config is present.

**Anomaly flagging** — Any cell where the rate is lower than the cell above it (heavier weight, same zone) or lower than the cell to its left (same weight, higher zone) is highlighted. In a normal rate card, rates should increase as weight increases and as zone increases — a decrease in either direction is unexpected and should be reviewed before sending to the prospect.

## SKU Net Rates

**What it is** — A net rates export built from SKU dimensions rather than historical shipment data. Instead of uploading a PLD file, the user inputs box dimensions and weights per SKU. The platform calculates billable weight from those dimensions and runs rates against the 3PL's carrier cost rates and markups.

**When to use it** — When a prospect doesn't have historical shipment data but knows their product dimensions. Common for newer 3PL prospects or brands launching a new product line.

**DIM weight logic** — DIM weight is calculated per rate set, per service type (Ground vs. Air). Each rate set can carry a different DIM divisor for Ground and Air services — the rate-set-specific carrier config is used. The account-level default config is not used when a rate-set config exists. DIM weight applies only when a package exceeds 1,728 cubic inches (greater than 1 cubic foot). A package that is exactly 1,728 cubic inches uses actual weight.

**Output** — The SKU net rates export shows one tab per rate set + carrier + service combination. Each tab contains separate line items per box, giving full visibility into how that specific rate set prices each box configuration.

When a user has multiple rate sets for the same carrier and service — for example two DHL Ground rate sets — each appears as its own tab, distinguished by a 3-digit unique identifier. The identifier is appended directly to the tab name and also printed inside the rate card itself, so customers can always identify which carrier and rate set a tab represents without needing to reference the platform. Example tab names: DHL Ground 001, DHL Ground 002.

Because Excel tab names are capped at 31 characters, longer carrier and service names will be truncated. The identifier and carrier name are always preserved inside the rate card itself to ensure the customer has the full context regardless of how the tab name is displayed.

## Blended Rate Card

**What it is** — A carrier-agnostic rate card showing the single cheapest available rate per weight and zone combination, organized by delivery speed tier. No carrier names appear — the 3PL presents these rates as their own pricing. The prospect sees the best available price for each lane and speed without knowing which carrier delivers it.

**When to use it** — When the 3PL wants to act as the carrier themselves and not expose their carrier mix to the prospect. Common for 3PLs with strong negotiated rates who don't want competitors or prospects to know which carriers they use.

**How it works** — The blended card is built directly from the net rate output — rates are not recalculated from scratch. Services are grouped by speed tier, and for each weight/zone cell the system takes the minimum marked-up rate across all qualifying services. Each tier is cumulative: it includes its own services plus any faster service if that faster service produces a cheaper rate.

**Speed tiers** — The speed tier for each service is set automatically based on the service's delivery speed. ("Deferred" services map to Ground Economy.)

**Input** — Same inputs as Net Rates: PLD, SKU, or No Data bid; carrier cost rates; markup settings. Speed tier is assigned automatically. If multiple rate sets are selected for the same carrier, the lowest rate across all selected rate sets is used for that carrier before the comparison across carriers.

**Output**

- Five tabs, one per speed tier
- Each tab is a weight × zone matrix — one rate per cell
- Rate per cell = lowest marked-up rate across all qualifying services at that tier or faster

| Tab | Services included |
|-----|-------------------|
| Ground Economy | No delivery guarantee. Minimum across all services — faster services included if cheaper. Broadest tier. |
| Ground (1–5 Day) | Ground-speed services + any faster tier if cheaper. Excludes economy/deferred. |
| 3 Day | 3-day services + 2-day and overnight if cheaper. |
| 2 Day | 2-day services + overnight if cheaper. |
| 1 Day | Overnight/express only. Narrowest tier. |

- No carrier names or service names visible anywhere in the export
- File named: ProspectName_NickName_BlendedRates
- If no services qualify for a speed tier, that tab is empty — no zeros, no errors
- Internally, the winning carrier/service per cell is captured and can be inspected using the Validation View — it is never shown in the export.

**Key distinctions**

- vs. Net Rates: Net Rates shows every carrier and service with full visibility. Blended collapses everything to one rate per cell with no carrier visibility.
- vs. Shipment File: Blended is a rate card (weight/zone matrix). Shipment File re-rates actual shipments row by row.

## Shipment File

**What it is** — A re-rated version of the prospect's actual shipment history. Each shipment in the uploaded file is re-rated against the 3PL's carrier rates and markups, showing exactly what that shipment would have cost under the new pricing. Includes a summary of total potential savings.

**When to use it** — When the prospect has historical shipment data and wants a shipment-by-shipment comparison of their current spend vs. what they would pay under the 3PL's rates. The most compelling sales tool for prospects with meaningful volume.

**Input**

- A shipment file (PLD) — required. No Data bid does not apply to this export type.
- Carrier cost rates and markup settings
- Winning carrier and rate per shipment determined by the bid logic

**Output** — Row-level detail for every re-rated shipment: original carrier and service, re-rated carrier and service, original cost, re-rated cost, markup applied, final quoted amount, zone, weight (actual and billable), and any additional services. Includes a Glossary tab with summary metrics — total shipments analyzed, rated vs. unrated count, current total shipping cost, proposed total shipping cost, and potential annual savings. Shipments that could not be rated appear in a separate Unrated Shipments tab with a specific reason per row. File named: ProspectName_NickName_ShipmentFile.

## Validation View

Diversifi includes a Validation View across all bid export types — SKU Net Rates, Shipment File, and Blended Rate Card exports.

The Validation View lets you inspect exactly how an exported rate was calculated. Select any rate cell to see the underlying inputs and calculations that produced the final value:

- Base rate
- Applied surcharges (fuel, residential, additional handling, DAS, etc.)
- Markup configuration and the calculated markup amount
- Billable and dimensional weight
- Final calculated rate
- Carrier, service, rate set, and zone information
- The underlying rate table values used in the calculation

**Why it's useful**

The Validation View makes every bid result fully auditable, so you can answer questions about a rate without guesswork. Common uses:

- Troubleshooting a customer-reported pricing discrepancy
- Verifying carrier rate imports and rate set configurations
- Confirming markup behavior and surcharge application
- Explaining to a customer exactly how a rate was generated
- Investigating differences between expected and actual export values

**Best practice**

If a rate looks off, use the Validation View first. Many questions trace back to rate configuration, surcharge setup, markup rules, billable weight, or rate-set selection — all visible here — so you can often resolve them without contacting support.
```

## Warehouses

**✅ No change needed.**
