---
'relay': patch
---

Reject a `REQUEST_UPDATE` whose `SWITCHING_SET_ASSIGNMENT` names a different
switching set. Previously the update was acknowledged and its other fields were
applied to the track's current set, silently ignoring the requested set id. A
track belongs to one switching set at a time; the update now fails before any
subscription parameter or set field changes.
