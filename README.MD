# 🕒 Time Range Overlap Detection in PHP / Laravel

Detecting time overlaps is essential in applications like:
- Trip scheduling
- Booking systems
- Calendars
- Vehicle or room availability

This guide explains the **correct way** to detect if two time ranges **overlap**, including code, diagrams, and full examples.

---

## ✅ The Universal Overlap Rule

Two time ranges **A** and **B** overlap if:

```php
A.start < B.end
AND
A.end > B.start


## 📊 Time Range Overlap Examples

| # | Case                                | A_start | A_end | B_start | B_end | Overlap? | Visual |
|---|-------------------------------------|---------|-------|---------|-------|----------|--------|
| 1 | Same time                           | 10:00   | 12:00 | 10:00   | 12:00 | ✅ Yes   | A: \|--------\|<br>B: \|--------\| |
| 2 | Partial overlap (A before B)        | 10:00   | 12:00 | 11:00   | 13:00 | ✅ Yes   | A: \|--------\|<br>&nbsp;&nbsp;&nbsp;&nbsp;B: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\|--------\| |
| 3 | Partial overlap (B before A)        | 11:00   | 13:00 | 10:00   | 12:00 | ✅ Yes   | &nbsp;&nbsp;&nbsp;&nbsp;A: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\|--------\|<br>B: \|--------\| |
| 4 | B fully inside A                    | 10:00   | 14:00 | 11:00   | 12:00 | ✅ Yes   | A: \|-------------\|<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;B: &nbsp;&nbsp;&nbsp;\|-----\| |
| 5 | A fully inside B                    | 11:00   | 12:00 | 10:00   | 14:00 | ✅ Yes   | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A: &nbsp;&nbsp;&nbsp;\|-----\|<br>B: \|-------------\| |
| 6 | No overlap (A ends before B starts) | 10:00   | 11:00 | 11:00   | 12:00 | ❌ No    | A: \|--------\|<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;B: &nbsp;&nbsp;\|--------\| |
| 7 | No overlap (B ends before A starts) | 11:00   | 12:00 | 10:00   | 11:00 | ❌ No    | &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A: &nbsp;&nbsp;\|--------\|<br>B: \|--------\| |

