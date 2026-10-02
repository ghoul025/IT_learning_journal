# Fundamentals

## What Is IT Operations

IT Operations is responsible for keeping technology working so people can do their jobs.

The goal is simple:

- Keep services running
- Support users
- Resolve issues
- Manage technology resources
- Reduce operational risk

Whether the environment is on-premises, cloud-based, or hybrid, IT Operations exists to ensure systems remain available, usable, and reliable.

### Examples

- Restoring a user's access to an application.
- Replacing a failed laptop.
- Investigating a service outage.
- Monitoring systems for problems.
- Managing user accounts and permissions.

---

## Core Objectives

Every IT Operations team works toward the same basic goals.

### Availability

Systems and services should be accessible when people need them.

**Example:** Users can access email, chat, and business applications during working hours.

### Reliability

Services should work consistently.

**Example:** Users can connect to the VPN every day without frequent failures.

### Stability

Technology should remain predictable and dependable.

**Example:** Updates are tested before deployment to avoid unexpected outages.

### Performance

Systems should operate efficiently.

**Example:** Applications respond within acceptable timeframes.

### Security

Access to systems and data should be controlled appropriately.

**Example:** Removing access when an employee leaves the organization.

### Supportability

Technology should be manageable and easy to troubleshoot.

**Example:** Devices follow standard configurations and procedures.

---

## What IT Operations Manages

IT Operations manages both technology resources and operational activities.

### Technology Resources

#### Services

Applications and systems used by the business.

Examples:

- Email
- Collaboration tools
- Internal applications
- Business platforms

#### Users

The people who use technology services.

Examples:

- Employees
- Contractors
- Support teams

#### Endpoints

Devices used to access company resources.

Examples:

- Laptops
- Desktops
- Mobile devices
- Thin clients

#### Assets

Technology owned or managed by the organization.

Examples:

- Computers
- Monitors
- Software licenses
- Peripherals

#### Access

Permissions that determine what users can use.

Examples:

- Application access
- Shared folders
- Administrative permissions

### Operational Activities

#### Incidents

Unexpected issues affecting services.

**Example:** Users cannot log in to a business application.

#### Requests

Routine tasks requested by users.

Examples:

- Software installation
- Password reset
- New account creation

#### Changes

Modifications made to systems or services.

Examples:

- Application upgrades
- Configuration updates
- Device replacements

---

## Understanding Service Dependencies

Technology services rarely operate on their own. Most services depend on multiple systems working together.

```text
Users
   ↓
Applications
   ↓
Systems
   ↓
Network
   ↓
Power
```

A problem at a lower layer can affect everything above it.

For example:

```text
Power Failure
   ↓
Network Equipment Offline
   ↓
Application Unavailable
   ↓
Users Cannot Work
```

Because of these dependencies, IT Operations should avoid focusing only on the visible symptom.

Instead, investigate the services and components that support the affected system.

### Examples

#### Application Issue

A user reports that a business application is unavailable.

Possible causes:

- Application failure
- System failure
- Database issue
- Network issue
- Authentication service issue

The visible symptom is the same, but the root cause may exist elsewhere in the dependency chain.

#### Login Issue

A user cannot access an application.

Possible causes:

- Account problem
- Identity service failure
- Network connectivity issue
- Application configuration issue

Good troubleshooting requires understanding how services depend on one another.

### Key Principle

When investigating an issue, always ask:

> "What does this service depend on?"

This simple question often leads to faster diagnosis and more accurate troubleshooting.

---

## Operational Roles

Different organizations may use different job titles, but most IT Operations functions fall into these areas.

### Service Desk

The primary point of contact for users.

Typical responsibilities:

- Receiving tickets
- Answering support requests
- Performing basic troubleshooting
- Escalating issues when necessary

### Desktop Support

Focuses on user devices and endpoint issues.

Typical responsibilities:

- Hardware replacement
- Software installation
- Device troubleshooting
- User assistance

### IT Operations

Maintains day-to-day technology services.

Typical responsibilities:

- Service monitoring
- Incident response
- Operational support
- Maintenance activities

### Systems Administration

Maintains servers, systems, and core infrastructure.

Typical responsibilities:

- System configuration
- Patch management
- Backup management
- Platform maintenance

### Network Operations

Maintains network connectivity and communication services.

Typical responsibilities:

- Network monitoring
- Connectivity troubleshooting
- Equipment management
- Network incident response

### Operations Center

Some organizations use a centralized operations team that monitors services and coordinates operational response activities.

Typical responsibilities:

- Monitoring systems and services
- Responding to alerts
- Coordinating incident response
- Tracking operational health
- Escalating issues to specialized teams

