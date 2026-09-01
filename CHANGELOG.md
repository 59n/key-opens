# Changelog

## 1.1.0 — 2026-09-01

### 10am Open: volume imbalance and NQ/MNQ prints

NQ and MNQ often print 10:00 NY away from the prior 1-minute close, and the two contracts can open a few ticks apart. This release treats that as its own thing — not an NDOG/NWOG.

**Added**
- Dedicated **10AM OPEN** settings group (moved out of Key Levels)
- Short, fixed **volume imbalance** box between the 9:59 close and the 10:00 open (does not extend across the chart)
- Optional **NQ 10am** and **MNQ 10am** lines, with auto-pair from the chart ticker and symbol overrides
- **Only show NQ/MNQ if they differ**, with a configurable tick threshold
- Min-gap filter (ticks) so 1-tick noise can be ignored

**Fixed**
- Pine `CE10008`: imbalance helper no longer assigns a global `var` inside a function
- NQ/MNQ extra lines were skipped when they matched the chart 10am print (so NQ showed nothing on an NQ chart)
- Other-contract 10:00 open could grab the **10:01** bar, drawing the line a few ticks off the real open

---

## 1.0.0

Initial public release of **Key Opens**.

- Timed key opens in New York time (18:00 through 09:30, plus 10:00)
- Custom daily opens, weekly / true weekly, monthly / true monthly
- Previous day/week high-low, ATH
- Asia / London / NY AM / NY PM session highs and lows, optional freeze when taken out
- NDOG and NWOG (lines, boxes, or both; top / mid / bottom)
- 1-minute tap detection, tested styles, hide-when-tapped
- Info panel and optional checklist
