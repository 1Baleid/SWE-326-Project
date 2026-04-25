# System Test Plan - Phase 1: Requirements Extraction

## Project Information
- **Course:** SWE326 - Software Testing
- **System Under Test:** Indico Events and Conference Management System
- **URL:** https://swe326.online
- **Phase:** 1 - Requirements Extraction
- **Team Leader:** Abdullah

---

## Document History

| Version | Date | Author | Description |
|---------|------|--------|-------------|
| 1.0 | 2026-04-25 | Team | Initial requirements extraction |

---

## System Description

### Overview
Indico is an open-source event management system developed at CERN (European Organization for Nuclear Research). It is a comprehensive web-based platform designed to manage the full lifecycle of academic and professional events, from simple lectures to large-scale international conferences.

### Purpose
The system serves as a centralized platform for:
- **Event Organization**: Creating and managing lectures, meetings, and conferences
- **Room Booking**: Reserving physical spaces for events and meetings
- **Registration Management**: Handling participant registration and payments
- **Abstract Submission**: Managing call for abstracts and peer review workflows
- **Content Management**: Storing and sharing presentations, documents, and materials

### Target Users
| User Type | Description |
|-----------|-------------|
| Event Organizers | Create and manage events, configure registration, manage abstracts |
| Administrators | System-wide configuration, user management, room setup |
| Participants | Register for events, submit abstracts, access event materials |
| Room Managers | Manage room bookings, approve/reject booking requests |
| Reviewers | Review submitted abstracts and provide evaluations |

### Modules Under Test
This test plan covers two primary modules:

1. **Events Module** - Manages three event types:
   - Lectures (simple single-session presentations)
   - Meetings (multi-session collaborative events)
   - Conferences (complex events with registration, abstracts, and tracks)

2. **Room Booking Module** - Handles:
   - Room search and availability checking
   - Single and recurring bookings
   - Pre-booking approval workflows
   - Room blocking and management

### System Access
- **URL**: https://swe326.online
- **Documentation**: https://getindico.io/ and https://indico.global/

---

## Team Members and Assignments

| Member | Assigned Section |
|--------|------------------|
| Abdullah (Leader) | Conference Events (Call for Abstracts, Reviewing, Registration, Payments) |
| Abdulmalik | Category Management + Lecture Events |
| Abdulrahman | Meeting Events (Timetables, Sessions, Contributions, Minutes) |
| Mohammad | Surveys + Zoom Integration + Other Features |
| Rayan | Room Booking Module (Full) |

---

# EVENTS MODULE REQUIREMENTS

---

## 1. Category Management Requirements (Abdulmalik)

| Req ID | Description | Priority |
|--------|-------------|----------|
| CAT-001 | System shall allow users to create a new category within an existing category | High |
| CAT-002 | System shall allow users to specify category title during creation | High |
| CAT-003 | System shall allow users to add a description to a category | Medium |
| CAT-004 | System shall display "Manage" dropdown menu for category operations | High |
| CAT-005 | System shall allow users to edit category settings | High |
| CAT-006 | System shall allow users to set category protection mode (Public, Inheriting, Protected) | High |
| CAT-007 | System shall allow "Public" protection where anyone can access | High |
| CAT-008 | System shall allow "Inheriting" protection where permissions come from parent category | High |
| CAT-009 | System shall allow "Protected" protection where only specific users/groups can access | High |
| CAT-010 | System shall allow adding managers who can modify category and all events within | High |
| CAT-011 | System shall allow setting event visibility options (Everywhere, Category subtree, Category only) | Medium |
| CAT-012 | System shall allow users to delete an empty category | Medium |
| CAT-013 | System shall prevent deletion of categories containing events | High |
| CAT-014 | System shall allow users to move a category to different parent category | Medium |
| CAT-015 | System shall allow creation of subcategories within categories | High |

---

## 2. Lecture Event Requirements (Abdulmalik)

