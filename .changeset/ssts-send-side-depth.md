---
'relay': patch
---

Count a forwarding stream against its switching set only while the relay is
still writing it. The slot is released when the last byte is handed to the
transport, or when the stream is reset, instead of after waiting for the
FIN-ACK. The FIN-ACK wait grows with RTT, so an idle long-RTT path read as
congested and overlapped more groups than a short-RTT one. The counted interval
is now local: RTT shifts it in time without changing its width.
