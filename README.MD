# 🕒 Time Range Overlap Detection

Detecting time overlaps is essential in applications like:

- Trip scheduling  
- Booking systems  
- Calendars  
- Vehicle or room availability  

This guide explains the **correct way** to detect if two time ranges **overlap**, including PHP code, diagrams, and full examples.

---

## ✅ The Universal Overlap Rule

Two time ranges **A** and **B** overlap if:

```php
A.start < B.end && A.end > B.start
```

## 🧪 Time Range Overlap Examples (Summary Table)
| # | Case                                | A\_start | A\_end | B\_start | B\_end | Overlap? |
| - | ----------------------------------- | -------- | ------ | -------- | ------ | -------- |
| 1 | Same time                           | 10:00    | 12:00  | 10:00    | 12:00  | ✅ Yes    |
| 2 | Partial overlap (A before B)        | 10:00    | 12:00  | 11:00    | 13:00  | ✅ Yes    |
| 3 | Partial overlap (B before A)        | 11:00    | 13:00  | 10:00    | 12:00  | ✅ Yes    |
| 4 | B fully inside A                    | 10:00    | 14:00  | 11:00    | 12:00  | ✅ Yes    |
| 5 | A fully inside B                    | 11:00    | 12:00  | 10:00    | 14:00  | ✅ Yes    |
| 6 | No overlap (A ends before B starts) | 10:00    | 11:00  | 11:00    | 12:00  | ❌ No     |
| 7 | No overlap (B ends before A starts) | 11:00    | 12:00  | 10:00    | 11:00  | ❌ No     |
