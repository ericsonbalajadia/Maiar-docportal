# iTrack
## Web-based Repair and Service Request Management System

**Internal Code Name:** white-cloud  
**Target:** AB.010.001

---

## Site Map
[Project Homepage](project-homepage.md) > **Feedback System**

---

# FR 1.3 - Feedback System

## Functional Name
**Feedback System**

## Description (System Requirement)
Allow requesters to leave feedback after repair/service completion

---

## Use Case: Submit Feedback

### Summary
Enables requester to provide feedback on a completed request.

### Actors
- Requester

### Preconditions
- Request has been completed

### Postconditions
- Feedback is stored and can be reviewed by the clerk or personnel

---

## Basic Flows

| Actor Action | System Response |
|-------------|-----------------|
| 1. Requester selects "Submit Feedback." | 1.1 Displays feedback form for completed requests. |
| 2. Requester submits feedback. | 2.1 Stores feedback and confirms submission. |

---

## Feedback Form Components

### Rating System
**Overall Satisfaction** (Required)
- ⭐⭐⭐⭐⭐ (1-5 stars)
- Visual star rating selector
- Hover tooltips: Very Poor, Poor, Average, Good, Excellent

### Detailed Ratings (Optional)
- **Response Time:** How quickly was your request addressed?
- **Communication:** Were you kept informed throughout the process?
- **Quality of Work:** How satisfied are you with the repair quality?
- **Professionalism:** How professional was the technician?

Each rated on a 1-5 scale

### Written Feedback
**Comments** (Required, minimum 10 characters)
- Multi-line text area
- Character limit: 1000 characters
- Placeholder: "Please share your experience with the repair service..."

### Additional Information
- **Would you recommend our service?** (Yes/No radio buttons)
- **Issue Resolved?** (Yes/Partially/No dropdown)

---

## Feedback Display

### For Requesters
After submission, requesters can:
- View their submitted feedback
- See when feedback was submitted
- Cannot edit once submitted (integrity)

### For Clerks/Personnel
- View all feedback for quality monitoring
- Generate feedback reports
- Identify areas for improvement
- Track technician performance

### For Technicians
- View feedback on their assigned requests
- Monitor their performance ratings
- Receive recognition for excellent service

---

## Feedback Analytics Dashboard

### Metrics Tracked
```
Overall Statistics
- Total Feedback Received: 245
- Average Rating: 4.3/5.0
- Response Rate: 68% (requesters who submitted feedback)
- Recommendation Rate: 85%

Response Time Ratings
- Excellent (5⭐): 120 (49%)
- Good (4⭐): 80 (33%)
- Average (3⭐): 30 (12%)
- Poor (2⭐): 10 (4%)
- Very Poor (1⭐): 5 (2%)
```

### Trends
- Monthly feedback trends
- Category-wise satisfaction
- Technician performance comparison
- Issue resolution rate

---

## Feedback Prompts

### Timing
- **Immediate:** Feedback form available as soon as status changes to "Completed"
- **Reminder:** Email reminder sent 24 hours after completion if no feedback
- **Follow-up:** Second reminder after 3 days
- **Closing:** Feedback window closes after 7 days

### Prompt Messages
```
Your request has been completed!

We value your feedback. Please take a moment to rate your experience.

[Submit Feedback]

Your feedback helps us improve our service and ensures quality maintenance 
for the entire campus community.
```

---

## Database Schema

### Feedback Table
```
- feedback_id (PK)
- request_id (FK)
- requester_id (FK)
- rating (1-5)
- response_time_rating (1-5, nullable)
- communication_rating (1-5, nullable)
- quality_rating (1-5, nullable)
- professionalism_rating (1-5, nullable)
- comments (text)
- would_recommend (boolean)
- issue_resolved (ENUM: 'yes', 'partially', 'no')
- submitted_at
- created_at
```

---

## Feedback Validation Rules

### Required Fields
- Overall rating (1-5 stars)
- Comments (minimum 10 characters)

### Optional Fields
- Detailed ratings (response time, communication, etc.)
- Would recommend (defaults to null if not answered)
- Issue resolved (defaults to 'yes' if not specified)

### Validation Messages
- "Please provide a rating" - if no rating selected
- "Comments must be at least 10 characters" - if too short
- "Comments cannot exceed 1000 characters" - if too long

---

## Feedback Reports

### For Management
**Monthly Feedback Report**
- Total feedback count
- Average ratings by category
- Top performing technicians
- Areas needing improvement
- Trend analysis

### For Technicians
**Individual Performance Report**
- Personal average rating
- Number of requests completed
- Positive feedback highlights
- Areas for improvement
- Comparison with team average

---

## Exceptions

| Exception | System Response |
|-----------|-----------------|
| **Feedback form incomplete** | Display validation errors, prevent submission |
| **System error** | Display error message, allow retry |
| **Request not completed** | Display message: "Feedback can only be submitted for completed requests" |
| **Feedback already submitted** | Display existing feedback with message: "You've already submitted feedback for this request" |

---

## Integration Points

### Email Notifications
- Feedback submission confirmation sent to requester
- Low rating alert sent to supervisor (rating ≤ 2 stars)
- Monthly feedback summary sent to GSO management

### Performance Analytics
- Feedback data feeds into technician performance dashboard
- Used for quarterly performance reviews
- Influences scheduling and assignment decisions

---

## Related Use Cases

- [Submit Feedback](submit-feedback.md) - Detailed feedback submission process
- [Request Tracking](request-tracking.md) - Access feedback form from completed requests
- [Status Update](status-update.md) - Completion triggers feedback prompt

---

© 2026 TRAQ