| Req ID | Description | Priority |
|--------|-------------|----------|
| LEC-001 | System shall allow users to create a lecture event by clicking "Create event" | High |
| LEC-002 | System shall allow selection of "Lecture" as event type | High |
| LEC-003 | System shall require users to specify lecture title | High |
| LEC-004 | System shall allow users to specify lecture date and time | High |
| LEC-005 | System shall allow users to specify lecture location/room | Medium |
| LEC-006 | System shall allow users to add description to lecture | Medium |
| LEC-007 | System shall allow adding speakers to a lecture | High |
| LEC-008 | System shall allow specifying speaker name and affiliation | Medium |
| LEC-009 | System shall allow adding materials (files, links) to a lecture | High |
| LEC-010 | System shall allow setting protection mode for lecture (Public, Inheriting, Protected) | High |
| LEC-011 | System shall display lecture in the category calendar | High |
| LEC-012 | System shall allow editing lecture details after creation | High |
| LEC-013 | System shall allow cloning a lecture event | Medium |
| LEC-014 | System shall allow users to delete a lecture event | Medium |
| LEC-015 | System shall allow setting event visibility (Everywhere, Category subtree, Category only) | Medium |

---

## 3. Meeting Event Requirements (Abdulrahman)

### 3.1 Meeting Creation

| Req ID | Description | Priority |
|--------|-------------|----------|
| MTG-001 | System shall allow users to create a meeting event | High |
| MTG-002 | System shall allow selection of "Meeting" as event type | High |
| MTG-003 | System shall require users to specify meeting title | High |
| MTG-004 | System shall allow users to specify meeting date and time | High |
| MTG-005 | System shall allow users to specify meeting end date/time | High |
| MTG-006 | System shall allow users to specify meeting location | Medium |
| MTG-007 | System shall allow adding description to meeting | Medium |
| MTG-008 | System shall allow setting chairperson(s) for meeting | Medium |

### 3.2 Timetable Management

| Req ID | Description | Priority |
|--------|-------------|----------|
| MTG-009 | System shall allow users to access meeting timetable | High |
| MTG-010 | System shall allow adding sessions to meeting timetable | High |
| MTG-011 | System shall allow adding session blocks within sessions | High |
| MTG-012 | System shall allow specifying session block title | High |
| MTG-013 | System shall allow specifying session block start time and duration | High |
| MTG-014 | System shall allow adding conveners to session blocks | Medium |
| MTG-015 | System shall display timetable in chronological order | High |

### 3.3 Session Management

| Req ID | Description | Priority |
|--------|-------------|----------|
| MTG-016 | System shall allow creating sessions with title | High |
| MTG-017 | System shall allow specifying session description | Medium |
| MTG-018 | System shall allow specifying session location/room | Medium |
| MTG-019 | System shall allow assigning session conveners | Medium |
| MTG-020 | System shall allow editing session details | High |
| MTG-021 | System shall allow deleting sessions | Medium |
| MTG-022 | System shall allow reordering sessions in timetable | Medium |

### 3.4 Contributions

| Req ID | Description | Priority |
|--------|-------------|----------|
| MTG-023 | System shall allow adding contributions to session blocks | High |
| MTG-024 | System shall allow specifying contribution title | High |
| MTG-025 | System shall allow specifying contribution duration | High |
| MTG-026 | System shall allow adding speakers to contributions | High |
| MTG-027 | System shall allow specifying speaker name and affiliation | Medium |
| MTG-028 | System shall allow adding materials to contributions | High |
| MTG-029 | System shall allow editing contribution details | High |
| MTG-030 | System shall allow deleting contributions | Medium |
| MTG-031 | System shall allow moving contributions between session blocks | Medium |
| MTG-032 | System shall calculate session block end time based on contributions | High |

### 3.5 Minutes

| Req ID | Description | Priority |
|--------|-------------|----------|
| MTG-033 | System shall allow adding minutes to a meeting | Medium |
| MTG-034 | System shall allow editing meeting minutes | Medium |
| MTG-035 | System shall allow formatting minutes text | Low |
| MTG-036 | System shall display minutes on meeting page | Medium |

### 3.6 Materials

| Req ID | Description | Priority |
|--------|-------------|----------|
| MTG-037 | System shall allow uploading files as materials | High |
| MTG-038 | System shall allow adding links as materials | High |
| MTG-039 | System shall allow specifying material title | Medium |
| MTG-040 | System shall allow downloading uploaded materials | High |
| MTG-041 | System shall allow deleting materials | Medium |

---

## 4. Conference Event Requirements (Abdullah)

### 4.1 Conference Creation and Setup

