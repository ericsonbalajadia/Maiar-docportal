## Maiar 
**Target:** MA.010.001

#### Site Map
[Project Homepage](../project-homepage.md) > **Request Review**

---

### FR 2.1 - Request Review
Allow GS Clerk to view and check important details and nature of requests

---

### Use Case: Review Request
Enables clerks to review and approve or reject requests.

|  | Description |
|--------|-------------|
| **Actor** | Clerk |
| **Precondition** | Requests are submitted by requesters |
| **Postcondition** | Requests are either approved or rejected |

#### Basic Flows

| Actor Action | System Response |
|-------------|-----------------|
| 1. Clerk selects a request to review. | 1.1 Displays request details. |
| 2. Clerk approves or rejects the request. | 2.1 Updates request status and notifies requester. |

---

#### Decision

**Option 1: Approve**
- Request proceeds to assignment queue
- Status changed to "Approved"
- Requester notified via email

**Option 2: Request More Information**
- Add comment asking for clarification
- Keep status as "Pending"
- Requester notified to provide additional info

**Option 3: Reject**
- Must provide rejection reason
- Status changed to "Cancelled"
- Requester notified with reason

---

#### Sub-Use Cases

#### 1. [Retrieve Request Details](review-request-retrieve-request-details.md)
Clerk/Personnel views full request details for review.

---

<p align="center">© 2026 Oryza</p>