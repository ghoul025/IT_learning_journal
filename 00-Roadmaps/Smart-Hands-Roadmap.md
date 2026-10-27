# Smart Hands+ Learning Roadmap
**Goal:** Become the onsite resource that Network Engineers, Systems Engineers, and IT Operations teams can reliably use during incidents, outages, maintenance, and infrastructure validation.

---

# Phase 1: Infrastructure Awareness (Weeks 1-4)

## Week 1 - Rack & Infrastructure Fundamentals

### Learn
- MDF vs IDF
- Rack layout basics
- Patch panels
- Access switches
- Core switches
- Routers
- Firewalls
- UPS
- PDU

### Objectives
- Identify every major device in your server/network room.
- Understand its purpose at a high level.
- Know which team owns each device.

### Practical Exercise
Walk the rack and answer:

- What is this device?
- What is it connected to?
- Who manages it?
- Is it critical to operations?

### Deliverable
Create:

```text
Site Infrastructure Map
```

---

## Week 2 - Cabling & Ports

### Learn

#### Copper
- Cat5e
- Cat6
- RJ45

#### Fiber
- Single Mode
- Multi Mode
- LC
- SC

#### Console
- USB Console
- RJ45 Console
- Serial Connections

### Objectives
Instantly identify:

- Ethernet cable
- Fiber cable
- Console cable
- Power cable

### Practical Exercise

Take photos and label:

```text
Cable Type
Purpose
Connected Device
```

---

## Week 3 - Switch Fundamentals

### Learn

- Access Switch
- Distribution Switch
- Core Switch

### Understand

- Access Port
- Trunk Port
- Uplink
- Downlink
- VLAN

### Objectives

When an engineer says:

```text
Check the uplink.
```

You immediately know where to look.

### Deliverable

Document:

```text
Switch Models
Switch Locations
Critical Uplinks
```

---

## Week 4 - Firewall Awareness

### Learn

- Firewall purpose
- LAN vs WAN
- NAT
- Security Policies
- ACL basics

### Vendor Familiarity

- Fortinet
- Palo Alto
- Cisco ASA

### Objectives

Visually identify:

```text
Firewall
Switch
Router
```

without hesitation.

---

# Phase 2: Remote Access & Validation (Weeks 5-8)

## Week 5 - PuTTY Mastery

### Learn

#### SSH
```bash
ssh user@ip-address
```

#### Serial Connections

- COM Port
- Serial Console
- USB Console

### Practice

- Create saved sessions
- Open SSH sessions
- Open Serial sessions

### Goal

When a Network Engineer says:

```text
Console into the switch.
```

You can do it confidently.

---

## Week 6 - CLI Familiarity

### Learn What These Mean

```bash
show version
show interfaces
show vlan
show inventory
show running-config
show ip interface brief
```

### Objective

You do NOT need to memorize.

You only need to:

- recognize them
- understand what information they provide

### Practical Exercise

Review sample outputs online.

---

## Week 7 - Infrastructure Validation

### Learn

How engineers verify:

- Link status
- Interface status
- Port activity
- Hardware health

### Replace This

```text
Looks okay.
```

### With This

```text
Gi1/0/48 is up.

Activity LEDs present.

No alert indicators observed.
```

### Goal

Report facts.

Never assumptions.

---

## Week 8 - Incident Support Workflow

### Learn

```text
Observe
↓
Validate
↓
Collect Information
↓
Escalate
↓
Monitor
```

### Practice

After every incident, answer:

- What information was needed?
- What information was missing?
- What could have been validated earlier?

### Deliverable

```text
Incident Observation Notes
```

---

# Phase 3: Server & Operations Support (Weeks 9-12)

## Week 9 - Server Hardware Fundamentals

### Learn

#### Dell

```text
iDRAC
```

#### HPE

```text
iLO
```

#### Lenovo

```text
XClarity
```

### Hardware Concepts

- RAID
- PSU
- NIC Status
- Fault Indicators

### Objective

Recognize healthy vs unhealthy hardware indicators.

---

## Week 10 - Virtualization Awareness

### Learn

- VMware
- ESXi
- Hyper-V

### Concepts

- Host
- VM
- Cluster
- Datastore

### Objective

Understand conversations between engineers.

Not administration.

---

## Week 11 - Smart Hands Runbooks

### Build Checklists

Examples:

#### Firewall Verification

```text
1. Verify power
2. Verify WAN link
3. Verify LAN link
4. Check fault indicators
5. Capture photo
```

#### Switch Validation

```text
1. Verify power
2. Verify uplink
3. Verify stack status
4. Check alarms
5. Report findings
```

---

## Week 12 - Incident Simulation

### Practice Scenarios

#### Scenario 1

```text
Engineer requests uplink verification.
```

#### Scenario 2

```text
Engineer requests console access.
```

#### Scenario 3

```text
Engineer requests firewall health check.
```

#### Scenario 4

```text
Engineer requests server status validation.
```

### Goal

Respond without needing to Google every step.

---

# Ongoing Weekly Habits

## Networking (2x/week)

Topics:

- DNS
- DHCP
- VLANs
- Routing
- NAT
- Wireless
- VPN

### Goal

Build NOC-level awareness.

---

## Smart Hands Journal

After every incident log:

```text
Date:
Issue:
Impact:
Teams Involved:
What I Observed:
What I Learned:
What I Would Do Faster Next Time:
```

---

## Operations Journal

Track:

```text
Incidents Supported
Escalations Assisted
Network Tasks
Server Tasks
Asset Tasks
```

These later become:

- Resume bullets
- Interview stories
- Performance review evidence

---

# Success Criteria

Within 3-6 Months You Should Be Able To:

✅ Identify all major infrastructure devices on-site

✅ Connect using PuTTY via SSH or Serial

✅ Understand basic switch and firewall terminology

✅ Validate ports, uplinks, and hardware indicators

✅ Communicate effectively with remote engineers

✅ Act as reliable Smart Hands during incidents

✅ Speak the language of NOC, Network, and Infrastructure teams

---

# End Goal

```text
IT Operations
      ↓
Trusted Smart Hands
      ↓
Operations Specialist
      ↓
NOC / Infrastructure Analyst
      ↓
Network or Systems Engineer
```

**Target mindset:**
"I don't need to be the engineer fixing the outage. I need to be the onsite person the engineer trusts during the outage."