| Req ID | Description | Priority |
|--------|-------------|----------|
| CONF-001 | System shall allow users to create a conference event | High |
| CONF-002 | System shall allow selection of "Conference" as event type | High |
| CONF-003 | System shall require users to specify conference title | High |
| CONF-004 | System shall allow users to specify conference start and end dates | High |
| CONF-005 | System shall allow users to specify conference location | Medium |
| CONF-006 | System shall allow users to specify timezone | Medium |
| CONF-007 | System shall allow adding conference description | Medium |
| CONF-008 | System shall allow setting conference logo/banner | Low |

### 4.2 Program and Tracks

| Req ID | Description | Priority |
|--------|-------------|----------|
| CONF-009 | System shall allow defining conference program | High |
| CONF-010 | System shall allow creating tracks for the conference | High |
| CONF-011 | System shall allow specifying track title | High |
| CONF-012 | System shall allow specifying track description | Medium |
| CONF-013 | System shall allow assigning track managers | Medium |
| CONF-014 | System shall allow editing track details | High |
| CONF-015 | System shall allow deleting tracks | Medium |

### 4.3 Call for Abstracts

| Req ID | Description | Priority |
|--------|-------------|----------|
| CONF-016 | System shall allow enabling Call for Abstracts feature | High |
| CONF-017 | System shall allow setting Call for Abstracts open date | High |
| CONF-018 | System shall allow setting Call for Abstracts close date | High |
| CONF-019 | System shall allow setting submission instructions | Medium |
| CONF-020 | System shall allow specifying required abstract fields | High |
| CONF-021 | System shall allow specifying optional abstract fields | Medium |
| CONF-022 | System shall allow setting maximum abstract length | Medium |
| CONF-023 | System shall allow users to submit abstracts when CFA is open | High |
| CONF-024 | System shall require submitters to specify abstract title | High |
| CONF-025 | System shall require submitters to specify abstract content | High |
| CONF-026 | System shall allow submitters to select target track | High |
| CONF-027 | System shall allow submitters to add co-authors | Medium |
| CONF-028 | System shall send confirmation email upon abstract submission | Medium |
| CONF-029 | System shall allow submitters to edit submitted abstracts before deadline | High |
| CONF-030 | System shall prevent abstract submission after closing date | High |
| CONF-031 | System shall allow extending/modifying submission deadline | Medium |

### 4.4 Abstract Reviewing

| Req ID | Description | Priority |
|--------|-------------|----------|
| CONF-032 | System shall allow enabling abstract reviewing workflow | High |
| CONF-033 | System shall allow assigning reviewers to tracks | High |
| CONF-034 | System shall allow assigning conveners to tracks | High |
| CONF-035 | System shall allow assigning judges for final decisions | High |
| CONF-036 | System shall allow setting reviewing questions/criteria | High |
| CONF-037 | System shall allow reviewers to access assigned abstracts | High |
| CONF-038 | System shall allow reviewers to submit reviews with ratings | High |
| CONF-039 | System shall allow reviewers to add comments to reviews | Medium |
| CONF-040 | System shall allow conveners to see all reviews for their track | High |
| CONF-041 | System shall allow conveners to propose accept/reject decisions | High |
| CONF-042 | System shall allow judges to make final accept/reject decisions | High |
| CONF-043 | System shall support "Accept", "Reject", "Merge", "Mark as Duplicate" decisions | High |
| CONF-044 | System shall allow bulk operations on multiple abstracts | Medium |
| CONF-045 | System shall send notification emails for review decisions | Medium |
| CONF-046 | System shall allow accepted abstracts to be added to conference program | High |

### 4.5 Registration

| Req ID | Description | Priority |
|--------|-------------|----------|
| CONF-047 | System shall allow enabling registration for conference | High |
| CONF-048 | System shall allow creating registration forms | High |
| CONF-049 | System shall allow adding fields to registration form | High |
| CONF-050 | System shall support text, dropdown, checkbox, date field types | High |
| CONF-051 | System shall allow marking fields as required or optional | High |
| CONF-052 | System shall allow setting registration open date | High |
| CONF-053 | System shall allow setting registration close date | High |
| CONF-054 | System shall allow setting registration modification deadline | Medium |
| CONF-055 | System shall allow setting maximum number of registrations | Medium |
| CONF-056 | System shall allow users to register when registration is open | High |
| CONF-057 | System shall validate required fields during registration | High |
| CONF-058 | System shall send confirmation email upon registration | Medium |
| CONF-059 | System shall allow registrants to modify registration before deadline | High |
| CONF-060 | System shall allow managers to view list of registrations | High |
| CONF-061 | System shall allow managers to export registration data | Medium |
| CONF-062 | System shall allow managers to manually add registrations | Medium |
| CONF-063 | System shall allow managers to edit registrations | Medium |
| CONF-064 | System shall allow managers to cancel registrations | Medium |

