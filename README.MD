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
