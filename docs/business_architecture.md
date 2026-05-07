## 🏗️ Business Architecture

The diagram below illustrates ClaimSense's three core operational flows — from initial setup through to batch fraud detection and individual claim deep-dives.

![ClaimSense Business Architecture](/docs/images/business_flows.png)

### Flow 1 — Onboarding
The user connects ClaimSense to their data environment and configures the rule set before any analysis begins:

1. **Configure DB connection** — point ClaimSense at your claims database; no data migration needed
2. **Upload data dictionary** — map your schema so ClaimSense understands your data structure
3. **Configure rules** — choose from standard out-of-the-box fraud rules and add custom insurer-defined rules

### Flow 2 — Run Scenarios
Once configured, ClaimSense runs a full batch analysis across all claims:

1. **Initiate** — trigger a scenario run manually or on a schedule
2. **Predictive modelling** — AI analyses patterns across your claims history
3. **Check all claims** — every open and closed claim is evaluated against configured rules
4. **Output** — each claim receives a fraud score (high / medium / low), a clear explainability summary, and is added to the adjuster's prioritised investigation queue

### Flow 3 — Individual Claim Analysis
For claims that need closer attention, adjusters can deep-dive a single claim:

1. **Select claim** — pick any claim from the system
2. **Predictive modelling** — run AI analysis on that specific claim
3. **Run rules** — apply any or all configured rules to the claim
4. **View results** — see the fraud score and the reasons behind it
5. **Add a new rule** — define a custom condition based on what you observe
6. **Test on claim** — instantly see the impact of the new rule on the selected claim
7. **Save rule** — the new rule is saved and automatically applied in all future Flow 2 batch runs and individual claim analyses

---