### 4.6 Registration Fees and Payments

| Req ID | Description | Priority |
|--------|-------------|----------|
| CONF-065 | System shall allow setting registration fees | High |
| CONF-066 | System shall allow creating different fee categories (early bird, regular, student) | High |
| CONF-067 | System shall allow setting fee amounts per category | High |
| CONF-068 | System shall allow setting fee validity dates | High |
| CONF-069 | System shall calculate applicable fee based on registration date | High |
| CONF-070 | System shall integrate with payment gateways | High |
| CONF-071 | System shall track payment status (pending, paid, cancelled) | High |
| CONF-072 | System shall generate payment receipts | Medium |
| CONF-073 | System shall allow managers to mark payments as received | Medium |
| CONF-074 | System shall allow managers to process refunds | Medium |

### 4.7 Invitations

| Req ID | Description | Priority |
|--------|-------------|----------|
| CONF-075 | System shall allow sending invitations to potential participants | Medium |
| CONF-076 | System shall allow importing email list for invitations | Medium |
| CONF-077 | System shall allow customizing invitation email template | Medium |
| CONF-078 | System shall track invitation status (sent, accepted, declined) | Medium |

### 4.8 Badge Printing

| Req ID | Description | Priority |
|--------|-------------|----------|
| CONF-079 | System shall allow generating badges for registrants | Medium |
| CONF-080 | System shall allow customizing badge layout | Low |
| CONF-081 | System shall allow bulk badge printing | Medium |
| CONF-082 | System shall include registrant information on badges | Medium |

### 4.9 Menu and Layout Customization

| Req ID | Description | Priority |
|--------|-------------|----------|
| CONF-083 | System shall allow customizing conference page layout | Low |
| CONF-084 | System shall allow adding custom menu items | Low |
| CONF-085 | System shall allow reordering menu items | Low |
| CONF-086 | System shall allow hiding default menu items | Low |

---

## 5. Event Surveys Requirements (Mohammad)

### 5.1 Survey Setup

| Req ID | Description | Priority |
|--------|-------------|----------|
| SRV-001 | System shall allow creating surveys for events | High |
| SRV-002 | System shall allow specifying survey title | High |
| SRV-003 | System shall allow specifying survey description/instructions | Medium |
| SRV-004 | System shall allow setting survey as anonymous or identified | High |
| SRV-005 | System shall allow setting survey open date | High |
| SRV-006 | System shall allow setting survey close date | High |

### 5.2 Questionnaire Creation

| Req ID | Description | Priority |
|--------|-------------|----------|
| SRV-007 | System shall allow adding sections to survey questionnaire | Medium |
| SRV-008 | System shall allow specifying section title | Medium |
| SRV-009 | System shall allow adding questions to sections | High |
| SRV-010 | System shall support single choice questions | High |
| SRV-011 | System shall support multiple choice questions | High |
| SRV-012 | System shall support text/open-ended questions | High |
| SRV-013 | System shall support rating scale questions | Medium |
| SRV-014 | System shall allow specifying question text | High |
| SRV-015 | System shall allow marking questions as required or optional | High |
| SRV-016 | System shall allow adding answer options for choice questions | High |
| SRV-017 | System shall allow reordering questions | Medium |
| SRV-018 | System shall allow editing questions | High |
| SRV-019 | System shall allow deleting questions | Medium |

### 5.3 Survey Management

