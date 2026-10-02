# Service Management

## What Is Service Management

Service Management is the practice of keeping technology services working for the people who use them.

The focus is not the server, application, network device, or tool.

The focus is the service.

If users can do their work, the service is working.

If users cannot do their work, something within the service needs attention.

### Examples

Services people use every day:

- Email
- File storage
- VPN access
- Collaboration tools
- Internal applications
- Customer-facing applications

---

## Why Services Matter

Technology exists to provide services.

Most users do not care how a service works behind the scenes.

They care about whether they can:

- Access it
- Use it
- Complete their work

### Examples

| Service | What Users Experience |
|----------|----------|
| Email | Sending and receiving messages |
| VPN | Accessing company resources remotely |
| File Storage | Opening and saving files |
| Authentication | Signing in to applications |
| Business Applications | Performing daily tasks |

When a service becomes unavailable, work is interrupted.

---

## Types of Services

Understanding service types helps identify where a problem may exist.

### User Services

Services directly used by people.

Examples:

- Email
- File sharing
- Chat platforms
- Business applications
- VPN access

---

### Supporting Services

Services that help other services function.

Examples:

- Authentication
- DNS
- Databases
- Storage platforms

Users may never interact with these directly, but many services depend on them.

---

### Infrastructure Services

The foundation that supports everything else.

Examples:

- Servers
- Virtual machines
- Cloud resources
- Networks
- Power systems

---

### Key Idea

Users usually notice failures in user services.

The actual problem often exists in a supporting service or infrastructure service.

---

## What Makes Up a Service

Most services are made up of multiple components.

```text
Users
   ↓
Service
   ↓
Supporting Services
   ↓
Systems
   ↓
Network
   ↓
Power
```

A problem at a lower layer can affect everything above it.

### Example

Users cannot access email.

Possible causes:

- Email application issue
- Authentication issue
- Server issue
- Network issue
- Power issue

The symptom is the same.

The root cause may be somewhere else in the chain.

---

## Service Ownership

Every service should have someone responsible for it.

That person or team helps ensure the service remains available, maintained, and supported.

Typical responsibilities include:

- Monitoring service health
- Coordinating support
- Managing maintenance
- Communicating issues
- Identifying improvements

### Example

An email service may involve:

- Support teams
- System administrators
- Network teams

Many people may support the service, but responsibility should still be clear.

---

## Service Lifecycle

Services change over time.

Most services follow a simple lifecycle.

```text
Plan
   ↓
Deploy
   ↓
Operate
   ↓
Maintain
   ↓
Improve
   ↓
Retire
```

### Plan

Identify what users need.

### Deploy

Make the service available.

### Operate

Support users and keep the service running.

### Maintain

Keep the service working.

### Improve

Make the service more reliable, useful, or efficient.

### Retire

Remove or replace the service when it is no longer needed.

### Example

A company introduces a new file-sharing platform.

1. A need is identified.
2. The platform is deployed.
3. Users begin using it.
4. Maintenance is performed.
5. Improvements are made.
6. The platform is eventually replaced.

---

## Service Availability

Availability answers a simple question:

> Can users use the service right now?

If users cannot access the service, the service is unavailable.

Common causes include:

- Application failures
- Authentication failures
- Network problems
- System outages
- Poorly planned changes

### Key Idea

Availability should be viewed from the user's perspective.

A server being online does not guarantee that users can actually use the service.

---

## Service Health

Availability alone does not tell the whole story.

A service can be online and still have problems.

A healthy service is:

- Available
- Reliable
- Responsive
- Stable
- Easy to support

### Example

An application loads so slowly that users cannot perform their work efficiently.

The application is online.

The service is not healthy.

---

## Service Health Checklist

When reviewing a service, ask:

### Can users access it?

- Can users sign in?
- Can users connect?
- Are core features available?

### Can users use it?

- Can users complete their tasks?
- Are important functions working?

### Is it fast enough?

- Is it responding normally?
- Are users experiencing delays?

### Is it failing repeatedly?

- Are the same issues returning?
- Are incidents becoming more frequent?

### Are supporting services healthy?

- Is authentication working?
- Is DNS working?
- Is storage working?
- Is the network healthy?

### Can it be supported?

- Is monitoring available?
- Is documentation available?
- Can issues be investigated effectively?

### Service Health Rule

A service is not healthy simply because it is online.

A service is healthy when users can access it, use it, and complete their work without significant issues.

---

## Service Support

Services require ongoing support.

Common support activities include:

- Checking service status
- Investigating problems
- Restoring functionality
- Performing maintenance
- Communicating issues
- Verifying fixes

### Example

Users report that an application is unavailable.

A typical response might be:

1. Confirm the issue.
2. Determine who is affected.
3. Find the cause.
4. Restore service.
5. Verify functionality.
6. Document the outcome.

---

## Service Dependencies

Services rarely work alone.

Most services depend on other services.

Example:

```text
Email
   ↓
Authentication
   ↓
Network
   ↓
Power
```

A failure lower in the chain can affect everything above it.

Understanding dependencies helps you:

- Troubleshoot faster
- Identify likely causes
- Understand impact
- Reduce downtime

### Key Question

When a service fails, ask:

> What does this service depend on?

---

## Service Perspective

Users see the service.

IT sees the components behind it.

### Example

A user reports:

> "I can't log in."

Possible causes:

- Account issue
- Authentication issue
- Application issue
- Network issue
- Server issue

The user's symptom is real.

The actual cause may exist somewhere else.

This mindset helps avoid focusing only on the visible problem.

---

## Service Improvement

Keeping a service running is only part of the job.

Services should improve over time.

Common improvement areas include:

- Reliability
- Availability
- Performance
- User experience
- Documentation
- Support processes

### Example

Users experience repeated login problems.

Instead of fixing each incident individually, the underlying cause is identified and corrected.

The goal is fewer future incidents.

---

## Measuring Success

A service is usually doing well when:

- Users can work without interruption.
- Outages are rare.
- Performance is stable.
- Issues are resolved quickly.
- The same problems are not constantly returning.
- Users rarely need support for routine tasks.

### Example

A good month might look like:

- Few service disruptions
- Stable performance
- Minimal recurring issues
- Successful maintenance work
- Positive user experience

---

## Operational Mindset

Good Service Management focuses on the user experience, not individual components.

Instead of asking:

> "Is the server running?"

Ask:

> "Can users successfully use the service?"

Focus on:

- User impact
- Availability
- Reliability
- Dependencies
- Continuous improvement

Technology is important.

The service is what matters.

---

# Key Takeaways

- Services are the reason technology exists.
- Users care about the service, not the underlying components.
- Most services depend on other services and infrastructure.
- Availability and health are not the same thing.
- Understanding dependencies helps troubleshoot issues faster.
- A service should be evaluated from the user's perspective.
- Good Service Management focuses on keeping services usable, reliable, and supportable.
- Continuous improvement helps reduce future issues and improve the user experience.
