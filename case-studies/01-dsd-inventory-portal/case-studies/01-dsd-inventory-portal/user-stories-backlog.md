# Jira User Stories & Acceptance Criteria

**Epic:** `EPIC-101: Field Order Capture & Inventory Deduction`  
**Product:** DSD Mobile Order & Inventory Portal  
**Author:** Product Owner / Business Analyst  

---

### Story 1: Offline Order Entry
* **Issue Key:** `DSD-101`
* **Priority:** High (Must Have)
* **Estimation:** 5 Story Points
* **User Story:**  
  *As a* DSD Route Specialist,  
  *I want to* log store inventory counts and create a restock order even when inside a grocery store walk-in freezer with no cellular service,  
  *So that* my delivery workflow is not delayed by poor connectivity.

**Acceptance Criteria (Gherkin Format):**
* **Scenario 1: Creating an order without network connectivity**
  * **Given** the mobile application has no cellular or Wi-Fi connection,
  * **When** the route specialist inputs delivered quantities (e.g., 15 cases of sausage, 10 cases of cheese) and taps "Save Order,"
  * **Then** the application stores the order locally in offline cache,
  * **And** displays a persistent banner: *"Offline: 1 order queued for sync."*
* **Scenario 2: Automatic synchronization when connection restores**
  * **Given** a queued order exists in the local cache,
  * **When** the mobile device reconnects to a cellular or Wi-Fi network,
  * **Then** the application automatically uploads the order to the central server within 30 seconds,
  * **And** updates the order status from "Pending Sync" to "Confirmed."

---

### Story 2: Tiered Promotional Pricing Engine
* **Issue Key:** `DSD-102`
* **Priority:** High (Must Have)
* **Estimation:** 3 Story Points
* **User Story:**  
  *As a* DSD Route Specialist,  
  *I want* the system to automatically apply wholesale volume discounts when an order meets predetermined case thresholds,  
  *So that* I do not have to calculate custom promotional pricing by hand.

**Acceptance Criteria (Gherkin Format):**
* **Scenario 1: Applying volume discount threshold**
  * **Given** a retail account has an agreed tier discount of 10% off for orders $\ge$ 20 cases,
  * **When** the route specialist adds 20 or more cases to the active invoice,
  * **Then** the system automatically applies the 10% discount line item,
  * **And** displays the updated net invoice total before final confirmation.
* **Scenario 2: Order below volume threshold**
  * **Given** the retail account's minimum volume threshold is 20 cases,
  * **When** the route specialist adds 18 cases to the order,
  * **Then** the system applies the base wholesale unit price,
  * **And** displays a reminder: *"Add 2 more cases to unlock 10% volume discount."*

---

### Story 3: Van Inventory Decrement & Sign-Off
* **Issue Key:** `DSD-103`
* **Priority:** Critical (Must Have)
* **Estimation:** 5 Story Points
* **User Story:**  
  *As a* DSD Route Specialist,  
  *I want* my loaded van inventory to update immediately upon obtaining the store manager’s digital signature,  
  *So that* I maintain real-time visibility into my remaining stock across the rest of the daily route.

**Acceptance Criteria (Gherkin Format):**
* **Scenario 1: Delivery sign-off and instant deduction**
  * **Given** the route specialist has a start-of-day van count of 70 cases,
  * **When** the store manager signs the digital delivery screen for a delivery of 15 cases and submits,
  * **Then** the system deducts 15 cases from the vehicle balance,
  * **And** updates the available van stock display to 55 cases,
  * **And** emails a PDF copy of the signed receipt to the store contact.
* **Scenario 2: Attempting to confirm delivery exceeding truck stock**
  * **Given** the vehicle stock shows 10 remaining cases,
  * **When** the route specialist attempts to confirm a delivery order of 12 cases,
  * **Then** the system prevents submission and displays an error: *"Insufficient truck inventory: 10 cases available."*
# Jira User Stories & Acceptance Criteria

**Epic:** EPIC-101: Field Order Capture & Inventory Deduction  
**Product:** DSD Mobile Order & Inventory Portal  
**Author:** Product Owner / Business Analyst  
**Methodology:** Scrum / Kanban Hybrid  
**Status:** Ready for Sprint Planning  

---