| Req ID | Description | Priority |
|--------|-------------|----------|
| SRV-020 | System shall allow opening survey for responses | High |
| SRV-021 | System shall allow closing survey for responses | High |
| SRV-022 | System shall allow users to submit survey responses when open | High |
| SRV-023 | System shall validate required questions before submission | High |
| SRV-024 | System shall prevent duplicate submissions (configurable) | Medium |
| SRV-025 | System shall allow viewing survey results | High |
| SRV-026 | System shall display response statistics/charts | Medium |
| SRV-027 | System shall allow exporting survey responses | Medium |

---

## 6. Zoom Integration Requirements (Mohammad)

| Req ID | Description | Priority |
|--------|-------------|----------|
| ZOM-001 | System shall allow creating Zoom meetings for events | High |
| ZOM-002 | System shall allow linking existing Zoom meetings to events | High |
| ZOM-003 | System shall allow specifying Zoom meeting title | High |
| ZOM-004 | System shall allow specifying Zoom meeting description | Medium |
| ZOM-005 | System shall allow setting Zoom meeting password | Medium |
| ZOM-006 | System shall allow setting alternative host for Zoom meeting | Medium |
| ZOM-007 | System shall display Zoom meeting link on event page | High |
| ZOM-008 | System shall allow participants to join Zoom meeting from event page | High |
| ZOM-009 | System shall allow editing Zoom meeting details | High |
| ZOM-010 | System shall allow deleting Zoom meeting from event | Medium |

---

## 7. Other Event Features Requirements (Mohammad)

### 7.1 Event Reminders

| Req ID | Description | Priority |
|--------|-------------|----------|
| REM-001 | System shall allow setting up event reminders | Medium |
| REM-002 | System shall allow specifying reminder time (before event) | Medium |
| REM-003 | System shall allow specifying reminder recipients | Medium |
| REM-004 | System shall send reminder emails at specified time | Medium |
| REM-005 | System shall allow customizing reminder message | Low |

### 7.2 Event Cloning

| Req ID | Description | Priority |
|--------|-------------|----------|
| CLN-001 | System shall allow cloning an existing event | Medium |
| CLN-002 | System shall allow specifying new date for cloned event | Medium |
| CLN-003 | System shall copy event details to cloned event | Medium |
| CLN-004 | System shall allow selecting which elements to clone | Low |

### 7.3 Calendar Integration

| Req ID | Description | Priority |
|--------|-------------|----------|
| CAL-001 | System shall allow exporting events to calendar format (ICS) | Medium |
| CAL-002 | System shall allow importing events from calendar files | Low |
| CAL-003 | System shall provide calendar subscription URL | Medium |

---

# ROOM BOOKING MODULE REQUIREMENTS (Rayan)

---

## 8. Room Booking Requirements

### 8.1 Room Search and Display

| Req ID | Description | Priority |
|--------|-------------|----------|
| RB-001 | System shall display list of available rooms | High |
| RB-002 | System shall allow searching rooms by building | High |
| RB-003 | System shall allow searching rooms by capacity | High |
| RB-004 | System shall allow searching rooms by equipment/features | Medium |
| RB-005 | System shall allow filtering rooms by availability | High |
| RB-006 | System shall allow marking rooms as favorites | Low |
| RB-007 | System shall display room details (capacity, phone, equipment) | Medium |
| RB-008 | System shall display room photo if available | Low |
| RB-009 | System shall display room booking calendar | High |
| RB-010 | System shall display room usage statistics | Low |

### 8.2 Single Booking

| Req ID | Description | Priority |
|--------|-------------|----------|
| RB-011 | System shall allow booking a room for a single date | High |
| RB-012 | System shall require specifying booking start time | High |
| RB-013 | System shall require specifying booking end time | High |
| RB-014 | System shall allow specifying booking reason/purpose | High |
| RB-015 | System shall allow adding booking description | Medium |
| RB-016 | System shall validate booking times (end after start) | High |
| RB-017 | System shall check room availability before confirming booking | High |
| RB-018 | System shall confirm successful booking to user | High |
| RB-019 | System shall send booking confirmation email | Medium |

### 8.3 Daily Booking

| Req ID | Description | Priority |
|--------|-------------|----------|
| RB-020 | System shall allow booking a room for full day | Medium |
| RB-021 | System shall apply same booking time across selected date | Medium |

### 8.4 Recurring Booking

