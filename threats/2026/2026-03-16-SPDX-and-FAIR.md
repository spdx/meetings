# FAIR and SPDX

<sub>Prepared for the SPDX Working Group by Jack Jones</sub>

<sub>Converted to markdown by Karsten Klein.</sub>

## Part 1: How FAIR Approaches Component Risk
Before getting into framework mechanics, it helps to start with a simple question: risk to whom, and in the form of what harm?

When we analyze the risk associated with a component like a network attachment dongle, it’s easy to focus on the component's attributes: is the firmware signed?  Is the vendor still issuing patches?  Are update channels authenticated?  These are all legitimate and important questions, but they describe conditions, not risk.  Risk lives downstream of those conditions, in the harm that could come to the organization that purchased and deployed the device.

Keeping the purchaser's harm front and center is exactly where FAIR starts.

### Start with the Loss Event
FAIR organizes risk analysis around loss events: specific, concrete things that cause harm to an asset owner.  In the case of a network dongle, the relevant loss event can be something like:
> The dongle is exploited as an attack vector, enabling unauthorized access to systems on the purchaser's network, which results in harm."

That one sentence does a lot of work.  It tells us who is harmed (the purchaser), what the mechanism of harm is (exploitation of the device), and what the consequence is: unauthorized network access that cascades into, for example data loss, operational disruption, regulatory exposure, and recovery costs.  Until we have that loss event scenario as an anchor, we can’t meaningfully reason about how serious the risk is or what to do about it.

### Mapping the Working Group's Concerns to FAIR Concepts
Scenarios like those raised in last week’s call (unauthorized updates and end-of-life (EOL) status) fit naturally into this framing once we have the loss event defined.
#### Scenario 1: Unauthorized Update
The authorized update concern is really a concern about supply chain integrity.  If a threat actor can tamper with a firmware update and deliver it through a legitimate channel, the dongle becomes a trusted but hostile presence on the network.  The control that prevents this, verifying that updates come from an authenticated, authorized source, directly reduces the likelihood that such a loss event occurs.  FAIR calls this loss event frequency: or how often a harmful action successfully compromise the asset and cause harm?  Strong update authentication keeps that number low.

#### Scenario 2: Unsupported / End-of-Life Dongle
The EOL concern is a different kind of problem.  It is not a specific attack; it’s the gradual degradation of a key control.  When a vendor stops issuing patches, vulnerabilities accumulate.  As time passes and those vulnerabilities become better understood by the attacker community, the likelihood of a successful exploit increases.  In FAIR terms, EOL status affects both threat capability (attackers have more to work with) and susceptibility (the device becomes progressively less resistant to attack).  The potential harm to the purchaser is the same as Scenario 1, but it’s potential increases on a slow curve rather than as a discrete event.

### Why This Matters for Prioritization
Here is where FAIR-like analysis earns its keep.  Not every dongle in every deployment carries the same risk, even if they share the same CVE profile or EOL date.  A dongle that manages access to a critical system on a sensitive network segment, in an environment with limited monitoring and slow incident response, carries far more risk than an identical dongle attached to an isolated, non-critical system in a well-monitored environment.

Attribute-based scoring approaches, such as CVSS, tend to treat the component's properties as a proxy for risk.  FAIR treats the component's properties as inputs to the analysis, not the answer.  The answer depends on the environment, the exposure, the quality of surrounding controls, and the magnitude of harm if things go wrong.  That provides the basis for an assessment the purchaser actually needs.

### A Practical Path Forward

For the purposes of SPDX risk assessment work, it may be useful to think about component risk in two layers.

The first layer is what FAIR calls **loss event frequency**: given this component in this deployment context, how likely is it that a harmful event occurs within some relevant time horizon?  Component attributes like update integrity and EOL status are key inputs here, but so are deployment context factors that sit outside the component itself.

The second layer is **loss magnitude**: if the event occurs, how bad is it for the purchaser?  This depends heavily on what the component is connected to, what data or operations it touches, and how quickly the organization can detect and respond.

Together, these two layers produce a risk estimate that supports decisions such as whether to accept the risk, mitigate it, transfer it, or avoid it.

## Part 2: What’s needed to Support Risk Analysis

