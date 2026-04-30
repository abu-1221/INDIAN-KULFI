# Product Requirements Document (PRD): Kulfi Management System

## 1. Project Overview
The Kulfi Management System is an enterprise-grade administrative and operational portal designed for high-precision management of inventory, sales, and fiscal records for a multi-product frozen dessert business.

### 1.1 Goals
*   **Automation**: Zero-interaction startup and maintenance.
*   **Integrity**: Real-time synchronization between sales and inventory.
*   **Transparency**: Absolute financial visibility through chronological ledgers.
*   **Performance**: Zero-lag operation on local networks.

---

## 2. Core Modules & Functionality

### 2.1 Authentication & Security Node
*   **Access Protocol**: Secure login system with session persistence.
*   **Role-Based Control**:
    *   **Administrators**: Full system access (User management, deletions, cost price editing).
    *   **Staff**: Operational access (Sales entry, inventory viewing, reports).
*   **Security Features**:
    *   CSRF Protection on all forms.
    *   Staff-only restricted financial endpoints.

### 2.2 Product Catalogue (Catalogue Node)
*   **SKU Management**: Unique identity for each product flavor and type.
*   **Dynamic Pricing**: Manage both Selling Price and Unit Cost for margin calculation.
*   **Product Status**: Ability to toggle product visibility (Active/Inactive).

### 2.3 Warehouse Matrix (Logistics Node)
*   **Real-time Tracking**: Automatic stock deduction upon sales commit.
*   **Stock Adjustment**: Manual adjustment (Add/Reduce) with reason logging.
*   **Low Stock Alerts**: Visual "Critical" indicators when stock drops below threshold.
*   **Valuation**: Automatic calculation of current warehouse total value based on cost.

### 2.4 Sales Terminal (POS Node)
*   **High-Speed Entry**: One-page terminal for rapid transaction dispatch.
*   **Auto-Calculation**: Automatic price fetching and total value calculation.
*   **Live Payload**: Dashboard within the terminal showing recent syncs and remaining stock.

### 2.5 General Ledger (Fiscal Node)
*   **Chronological Matrix**: A unified list of Sales (+), Expenses (-), and Income (+).
*   **Running Balance**: Dynamic calculation of cash-on-hand/account balance after every entry.
*   **Filtering**: Date-range specific financial audits.

### 2.6 Operational Intelligence (Reporting)
*   **Daily Insights**: Automated daily sales and profit summary.
*   **Weekly Audits**: Multi-day trends and flavor distribution charts.
*   **Print Matrix**: High-resolution, print-ready sheets for physical record keeping.

---

## 3. Technical Specifications

### 3.1 Infrastructure
*   **Hosting**: Local Network Hosting (Option 2) with auto-binding to `0.0.0.0:8000`.
*   **Database**: ACID-compliant SQLite for reliable local performance.
*   **UI Framework**: Tailwind CSS with custom premium glassmorphism theme.

### 3.2 Automation Scripts
*   **Launch_Kulfi.vbs**: Silent background bootloader.
*   **start.bat**: Environment verification, port cleaning, and network IP detection.
*   **stop.bat**: Graceful engine termination.

### 3.3 Device Compatibility (Responsiveness)
*   **Mobile-First**: Fully optimized for staff using phones/tablets on the shop Wi-Fi.
*   **Breakpoints**: Specialized layouts for Mobile, Tablet, Laptop, and Desktop.

---

## 4. Operational Workflow

1.  **Initialization**: Launch system via `Launch_Kulfi.vbs`.
2.  **Access**: Login via local PC or Mobile (using displayed IP).
3.  **Daily Sales**: Dispatch transactions via the "Sales Terminal".
4.  **Inventory**: Monitor "Warehouse Matrix" for stock replenishment needs.
5.  **Audit**: Review "General Ledger" at end-of-day for financial reconciliation.

---

## 5. Future Roadmap
*   **Sync v2**: Native Android/iOS application integration.
*   **Cloud Hybrid**: Periodic encrypted backups to remote servers.
*   **AI Predict**: Demand forecasting based on historical sales patterns.