| Req ID | Description | Priority |
|--------|-------------|----------|
| RB-022 | System shall allow creating recurring room bookings | High |
| RB-023 | System shall support daily recurrence pattern | High |
| RB-024 | System shall support weekly recurrence pattern | High |
| RB-025 | System shall support monthly recurrence pattern | Medium |
| RB-026 | System shall allow specifying recurrence end date | High |
| RB-027 | System shall allow specifying number of occurrences | Medium |
| RB-028 | System shall display all occurrences before confirming | High |
| RB-029 | System shall allow excluding specific dates from recurrence | Medium |

### 8.5 Pre-Booking (Approval Workflow)

| Req ID | Description | Priority |
|--------|-------------|----------|
| RB-030 | System shall support pre-booking for rooms requiring approval | High |
| RB-031 | System shall allow room managers to configure pre-booking requirement | High |
| RB-032 | System shall notify room manager of pending pre-bookings | High |
| RB-033 | System shall allow room manager to approve pre-bookings | High |
| RB-034 | System shall allow room manager to reject pre-bookings | High |
| RB-035 | System shall notify user of pre-booking approval/rejection | High |
| RB-036 | System shall convert approved pre-booking to confirmed booking | High |
| RB-037 | System shall display pre-booking status to user | Medium |

### 8.6 Booking Conflicts

| Req ID | Description | Priority |
|--------|-------------|----------|
| RB-038 | System shall detect booking conflicts (overlapping times) | High |
| RB-039 | System shall notify user of booking conflicts | High |
| RB-040 | System shall prevent confirming conflicting bookings | High |
| RB-041 | System shall offer to skip conflicting days in recurring bookings | High |
| RB-042 | System shall display conflicting booking details | Medium |

### 8.7 Booking Management

| Req ID | Description | Priority |
|--------|-------------|----------|
| RB-043 | System shall allow users to view their bookings | High |
| RB-044 | System shall allow users to edit their bookings | High |
| RB-045 | System shall allow users to cancel their bookings | High |
| RB-046 | System shall send cancellation confirmation | Medium |
| RB-047 | System shall allow room managers to view all bookings for their rooms | High |
| RB-048 | System shall allow room managers to cancel bookings | High |

### 8.8 Room Blocking

| Req ID | Description | Priority |
|--------|-------------|----------|
| RB-049 | System shall allow room managers to block rooms for periods | High |
| RB-050 | System shall require specifying block start date | High |
| RB-051 | System shall require specifying block end date | High |
| RB-052 | System shall allow specifying block reason | Medium |
| RB-053 | System shall prevent bookings during blocked periods | High |
| RB-054 | System shall display blocked periods on room calendar | High |
| RB-055 | System shall allow room managers to remove blocks | High |
| RB-056 | System shall allow specifying which users can book during block (exceptions) | Medium |

### 8.9 User Roles and Permissions

| Req ID | Description | Priority |
|--------|-------------|----------|
| RB-057 | System shall support "User" role for regular room booking | High |
| RB-058 | System shall support "Room Manager" role for specific rooms | High |
| RB-059 | System shall support "Administrator" role for system-wide access | High |
| RB-060 | System shall allow Users to book available rooms | High |
| RB-061 | System shall allow Users to manage their own bookings | High |
| RB-062 | System shall allow Room Managers to approve/reject pre-bookings | High |
| RB-063 | System shall allow Room Managers to block rooms | High |
| RB-064 | System shall allow Room Managers to manage all bookings for their rooms | High |
| RB-065 | System shall allow Administrators to manage all rooms | High |
| RB-066 | System shall allow Administrators to assign Room Manager roles | High |
| RB-067 | System shall allow Administrators to configure room properties | High |

---

# Testing Techniques for Phase 2

The following testing techniques will be applied during Phase 2 (Manual Testing) based on the requirements extracted above.

---

## 1. Input Space Partitioning (ISP)

### Description
Input Space Partitioning divides the input domain into partitions where inputs within each partition are expected to exhibit similar behavior. Test cases are designed to cover representative values from each partition, including valid inputs, boundary values, and invalid inputs.

### Applicable Requirements
- **Registration Forms (CONF-047 to CONF-064)**: Partitioning email formats, name lengths, field validations
- **Room Booking Inputs (RB-011 to RB-019)**: Partitioning time ranges, date formats, booking durations
- **Survey Inputs (SRV-010 to SRV-016)**: Partitioning response types, text lengths, selection counts

