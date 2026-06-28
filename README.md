# 📊 Omnichannel E-Commerce Intelligence Suite

An interactive, multi-role enterprise analytics application that converts millions of high-velocity clickstream event logs into actionable corporate strategy. By simulating three separate functional data roles, this project decouples top-line financial performance from granular digital product journey mapping to support cross-functional decision making.

---

## 👥 Cross-Functional Analyst Personas

Rather than delivering a flat, generic dashboard, the solution is explicitly structured to fulfill the tactical requirements of three distinct organizational data professionals:

*   **The Business Analyst (BA):** Acts as a strategic advisor to the CFO, optimizing the *Monetization & Revenue Architecture* to report true, filtered cash-flow volumes.
*   **The Portfolio / Procurement Analyst:** Monitors supply operations, evaluating supplier revenue capture, portfolio density, and platform supply chain risks.
*   **The Product Analyst (PA):** Maps out the storefront's digital footprint, engineering chronological behavior paths to expose user experience (UX) friction and drop-off bottlenecks.

---

## 🧭 The 4 Analytical Domains Implemented

The underlying analytical views are organized systematically into four specialized business disciplines:

### 💰 1. Monetization & Revenue Architecture (CFO View)
Focuses on baseline financial conversion parameters by isolating paid validation sequences (`event_type = purchase`) from raw browser noise.
*   **Gross Merchandise Value (GMV):** $5.57M in generated revenue volume.
*   **Average Order Value (AOV):** $321.89 per completed transaction.
*   **Total Volume:** 17.29K completed and paid orders.

### 🏅 2. Vendor Portfolio & Inventory Dynamics (Procurement View)
Exposes platform brand-level concentration to discover supplier dominance.
*   **Top 5 Brands Bar Chart:** Employs dynamic `Top N` field parameters to automatically strip out low-volume long-tail brands and isolate core market leaders.
*   **Market Share Donut Chart:** Visualizes parent brand wallet capture, revealing extreme platform dependencies on top-tier electronics manufacturers.

### ⏱️ 3. Temporal Pacing & Demand Forecasting (Marketing View)
Maps chronological purchasing spikes to optimize budget scheduling, marketing touchpoints, and processing infrastructure.
*   **Hourly Revenue Velocity Line Chart:** Tracks spending waves distributed across a 24-hour categorical time axis to pinpoint precise operational transaction velocity.

### 🕹️ 4. Customer Journey & Behavioral Funnels (Product/UX View)
Audits the sequential storefront lifecycle flow to isolate drop-off friction points.
*   **Macro User Funnel Chart:** Leverages the `Distinct Count` of user entities across sequential milestones (`View` → `Cart` → `Purchase`).
*   **Brand Friction Matrix Grid:** A matrix cross-referencing brand metrics against user events, overlaid with conditional formatting cell heatmaps to visually isolate conversion leaks.

---

## 📂 Dataset Information

*   **Dataset Name:** eCommerce behavior data from multi-category store (October 2019)
*   **Data Source & Hosting:** Provided courtesy of REES46 Marketing Platform and hosted natively on Kaggle.
*   **Dataset Link:** [Kaggle Dataset Repository](https://www.kaggle.com/datasets/mkechinov/ecommerce-behavior-data-from-multi-category-store)
*   **Data Scope & Profile:** This solution processes a core 3-Million-row slice of clickstream history tracking behavior data from a large multi-category online storefront. 

### 📐 Database Schema Reference
Each row represents a dedicated event representing a many-to-many relationship mapping between individual users and catalog products:

| Property Name | Data Type | Semantics / Description |
| :--- | :--- | :--- |
| `event_time` | DateTime (UTC) | The precise clock timestamp when the event occurred. |
| `event_type` | Text (Categorical) | Interaction flag: `view`, `cart`, `remove_from_cart`, or `purchase`. |
| `product_id` | Integer | Unique database key identifier for the catalog item. |
| `category_id` | BigInt | Unique database key identifier for the category taxonomy. |
| `category_code` | Text (String) | Meaningful meaningful path label for category taxonomy (if present). |
| `brand` | Text (String) | Downcased manufacturer brand identifier string. |
| `price` | Float (Decimal) | Explicit financial value of the targeted product item. |
| `user_id` | Integer | Permanent user account identifier. |
| `user_session` | Text (UUID) | Temporary user session string; changes upon a prolonged pause. |

---

## 🛠️ Dashboard Visual Layout Architecture

The Power BI workspace file is partitioned into two core physical presentation canvases:

### 📑 Page 1: "Executive Business Performance" (BA & Portfolio View)
*   **Top Tier:** 3 Horizontal Executive KPI Cards displaying baseline financial totals.
*   **Mid Pane:** Clustered Bar Charts and clean Donut Charts mapping top-performing suppliers.
*   **Base Pane:** A wide, horizontally-spanning Line Graph rendering hourly revenue curves.
*   **Global Controller:** An active **Brand Slicer** configured as a compact dropdown menu to enable instant interactive cross-filtering across the entire canvas with a single click.

### 📑 Page 2: "Product & Journey Analytics" (Product Analyst View)
*   **Left Canvas Panel:** An explicit Funnel Visual utilizing manual axis sort overrides to bypass default alphabetical groupings, forcing a true chronological funnel framework.
*   **Right Canvas Panel:** A heavy Matrix Grid tracking vendor-specific event counts, utilizing background color gradient heatmaps to point out drop-off anomalies.

---

## 🔬 Core Strategic Insights Discovered

1.  **The "Direct Buy" Funnel Phenomenon:** Product funnel sequences explicitly revealed that finalized `purchase` events regularly bypassed traditional `cart` interaction buffers. This proves that shortcut components (e.g., "Buy Now" checkout configurations) radically transform expected chronological user flows.
2.  **Market Concentration Exposure:** Portfolio share analysis showed a highly disproportionate platform revenue reliance on Apple and Samsung electronics, presenting immediate platform procurement risks and establishing a clear business case for immediate vendor diversification.

---

## 🚀 How to View the Project

1. Download and install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (Available for free on Windows).
2. Download the source file from the [Kaggle Dataset Link](https://www.kaggle.com/datasets/mkechinov/ecommerce-behavior-data-from-multi-category-store).
3. Clone this repository locally to your directory.
4. Open the `.pbix` file inside Power BI Desktop to inspect the live interactions, visual layouts, and semantic modeling configurations.
