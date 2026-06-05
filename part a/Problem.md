## Problem 1: Tatkal Booking Crashes at 10:00 AM [Given]

## What is broken

The Tatkal booking system experiences extreme load spikes when booking opens at 10:00 AM. Users frequently encounter page freezes, session expirations, loading failures, and booking interruptions without meaningful feedback.

 -- Affected Users
Daily Tatkal passengers
Working professionals
Students
Emergency travelers
Travel agents

Potentially lakhs of users attempt booking during the opening window.  

Frequency
Daily
Most severe between 10:00–10:15 AM
Current Flow — Step by Step
User opens IRCTC around 9:50 AM.
User logs into their account.
User searches trains for desired route.
User selects Tatkal quota.
User fills passenger details before 10:00 AM.
User waits for booking window to open.
At 10:00 AM user clicks "Book Now."
Server receives massive simultaneous requests.
Loading spinner appears.
User experiences timeout, refresh, or error.
User retries multiple times.
Tatkal quota becomes unavailable.
Where Exactly It Breaks

Step 8–10.

The platform receives a surge of booking requests but provides no queue position, progress indicator, or explanation of failure.

Severity

High

## Problem 2: Search Filters Do Not Work Reliably [Given]
What is broken

Search filters such as class type, departure time, and seat availability do not consistently update results or persist during navigation.

Affected Users
New users
Elderly passengers
Users comparing multiple trains
Frequency
Every search session involving filters
Current Flow — Step by Step
User searches Delhi → Mumbai.
Train list appears.
User selects Sleeper Class filter.
Results refresh.
User adds "Available Seats Only."
User opens a train detail page.
User returns to search results.
Previously applied filters disappear.
User reapplies filters.
Results appear inconsistent.
Where Exactly It Breaks

Step 7–8.

Filter state is lost during navigation.

Severity

Medium

## Problem 3: Seat Selection Resets [Given]
What is broken

Preferred berth selections often fail to persist throughout booking.

Affected Users
Senior citizens
Women traveling alone
Families
Long-distance travelers
Frequency

Intermittent but commonly reported.

Current Flow — Step by Step
User searches train.
User starts booking.
Passenger details are entered.
User selects Lower Berth preference.
User clicks Continue.
Next page loads.
Berth preference is missing or reset.
User must verify selection again.
Booking proceeds with uncertainty.
Where Exactly It Breaks

Step 5–7.

State synchronization between screens fails.

Severity

High

Problem 4: Confusing Waiting List Information [Self-Discovered]
How I Found It

While checking train availability across multiple classes.

What is broken

Waiting list information is shown using abbreviations such as GNWL, RLWL, PQWL without contextual explanation.

Affected Users
First-time train travelers
Elderly users
Tourists
Frequency

Every time a waitlisted train is searched.

Current Flow — Step by Step
User searches train.
Availability screen opens.
Status shows WL 48.
User notices GNWL/RLWL code.
User attempts to understand chances.
No explanation is visible.
User searches externally.
Decision becomes difficult.
Where Exactly It Breaks

Step 4–6.

Critical booking terminology lacks explanation.

Screenshot

assets/screenshots/waitlist-confusion.png

Severity

Medium

Problem 5: PNR Status and Cancellation Options Are Hard to Locate [Self-Discovered]
How I Found It

While exploring post-booking services.

What is broken

PNR inquiry, cancellation, and TDR filing are separated into different menus and difficult to locate quickly.

Affected Users
Occasional travelers
Elderly passengers
Users needing urgent cancellations
Frequency

Whenever users require post-booking actions.

Current Flow — Step by Step
User logs in.
User wants to cancel a ticket.
User searches navigation menu.
Multiple service categories appear.
User opens incorrect page.
User returns to menu.
User eventually finds cancellation section.
Additional confirmation screens appear.
Where Exactly It Breaks

Step 3–5.

Information architecture makes common tasks difficult to discover.

Screenshot

assets/screenshots/cancellation-navigation.png

Severity

Medium

Problem 6: Mobile Website Layout Creates Booking Friction [Self-Discovered]
How I Found It 

Tested booking flow on mobile browser.

What is broken

Several forms, tables, and train listings require excessive scrolling and make comparison difficult.

Affected Users
Mobile-only users
Rural users
Older smartphone users
Frequency

Every mobile booking session.

Current Flow — Step by Step
User opens IRCTC on mobile browser.
User searches trains.
Results list loads.
User scrolls horizontally and vertically.
Important information appears below fold.
User expands train details.
Interface becomes crowded.
User struggles to compare trains.
Where Exactly It Breaks

Step 4–7.

The responsive layout is not optimized for quick comparison.

Screenshot

assets/screenshots/mobile-layout.png

Severity

Medium–High

Summary Table
Problem	Category	Frequency	Severity
Tatkal Crash	Performance	Daily at 10 AM	High
Filters Reset	Search UX	Frequent	Medium
Seat Selection Reset	Booking Flow	Frequent	High
Waiting List Confusion	Information Design	Frequent	Medium
Cancellation Discovery	Navigation	Frequent	Medium
Mobile Booking Friction	Mobile UX	Daily	Medium-High
Conclusion

The six documented issues impact three major areas:

System reliability (Tatkal booking).
Booking flow usability (filters, seat preferences).
Information architecture and accessibility (waitlist understanding, cancellations, mobile navigation).

These findings will directly inform Part B feature specifications and redesign proposals.