### Example: Email Field Partitioning (CONF-057)

| Partition | Example Values | Expected Result |
|-----------|----------------|-----------------|
| Valid email format | user@domain.com, test.name@university.edu | Accept |
| Missing @ symbol | userdomain.com | Reject |
| Missing domain | user@ | Reject |
| Empty input | (blank) | Reject (if required) |
| Special characters | user+tag@domain.com | Accept |
| Multiple @ symbols | user@@domain.com | Reject |

---

## 2. Control Flow Coverage

### Description
Control Flow Coverage ensures that test cases exercise different execution paths through the system's workflows. This includes statement coverage, branch coverage, and path coverage to verify all decision points and process flows are tested.

### Applicable Requirements
- **Abstract Review Workflow (CONF-032 to CONF-046)**: Submit → Assign Reviewers → Review → Convener Decision → Judge Decision → Accept/Reject
- **Payment Processing Flow (CONF-065 to CONF-074)**: Select Fee → Calculate Amount → Process Payment → Confirm/Fail → Receipt/Retry
- **Pre-Booking Approval (RB-030 to RB-037)**: Request → Pending → Approve/Reject → Confirm/Cancel

### Example: Abstract Review Workflow Paths

```
Path 1: Submit → Review → Accept → Add to Program
Path 2: Submit → Review → Reject → Notify Author
Path 3: Submit → Review → Request Revision → Resubmit → Accept
Path 4: Submit → Mark as Duplicate → Merge with Existing
```

| Path | Branches Covered | Test Case Focus |
|------|------------------|-----------------|
| Accept Path | Review positive, Judge approve | Verify accepted abstracts appear in program |
| Reject Path | Review negative, Judge reject | Verify rejection notification sent |
| Revision Path | Review conditional, Author resubmits | Verify resubmission workflow |
| Merge Path | Duplicate detection branch | Verify merge functionality |

---

## 3. Data Flow Testing

### Description
Data Flow Testing tracks how data values flow through the system, from where they are defined (created/assigned) to where they are used (read/processed). This ensures data integrity across different system components and identifies potential issues with uninitialized or improperly handled data.

### Applicable Requirements
- **Event Creation to Calendar Display**: Event data defined at creation, used in calendar rendering
- **Abstract Submission to Program**: Abstract content defined by author, flows through review, used in final program
- **Registration to Badge Printing**: Registrant data defined at registration, used for badge generation

### Example: Event Data Flow

| Stage | Definition (def) | Use | Verification |
|-------|------------------|-----|--------------|
| Creation | Title, date, location defined | Stored in database | Data persists correctly |
| Display | - | Event details rendered on page | All fields display accurately |
| Calendar | - | Date/time used for calendar entry | Correct positioning in calendar |
| Export | - | ICS file generation | Valid calendar format with correct data |
| Modification | Title updated (re-def) | Updated display | Changes propagate correctly |

### Data Flow Chains
```
Registration Data: Form Input (def) → Validation → Database (use) →
                   Confirmation Email (use) → Badge Print (use) → Export (use)

Abstract Data: Submission (def) → Review Assignment (use) →
              Reviewer Comments (def) → Decision (use) →
              Program Inclusion (use) → Proceedings (use)
```

---

## 4. Logic Coverage (Condition/Decision)

### Description
Logic Coverage tests the logical conditions in system decisions to ensure all combinations of conditions are exercised. This includes:
- **Decision Coverage**: Each decision point evaluates to both true and false
- **Condition Coverage**: Each individual condition within a decision evaluates to both true and false
- **MC/DC (Modified Condition/Decision Coverage)**: Each condition independently affects the decision outcome

### Applicable Requirements
- **Protection Mode Logic (CAT-007 to CAT-009)**: Conditions determining access based on protection settings
- **Booking Conflict Detection (RB-038 to RB-042)**: Conditions for time overlap and room availability
- **Fee Calculation Logic (CONF-065 to CONF-069)**: Conditions determining applicable fee category

### Example: Booking Conflict Detection (RB-038)

**Decision**: Allow booking if `(room is available) AND (no time overlap) AND (user has permission)`

