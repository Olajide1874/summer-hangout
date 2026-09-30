Duplicate confirmation emails sent when Confirm Booking is double-clicked



**Description**
When a customer clicks "Confirm Booking" twice in quick succession (often due to a slow page response), the system processes the booking twice and sends two identical confirmation emails for the same booking.

**Steps to reproduce**
1. Open the class booking page and select a class time slot.
2. Click "Confirm Booking" twice in quick succession.
3. Check the customer's inbox and the booking logs.

**Expected behavior**
Only one confirmation email should be sent per booking.

**Actual behavior**
Two identical confirmation emails are sent for the same booking.

**Log evidence**
```
[14:03:11] Booking request received: booking_id=B-5521, event=Beach Volleyball Meetup, customer_id=C-2290
[14:03:11] Confirmation email queued: booking_id=B-5521, recipient=customer_id=C-2290
[14:03:11] Confirmation email sent: booking_id=B-5521
[14:03:12] Booking request received: booking_id=B-5521, event=Beach Volleyball Meetup, customer_id=C-2290  (duplicate — resubmission within 1s)
[14:03:12] Confirmation email queued: booking_id=B-5521, recipient=customer_id=C-2290  (duplicate)
[14:03:12] Confirmation email sent: booking_id=B-5521  (duplicate)
```
