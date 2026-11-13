# Simulation spec (v1, 2D)
- Standalone library, stable API. Python+NumPy first; keep hot loop portable to Rust/C++ later behind same interface.
- Fixed tick: physics 60 Hz, agent decisions 20–30 Hz. No wall-clock. One seeded PRNG owned by the sim.
- Track = versioned JSON: centerline, width, kerbs, pit lane, grid, checkpoints, slipstream/DRS zones, surface types.
- Car: position, heading, velocity, yaw rate; friction-circle tire grip (traction+cornering share limit); engine power/drag curve; brake force; simple downforce; tire wear+temperature affect grip; fuel/battery affects pace.
- Racecraft: collisions with penalties, slipstream (drag reduction behind a car), track limits (off-track slow + penalty), pit stops (pit speed limit, tire change time).
- Rules: standing start with lights, N laps, qualifying (solo timed laps) sets grid, deterministic penalties, classification by laps then time.
- Setup budget: fixed points to distribute (downforce vs top speed, brake bias, tire compound); all else identical.
- Performance: 20 cars × 5 laps ≥ 20× real time on one core, excluding agent compute.
- Property tests: determinism across runs/machines, no NaN, no wall tunnelling at max speed, energy not created.
