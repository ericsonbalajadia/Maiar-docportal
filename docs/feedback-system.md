## Maiar 
**Target:** MA.010.001

#### Site Map
[Project Homepage](../project-homepage.md) > **Feedback System**

---

### FR 1.3 - Feedback System
Allow requesters to leave feedback after repair/service completion

---

### Use Case: Submit Feedback
Enables requester to provide feedback on a completed request.

|  | Description |
|--------|-------------|
| **Actor** | Requester |
| **Precondition** | Request has been completed |
| **Postcondition** | Feedback is stored and can be reviewed by the clerk or personnel |

#### Basic Flows

| Actor Action | System Response |
|-------------|-----------------|
| 1. Requester selects "Submit Feedback." | 1.1 Displays feedback form for completed requests. |
| 2. Requester submits feedback. | 2.1 Stores feedback and confirms submission. |

---

### Feedback Form Components

#### Rating System

**Service Satisfaction** (Required)
- ⭐⭐⭐⭐⭐ (1-5 stars)
- Visual star rating selector
- Hover tooltips: Not Satisfied, Slightly Satisfied, Moderately Satisfied, Very Satisfied, Extremely Satisfied

**Overall Rating** (Required)
- ⭐⭐⭐⭐⭐ (1-5 stars)
- Visual star rating selector
- Hover tooltips: Poor, Fair, Good, Very Good, Excellent

#### Written Feedback
**Comments and Suggestions** (Required, minimum 10 characters)
- Multi-line text area
- Character limit: 100 characters
- Placeholder: "Please share your experience with the repair service..."

#### Additional Information
- **Would you recommend our service?** (Yes/No buttons)
- **Issue Resolved?** (Yes/Partially/No dropdown)

---

<p align="center">© 2026 Oryza</p>


