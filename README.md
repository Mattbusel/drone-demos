# Tensorust drone stack, live demos

Self-contained, offline static demos of the Tensorust open-source drone crates. Open `index.html` to browse the gallery, or open any demo folder's `index.html` directly. No backend, no build step, no network required.

## Demos

| Demo | What it shows | Crates |
|------|---------------|--------|
| [sentinel-flood](sentinel-flood/) | 500 fake Remote ID identities collapse to one emitter, revealing the real drone | `remoteid`, `remoteid-sentinel`, `remoteid-scenario` |
| [dji-pilot-reveal](dji-pilot-reveal/) | One OcuSync DroneID payload decoded; the drone broadcasts the pilot's location | `remoteid::dji` |
| [remoteid-to-tak](remoteid-to-tak/) | Remote ID bridged to Cursor-on-Target; spoofers arrive as suspect markers | `remoteid`, `uas-cot` |
| [spoofer-caught](spoofer-caught/) | Counter-UAS console: honest drones stay green, public spoofing tools flip red | `remoteid` |
| [flight-replay](flight-replay/) | 96,922 ArduPilot messages replayed to a battery-failsafe RTL | `flightlog-core` |
| [klv-fmv-overlay](klv-fmv-overlay/) | FMV exploitation station over real MISB ST 0601 telemetry with conformance checks | `misb` |

Plus byte-level decoders under [`bits/`](bits/): F3411 Basic ID, F3411 Location, DJI DroneID, MAVLink 2, ST 0601 KLV.

## Honest by design

The scenarios are simulated so each story reads clearly. Every decoded field, trust verdict and detection result is produced by the open-source crates themselves, run natively against real payloads (including DJI captures from the NDSS 2023 research dataset) and replayed in the browser. Nothing is faked and no capability is invented.

The stack is receive-only. There is no transmit path anywhere in this code.

## Crates

- [remoteid](https://crates.io/crates/remoteid) 0.3.3
- [remoteid-sentinel](https://crates.io/crates/remoteid-sentinel) 0.1.0
- [remoteid-scenario](https://crates.io/crates/remoteid-scenario) 0.1.0
- [uas-cot](https://crates.io/crates/uas-cot) 0.6.0
- [misb](https://crates.io/crates/misb) 0.4.1
- [flightlog-core](https://crates.io/crates/flightlog-core) 0.2.0
- [mavlink-tlog](https://crates.io/crates/mavlink-tlog) 0.1.4