| Test | Room Available | No Time Overlap | User Has Permission | Decision | Purpose |
|------|----------------|-----------------|---------------------|----------|---------|
| 1 | T | T | T | Allow | All conditions true |
| 2 | F | T | T | Deny | Room availability affects decision |
| 3 | T | F | T | Deny | Time overlap affects decision |
| 4 | T | T | F | Deny | Permission affects decision |
| 5 | F | F | F | Deny | All conditions false |

### Example: Fee Category Selection (CONF-069)

**Conditions**:
- A: Registration date ≤ early bird deadline
- B: Registrant is student
- C: Registrant is speaker

| Test | A (Early) | B (Student) | C (Speaker) | Applied Fee |
|------|-----------|-------------|-------------|-------------|
| 1 | T | T | F | Early Bird Student |
| 2 | T | F | F | Early Bird Regular |
| 3 | F | T | F | Regular Student |
| 4 | F | F | F | Regular |
| 5 | T | F | T | Speaker (free) |

---

# Testing Tools

The following tools will be used for testing activities in Phase 2 and Phase 3.

## Manual Testing Tools

| Tool | Purpose | Usage Phase |
|------|---------|-------------|
| Google Chrome | Primary browser for testing | Phase 2, 3 |
| Mozilla Firefox | Secondary browser for cross-browser testing | Phase 2 |
| Chrome DevTools | Debugging, network inspection, console logging | Phase 2, 3 |
| Snipping Tool / Greenshot | Capturing screenshots for bug reports | Phase 2 |
| Microsoft Word | Test plan documentation, bug report templates | Phase 2, 3 |
| Microsoft Excel | Test case management, traceability matrices | Phase 2, 3 |

## Automated Testing Tools

| Tool | Purpose | Usage Phase |
|------|---------|-------------|
| Testsigma | Cloud-based test automation platform with AI-driven test creation | Phase 3 |
| Playwright | Modern browser automation framework with auto-wait, tracing, and multi-browser support | Phase 3 |
| Python/TypeScript | Programming languages for writing Playwright test scripts | Phase 3 |

## Supporting Tools

| Tool | Purpose | Usage Phase |
|------|---------|-------------|
| Git/GitHub | Version control for test artifacts and scripts | All Phases |
| JIRA/Trello | Bug tracking and task management | Phase 2, 3 |
| Postman | API testing (if applicable) | Phase 3 |

---

# Requirements Summary

| Module | Section | Count |
|--------|---------|-------|
| Events | Category Management | 15 |
| Events | Lecture Events | 15 |
| Events | Meeting Events | 41 |
| Events | Conference Events | 86 |
| Events | Surveys | 27 |
| Events | Zoom Integration | 10 |
| Events | Other Features (Reminders, Cloning, Calendar) | 10 |
| Room Booking | Full Module | 67 |
| **Total** | | **271** |

---

# Requirements by Team Member

| Team Member | Sections | Requirement IDs | Count |
|-------------|----------|-----------------|-------|
| Abdulmalik | Category + Lecture | CAT-001 to CAT-015, LEC-001 to LEC-015 | 30 |
| Abdulrahman | Meeting | MTG-001 to MTG-041 | 41 |
| Abdullah | Conference | CONF-001 to CONF-086 | 86 |
| Mohammad | Surveys + Zoom + Other | SRV-001 to SRV-027, ZOM-001 to ZOM-010, REM-001 to REM-005, CLN-001 to CLN-004, CAL-001 to CAL-003 | 49 |
| Rayan | Room Booking | RB-001 to RB-067 | 67 |
| **Total** | | | **273** |

---

# Appendix A: Priority Definitions

| Priority | Definition |
|----------|------------|
| High | Core functionality essential for system operation; must be tested |
| Medium | Important functionality that enhances user experience; should be tested |
| Low | Nice-to-have functionality; test if time permits |

---

# Appendix B: Requirement ID Prefixes

| Prefix | Module/Section |
|--------|----------------|
| CAT | Category Management |
| LEC | Lecture Events |
| MTG | Meeting Events |
| CONF | Conference Events |
| SRV | Event Surveys |
| ZOM | Zoom Integration |
| REM | Event Reminders |
| CLN | Event Cloning |
| CAL | Calendar Integration |
| RB | Room Booking |

---

*Document prepared for SWE326 Software Testing - Phase 1*
*King Fahd University of Petroleum & Minerals*