> In smaller organizations, one person may perform several of these roles. In larger organizations, these responsibilities are often divided across multiple teams.

---

## Reactive and Proactive Operations

IT Operations consists of both reactive and proactive work.

### Reactive Operations

Reactive work happens after a problem or request is identified.

Examples:

- Responding to incidents
- Troubleshooting issues
- Restoring service
- Handling escalations
- Supporting users

#### Example

A user reports that an application will not open.

Operations investigates the issue, identifies the cause, applies a fix, verifies functionality, and restores service.

---

### Proactive Operations

Proactive work aims to prevent problems before they occur.

Examples:

- Monitoring systems
- Performing maintenance
- Reviewing recurring incidents
- Updating documentation
- Automating repetitive tasks

#### Example

Operations notices a server repeatedly running low on disk space and resolves the underlying issue before it causes an outage.

---

## Operational Workflow

Most operational work follows the same general process.

```text
Monitor
   ↓
Detect
   ↓
Assess
   ↓
Respond
   ↓
Resolve
   ↓
Verify
   ↓
Document
   ↓
Improve
```

### Monitor

Observe systems, services, and environments.

### Detect

Identify issues, failures, or requests.

### Assess

Determine impact and required action.

### Respond

Take appropriate action.

### Resolve

Restore service or complete the task.

### Verify

Confirm that the issue is resolved or the requested work was completed successfully.

Verification helps prevent premature ticket closure, repeat incidents, and incomplete changes.

### Document

Record what happened and what was done.

### Improve

Identify opportunities to prevent future issues.

### Example

An alert reports a service failure:

1. Monitoring detects the issue.
2. Operations investigates.
3. Service is restored.
4. Functionality is verified.
5. Findings are documented.
6. Preventive improvements are implemented.

---

## Core Principles

### Minimize Downtime

Restore service as quickly and safely as possible.

### Reduce Risk

Avoid unnecessary disruption to users and services.

### Standardize

Consistent processes lead to predictable results.

### Document Work

Important knowledge should not exist only in someone's memory.

### Verify Before Closing

Confirm that the issue is actually resolved.

### Automate Repetitive Tasks

Reduce manual effort where practical.

### Continuously Improve

Learn from mistakes, incidents, and experience.

---

## Common Work Inputs

The majority of operational work originates from a few sources.

### User Requests

Examples:

- Password reset
- Software installation
- Access request

### Incidents

Examples:

- Application outage
- Login issue
- Hardware failure

### Alerts

Examples:

- Service failure
- High resource usage
- Storage warning

### Changes

Examples:

- Software updates
- Configuration changes
- Infrastructure upgrades

### Maintenance Tasks

Examples:

- Patch deployment
- Device replacement
- System cleanup

---

## Common Work Outputs

IT Operations produces outcomes rather than products.

Examples:

- Restored services
- Completed requests
- Updated user access
- Managed assets
- Operational documentation
- Improved processes

### Example

A new employee onboarding request may result in:

- User account creation
- Access assignment
- Laptop deployment
- Asset inventory update
- Documentation update

---

## Success Indicators

Successful IT Operations is measured by results.

### Service Availability

Systems remain accessible and functional.

### Resolution Efficiency

Issues are resolved in a reasonable amount of time.

### Service Quality

Users can perform their work without unnecessary disruption.

### User Satisfaction

Support meets user and business expectations.

### Operational Efficiency

Resources are managed effectively.

### Risk Reduction

Potential issues are identified and addressed before they become major problems.

---

## Operational Mindset

Technology changes quickly, but good operational habits remain the same.

### Be Methodical

Follow a process instead of guessing.

### Avoid Assumptions

Validate information before taking action.

### Verify Findings

Confirm the problem, cause, and solution.

### Prioritize Impact

Focus on what affects the business the most.

### Document Decisions

Ensure others can understand what was done.

### Escalate When Necessary

Know when additional expertise is required.

### Learn Continuously

Every issue is an opportunity to improve.

### Practical Example

A user reports that an application is not working.

Instead of immediately reinstalling the software:

1. Gather information.
2. Identify the symptoms.
3. Review recent changes.
4. Investigate possible causes.
5. Apply the appropriate fix.
6. Verify the result.
7. Document the resolution.

This approach saves time, improves accuracy, and creates knowledge that can be reused in future incidents.

---

# Key Takeaways

- IT Operations keeps technology services running.
- The focus is on availability, reliability, stability, and support.
- Operations includes both reactive and proactive work.
- Most operational activities follow a common lifecycle.
- Services depend on other systems and components.
- Documentation, standardization, verification, and continuous improvement are essential habits.
- Successful IT Operations is measured by service outcomes, not tools.
- A structured troubleshooting mindset is often more valuable than knowing a specific product or platform.
