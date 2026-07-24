lowchart TD

A([Lead Source<br/>Facebook Ads / Landing Page])
--> B[Lead Inquiry Form Submitted]

B --> C[Lead & Offers Workflow<br/>5 SMS + 4 Emails]
C --> D[Pipeline Stage<br/>New Lead]

D --> E{Customer Replied?}

E -- No --> F[Move to Stalled Leads]
F --> G[Remove from Workflows]
G --> H[Notify Admin]

E -- Yes --> I[Stop Promotional Messages]
I --> J[Move to Engaged]
J --> K[Notify Admin]

K --> L{Admin Sends Booking Link?}

L --> M[Appointment Requested]
M --> N[Send 3 Emails + 2 SMS<br/>Booking Link]

N --> O{Appointment Booked?}

O -- No --> F

O -- Yes --> P[Appointment Confirmed]
P --> Q[Add Appointment Booked Tag]
Q --> R[Thank You SMS]
R --> S[Pipeline: Appointment Booked]
S --> T[Appointment Reminder Workflow]

T --> U[Reminder 1 Day Before]
U --> V[Reminder 1 Hour Before]
V --> W[Pipeline: Appointment Reminder Sent]

W --> X{Appointment Outcome}

X -- Patient Arrived --> Y[Checked In]
Y --> Z[Notify Admin]
Z --> AA[Thank You SMS]
AA --> AB[CheckedIn Tag]

AB --> AC[Treatment Completed]
AC --> AD[Thank You Email + SMS]
AD --> AE[3 Month Follow-up]
AE --> AF[Rebooking Campaign Available]

AC --> AG[Review Request Sent]
AG --> AH[Send Google Review Email + SMS]
AH --> AI{Review Submitted?}

AI -- Yes --> AJ[Review Received]

AJ --> AK{Final Outcome}

AK -->|Closed Won| AL[Thank You Email]
AK -->|Closed Lost| AM[Closure Email]

X -- No Show --> AN[No Show Workflow]
AN --> AO[No Show SMS]
AO --> AP[Reschedule Workflow]

AP --> AQ{Rescheduled?}

AQ -- Yes --> P
AQ -- No --> AR[Needs Manual Follow Up]

X -- Cancelled --> AS[Cancellation Workflow]
AS --> AT[Cancellation Email + SMS]
AT --> AP

AF --> J
