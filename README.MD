# Detecting Time Range Overlap in PHP/Laravel

When dealing with scheduling, bookings, trips, or calendars, it's crucial to check if two time intervals **overlap**. This guide explains the **universal rule for detecting overlapping time ranges**, complete with code, visuals, and real examples.

---

## ✅ Overlap Rule

Two time ranges `A` and `B` **overlap** if:

```php
A_start < B_end
AND
A_end > B_start
