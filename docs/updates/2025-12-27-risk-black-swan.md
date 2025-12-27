This update focuses on risk-control correctness and extreme-event behavior.

The recent work was aimed at answering a critical question:
**where risk limits are actually defined and enforced at runtime**, and ensuring that emergency handling behaves deterministically.

Key findings:
- Risk limits are present in environment variables, but the trading system effectively relies on a single active `RiskManager` contract and structured configuration.
- Multiple legacy or conflicting config files exist, creating audit noise but not affecting the active trading path.
- The orchestrator’s auto-tuning logic operates correctly through a dedicated RiskManager property and required no changes.

Special attention was given to the Black Swan event handler.
The logic was cleaned up to ensure:
- best-effort position closure,
- **idempotent risk tightening** with a cooldown,
- absolute emergency caps instead of repeated multipliers,
- and updates applied to the correct RiskConfig fields.

Current status:
- The runtime source of risk limits is now clearly understood.
- Black Swan handling is aligned with the actual RiskManager contract.
- Emergency risk reduction is bounded and repeatable.

Next focus:
- consolidate a single source of truth for risk limits,
- remove or archive legacy configs,
- validate Black Swan behavior end-to-end under simulated conditions.

This work prioritizes predictability and safety over feature expansion.
