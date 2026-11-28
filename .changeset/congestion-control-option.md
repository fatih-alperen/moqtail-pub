---
'relay': minor
'client': minor
---

Add a QUIC congestion-control option: `congestion_control` in the relay YAML
(`bbr`, `cubic` or `reno`) and `--congestion-control` on the test client. The
default stays BBR. QUIC applies one controller per connection, shared by every
stream and every SSTS switching set on it; MOQT does not negotiate a controller.

The relay uses the same controller for connections it dials to cluster peers.
