# Agent contract (versioned; also emit JSON Schema/Protobuf in /spec)
**Observation (egocentric only, per decision tick)**: own speed, steering angle, yaw rate, slip, per-tire wear/temp, fuel/energy, lap, race position; track perception (N edge-ray distances, upcoming curvature at fixed look-aheads, surface per tire); nearby cars within radius (relative position/velocity only, never identity/code); race info (gaps ahead/behind, pit window, penalties).
**Action**: steering −1..1, throttle 0..1, brake 0..1, optional pit request + tire choice.
**Limits**: per-tick latency budget (e.g. 5 ms at 30 Hz), max model size, max memory, no file/network. Over budget → repeat previous action; repeated violations → DQ.
**Submission formats (in order)**: (1) ONNX + manifest.json (contract version, I/O names, normalisation) – safest; (2) Python package `agent.py` with `class Agent: reset(info); act(obs)->dict` + lockfile limited to allow-list (numpy, torch-cpu, onnxruntime, scipy), sandbox only; (3) low-code JSON config run by built-in controller.
**SDK** `f1league-sdk`: Gymnasium `F1Env` identical to production, `evaluate(agent)` vs reference bots, `f1league pack` validates + zips.
