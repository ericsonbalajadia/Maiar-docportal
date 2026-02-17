## Maiar 
**Target:** MA.010.001

#### Site Map
[Project Homepage](../project-homepage.md) > **Email Notification System**

---

### FR 1.2 - Email Notification System
Automatically notify requesters via email when their request status changes

---

### Use Case: Send Notification
Allows requester to receive notifications about request updates or system messages.


|  | Description |
|--------|-------------|
| **Actor** | Requester |
| | Email System |
| **Precondition** | Requester is registered and has at least one active request |
| **Postcondition** | Requester receives notifications through the system |

#### Basic Flows

| Actor Action | System Response |
|-------------|-----------------|
| 1. Requester opts in to notifications. | 1.1 Registers requester for notifications. |
| 2. System sends updates automatically. | 2.1 Requester receives notification via system interface or email. |

---

#### Notification Triggers

The system automatically sends email notifications when:

#### Request Status Changes
- **New Request Submitted:** Confirmation email to requester
- **Request Approved:** Notification that request is approved and queued
- **Technician Assigned:** Notification that technician has been assigned
- **Status Changed to In Progress:** Work has begun
- **Status Changed to Completed:** Work is finished, feedback requested
- **Request Cancelled:** Notification of cancellation with reason

#### Comments and Updates
- **New Comment Added:** Email when clerk, or personnel comments
- **Schedule Updated:** Changes to repair schedule

#### System Messages
- **Reminder for Feedback:** If no feedback provided 24 hours after completion
- **Inactivity Notice:** Request pending for extended period

---

### Email Template Structure

#### Email Format

```
From: iTrack System <noreply@itrack-vsu.edu.ph>
To: [requester_email]
Subject: [Status Update] Request #REQ-2026-00123

Dear [Requester Name],

[Main message content based on notification type]

Request Details:
- Request ID: REQ-2026-00123
- Title: [Request Title]
- Status: [Current Status]
- Location: [Building - Room]

If you have any questions, please contact the General Services Office.

Best regards,
University General Services Office

---
This is an automated message. Please do not reply to this email.
To manage notification preferences, visit your account settings.
```
---

#### Notification Preferences

Users can manage their notification settings:

#### Email Preferences
- ☑ Request status updates
- ☐ New comments
- ☑ Assignment notifications

#### Notification Channels
- ☑ Email notifications
- ☐ In-app notifications
---

<p align="center">© 2026 Oryza</p>
