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

---

### Prioritized Backlog Summary Table

| Issue Key | Summary | Type | Priority | Story Points | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `DSD-101` | Offline Order Entry & Local Caching | User Story | High | 5 | Ready for Dev |
| `DSD-102` | Automated Tiered Pricing Engine | User Story | High | 3 | Ready for Dev |
| `DSD-103` | Digital Sign-off & Real-Time Van Decrement | User Story | Critical | 5 | Ready for Dev |
| `DSD-104` | Bluetooth Portable Printer Integration | User Story | Medium | 3 | Backlog |
| `DSD-105` | Low-Stock Warning Reorder Triggers | User Story | Low | 2 | Backlog |