## Strategic Intent
Eliminate reconciliation discrepancies between delivery driver stock and retail receiving docks by introducing offline-first barcode scanning, automated shortage triage, and real-time electronic Proof of Delivery (ePOD).

---

## User Stories & Gherkin Acceptance Criteria

### Story 1: Offline Order Entry & Barcode Scanning
* **Issue Key:** DSD-101
* **Priority:** High (P1)
* **Story Points:** 5
* **User Story:**  
  *As a* Route Delivery Driver,  
  *I want to* scan crate barcodes and capture orders while in offline mode,  
  *So that* distribution check-in velocity is not halted by retail basement dead zones.

#### Acceptance Criteria
* **Scenario 1: Scan execution in disconnected state**
  * **Given** the driver device has no active Wi-Fi or cellular connectivity,
  * **When** the driver scans a valid GS1-128 crate barcode,
  * **Then** the system validates the scan against the locally cached daily manifest,
  * **And** flags the line item with an "Offline Staged" badge.
* **Scenario 2: Automatic delta sync upon reconnection**
  * **Given** 1 or more scans are queued locally on the handheld device,
  * **When** network connectivity is re-established for $\ge 5$ consecutive seconds,
  * **Then** the application executes a background sync against the inventory service,
  * **And** updates the UI status indicator to "Synced".

---

### Story 2: Discrepancy Flagging & Short-Shipment Triage
* **Issue Key:** DSD-102
* **Priority:** Critical (P0)
* **Story Points:** 8
* **User Story:**  
  *As a* Receiving Store Manager,  
  *I want* the system to flag manifest shortfalls immediately prior to invoice sign-off,  
  *So that* the final bill reflects verified received quantities rather than planned manifest numbers.

#### Acceptance Criteria
* **Scenario 1: Intake count shortfall**
  * **Given** a planned order of 40 cases for SKU #8821,
  * **When** the driver intake scan logs only 36 physical cases,
  * **Then** the portal triggers a blocking alert: `"Shortfall Detected: -4 units for SKU #8821"`,
  * **And** requires both driver and receiver PIN verification to proceed.
* **Scenario 2: Real-time invoice adjustment**
  * **Given** a verified shortfall has been authorized by both parties,
  * **When** the final delivery ticket is compiled,
  * **Then** the invoice total recalculates immediately for the 36 delivered units,
  * **And** a return/shortage record routes automatically to central dispatch.

---

### Story 3: Electronic Proof of Delivery (ePOD) & Sign-Off
* **Issue Key:** DSD-103
* **Priority:** High (P1)
* **Story Points:** 3
* **User Story:**  
  *As a* Route Delivery Driver,  
  *I want* to capture an electronic signature and store receiver ID on glass,  
  *So that* delivery disputes and shrinkage claims have an auditable digital trail.

#### Acceptance Criteria
* **Scenario 1: Sign-off verification**
  * **Given** all manifest line items are marked accepted or short,
  * **When** the receiving manager signs the device screen and enters their employee ID,
  * **Then** the record generates a SHA-256 digital stamp containing GPS coordinates and timestamps,
  * **And** dispatches a finalized PDF receipt to the store contact within 60 seconds.

---

## Definition of Done (DoD)
* **Testing:** All Gherkin scenarios verified through automated unit/integration test suites.
* **Data Integrity:** Local client storage (IndexedDB/SQLite) retains transaction queues across forced app closures.
* **Traceability:** User stories linked to Figma UI mocks and Jira acceptance criteria fields.
* **Architecture:** Payload contracts and error states documented in Confluence.
---

### Prioritized Backlog Summary Table

| Issue Key | Summary | Type | Priority | Story Points | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `DSD-101` | Offline Order Entry & Local Caching | User Story | High | 5 | Ready for Dev |
| `DSD-102` | Automated Tiered Pricing Engine | User Story | High | 3 | Ready for Dev |
| `DSD-103` | Digital Sign-off & Real-Time Van Decrement | User Story | Critical | 5 | Ready for Dev |
| `DSD-104` | Bluetooth Portable Printer Integration | User Story | Medium | 3 | Backlog |
| `DSD-105` | Low-Stock Warning Reorder Triggers | User Story | Low | 2 | Backlog |