As I understand it (and I may be wrong about this) SPDX provides a component description schema: it captures what a component is, including its identity, version, supplier, license, known vulnerabilities, and dependencies.  FAIR is fundamentally a loss event analysis framework.  It needs deployment-context data: what is this component connected to, how is it exposed, what controls surround it, and how sensitive or critical are the assets it touches.

The gap between those two is where most of the work lives.


It seems to me that current SPDX data can feed the threat capability and susceptibility inputs to a FAIR-style analysis -- CVE data, EOL status, and patch authentication mechanisms all speak to whether a component is exploitable and how easily.  But FAIR also needs data that SPDX may not currently have a home for.  Without those fields, SPDX data can tell you something about a component's exploitability, but not about the risk it poses to a specific purchaser in a specific deployment.
What follows is an example set of deployment-context fields, organized by the analytical purpose they serve within FAIR's variable structure.  Not all of these would need to live in the core SPDX schema.  Some are component properties; others are deployment properties that might more naturally belong in a companion record associated with an SPDX bill of materials entry at the time of deployment.  That is an architectural question for the working group, but the field definitions below should help frame it.

### Exposure Fields

**Analytical purpose:** Feed threat contact frequency.  These describe how reachable the component is from the outside world.  A dongle sitting behind three layers of network segmentation with no remote management capability is a fundamentally different risk object than an identical dongle that is internet-reachable and remotely administered.

* Network exposure tier: internet-facing / intranet-only / air-gapped / physically isolated
* Remote management enabled: yes / no
* Management interface type: vendor cloud portal / on-premises / none
* Physical access requirements: open facility / controlled access / restricted or secured area
* Authentication required for access: none / single factor / multi-factor

### Asset Sensitivity Fields
**Analytical purpose:** Feed loss magnitude.  These describe what the component can reach, which is the primary driver of how bad things get if it is compromised.

* Data classification of accessible assets: public / internal / confidential / restricted
* System criticality tier: non-critical / business-important / mission-critical
* Regulatory scope: list applicable regimes (PCI-DSS, HIPAA, SOX, etc.) if any
* Estimated population at risk: rough order of magnitude for records, users, or systems accessible through this component
* Operational dependency: is this component in a path where failure or compromise causes operational disruption? (yes / no)

### Control Environment Fields
**Analytical purpose:** Feed resistance strength and loss magnitude via detection and response capability.  This is where FAIR most visibly departs from attribute-based scoring: the same component carries very different risk depending on what controls are wrapped around it in the specific deployment.

* Patch and update management: automated with verification / manual with verification / manual without verification / none
* Network monitoring coverage: full packet capture / flow data / agent-based / none
* Alerting on anomalous component behavior: yes / no / unknown
* Mean time to detect (estimated tier): hours / days / weeks / unknown
* Mean time to respond (estimated tier): hours / days / weeks / unknown
* Incident response plan covers this component type: yes / no / unknown

### Threat Context Fields
**Analytical purpose:** Feed threat capability and probability of action.  These are largely derivable from existing data sources such as CVE databases and threat intelligence feeds, but they need a home in the schema to be usable analytically.

* Known active exploitation in the wild: yes / no / unknown
* Public exploit code available: yes / no / unknown
* Attacker community interest level: low / moderate / high (sourced from threat intel)
* Component present in known attack campaigns: yes / no / unknown

### Design Considerations for the Working Group

**Field precision does not need to be high to be useful.** Ordinal tiers, such as internet-facing versus air-gapped, or mission-critical versus non-critical, capture most of the analytical leverage.  FAIR works well with ranges and ordinal judgments; it does not require false precision.

**Component properties and deployment properties are different things.** The exposure, asset sensitivity, and control environment fields above describe the deployment, not the component itself.  They are likely better suited to a companion record structure that gets associated with an SPDX bill of materials entry at deployment time, rather than embedded in the core component description.

**Some fields will be uncomfortable for vendors to populate.** Fields that imply liability-adjacent judgments about component behavior in specific environments are more naturally filled in by the purchaser and deployer.  The schema design should accommodate that division of responsibility.

> Importantly, the goal here is not to impose FAIR's full machinery on SPDX.  It’s to help ensure that the data SPDX captures and the data FAIR needs are aligned, so that organizations using SPDX as a foundation can build toward useful risk estimates without having to reconstruct the context from scratch.  That alignment seems achievable, and the field list above might be a practical starting point for defining what it would take.  Also, the data needed for a FAIR analysis would be virtually identical for any risk measurement method.

