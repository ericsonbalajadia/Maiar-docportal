## Maiar 
**Target:** MA.010.001

#### Site Map
[Project Homepage](../project-homepage.md) > **Request Tracking**

---

### FR 1.1 - Request Tracking

Allow requesters to view real-time status of their submitted requests

---

### Use Case: Track Request
Allows requester to manage their request and view the status of their submitted requests.


|  | Description |
|--------|-------------|
| **Actor** | Requester |
| **Precondition** | Requester has submitted at least one request |
| **Postcondition** | Requester can view the current status of their requests |

#### Basic Flows

| Actor Action | System Response |
|-------------|-----------------|
| 1. Requester selects "Track Request." | 1.1 Displays list of requests with current status. |
| 2. Requester selects a request to view details. | 2.2 Displays detailed information about the request and any updates. |

---

#### Status Types

The system tracks the following request statuses:

| Status | Description | Color Indicator |
|--------|-------------|-----------------|
| **Pending** | Request submitted, awaiting clerk review | Orange |
| **Approved** | Request approved by clerk, pending assignment | Purple |
| **In Progress** | Repair/service work is ongoing | Blue |
| **Completed** | Work finished, awaiting feedback | Green |
| **Cancelled** | Request cancelled by requester or clerk | Gray |

---

#### Sub-Use Cases

#### 1. [Add Comments](track-request-add-comments.md)
Requester can add comments or additional information to their request.

#### 2. [Retrieve Request Details](track-request-retrieve-request-details.md)
System fetches and displays complete request information.

---

<p align="center">© 2026 Oryza</p>
