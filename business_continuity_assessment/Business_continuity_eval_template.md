# Business Continuity

_Documentation of what risks to business continuity a project exhibits and how that affects the readiness for a potential exit from the current supplier_

- **Solution**: `______` · **In-scope repositories**: `______`
- **Snapshot** (date, with commit per repository): `______` · **Prepared by**: `______`

## Exit-readiness assessment

| Post-exit capabilities                                                              | State | What risks are blocking?                  | Combined effort |
| ----------------------------------------------------------------------------------- | ----- | ----------------------------------------- | --------------- |
| Can we keep developing the solution?                                                | ❓     | [open risks](../../issues?q=label%3A%22capability%3Adevelopment%22) | x to x workdays |
| Can we still build and release the solution?                                        | ❓     | [open risks](../../issues?q=label%3A%22capability%3Arelease%22) | x to x workdays |
| Can the releases still be deployed to a production instance?                        | ❓     | [open risks](../../issues?q=label%3A%22capability%3Adeploy%22) | x to x workdays |
| Can we still keep the source code and images secure?                                | ❓     | [open risks](../../issues?q=label%3A%22capability%3Asecurity%22) | x to x workdays |
| Can we ensure that we still keep the solution compliant with current governing law? | ❓     | [open risks](../../issues?q=label%3A%22capability%3Acompliance%22) | x to x workdays |

**State**: ✅ yes · ⚠️ partly · ❌ no · ❓ unknown

**Combined effort**: sum of the effort on the issues blocking that capability (day ranges, not bands), counted once across rows. Effort, not cost.

## Risk matrix

| Risk                            | Likelihood | Impact | Risk rating                               |
| ------------------------------- | ---------- | ------ | ----------------------------------------- |
| [risk-issue](link to the issue) | (1-5)      | (1-5)  | 🔴 **Critical**  / 🟠 **High** / 🟢 **Low** |
| [risk-issue](link to the issue) | (1-5)      | (1-5)  | 🔴 **Critical**  / 🟠 **High** / 🟢 **Low** |
| [risk-issue](link to the issue) | (1-5)      | (1-5)  | 🔴 **Critical**  / 🟠 **High** / 🟢 **Low** |

Risk assessment criteria established per ISO/IEC 27001:2022, 6.1.2; scales and rating bands defined below. Each risk rating maps to one label in the issue tracker: `risk:critical`, `risk:high`, `risk:low`.

**Likelihood**: chance of occurrence within 12 months of the supplier exiting: 5 almost certain · 4 likely · 3 possible · 2 unlikely · 1 rare

**Impact**: consequence for the solution if it occurs: 5 severe, a capability is lost · 4 major, we can't do something important · 3 moderate, slows us down · 2 minor, extra work · 1 negligible

**Risk rating**: likelihood × impact on a 1-5 scale, giving 1-25.

🔴 **Critical** (15-25): act before handover · 🟠 **High** (8-14): plan and schedule · 🟢 **Low** (1-7): accept for now
