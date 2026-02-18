## Maiar  
**Target:** MA.010.001

---

#### Site Map
[Project Homepage](../project-homepage.md) > **Status Update**

---

### FR 2.0 - Status Update
Allow GS Clerk/Personnel to update request status (pending, approved, in-progress, completed, cancelled)

---

### Use Case: Update Status
Allow clerk/personnel to update the status of requests in the system.

|  | Description |
|--------|-------------|
| **Actor** | Clerk, Personnel |
| **Precondition** | Request exists in the system |
| **Postcondition** | FRequest status is updated and visible to requester |

#### Basic Flows

| Actor Action | System Response |
|-------------|-----------------|
| Clerk/Personnel selects a request to update. | Displays current status and update options. |
| Clerk/Personnel updates the status. | Saves status and notifies requester. |

---

#### Status Descriptions

| Status | Description | Who Can Set | Next Possible Status |
|--------|-------------|-------------|---------------------|
| **Pending** | New request awaiting review | System (auto) | Approved, Cancelled |
| **Approved** | Request approved, awaiting assignment | Clerk | Assigned, Cancelled |
|  | Personnel assigns technician | Personnel |  |
| **In Progress** | Work is ongoing | Personnel, Clerk | Completed, Assigned |
| **Completed** | Work finished | Personnel, Clerk | (Final state) |
| **Cancelled** | Request cancelled | Clerk/Requester | (Final state) |

---
#### Status Workflow

```
┌──────────┐
│ Pending  │ → Initial status when request is submitted
└────┬─────┘
     │
     ↓
┌──────────┐
│ Approved │ → Clerk reviews and approves request
└────┬─────┘
     │
     ↓
 [Assigned] → Technician assigned to request
     │
     ↓
┌─────────────┐
│ In Progress │ → Work has begun
└────┬────────┘
     │
     ↓
┌───────────┐
│ Completed │ → Work finished
└────┬──────┘
     │
     ↓
  [Feedback]
```
#### Sub-Use Cases

#### 1. [Add Comments](update-request-status-add-comments.md)
Personnel adds comment when updating status.

#### 2. [Send Notification](update-request-status-send-notification.md)
System sends notification after status is updated.

---

<p align="center">© 2026 Oryza</p>


