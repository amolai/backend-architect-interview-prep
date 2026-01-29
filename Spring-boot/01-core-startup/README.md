# Spring Boot Core & Startup

## Key Concepts (with explanations)

### 1. SpringApplication Bootstrapping
`SpringApplication` is the **entry point abstraction** that bootstraps a Spring Boot application.
It coordinates:
- environment loading (properties, profiles)
- logging setup
- application context creation
- lifecycle event publishing
- triggering auto-configuration
- embedded server startup

At Staff/Principal level, this is important because it defines **where customization hooks exist** and **where startup failures originate**.

---

### 2. Startup Lifecycle
Spring Boot startup is a **deterministic, multiphase process**, not a black box.

High-level phases:
1. Environment preparation
2. ApplicationContext creation
3. Auto-configuration evaluation
4. Bean definition registration
5. Bean instantiation & dependency injection
6. Embedded server startup
7. Application lifecycle events

Understanding this lifecycle allows you to:
- reason about startup time
- place initialization logic correctly
- debug failures before traffic is served

---

### 3. Embedded Server Model
Spring Boot embeds the web server (Tomcat, Jetty, Netty) **inside the application process**.

This shifts responsibility from the platform to the application:
- server versioning is application-controlled
- configuration is code-driven
- deployment becomes a single artifact

This model improves portability and consistency but reduces centralized server governance.

---

### 4. ApplicationContext vs WebApplicationContext
`ApplicationContext` is the core Spring container.
`WebApplicationContext` extends it with:
- servlet context awareness
- request/session scopes
- web-specific infrastructure beans

Understanding the distinction is critical when diagnosing:
- bean scope issues
- startup failures in web apps
- request lifecycle problems

---

### 5. Startup Performance
Startup time is influenced by:
- classpath size
- number of auto-configurations
- bean count
- proxy creation
- eager initialization logic

At scale, startup performance impacts:
- deployment speed
- autoscaling responsiveness
- incident recovery time

This is why startup optimization is a **production concern**, not just developer convenience.

---

## Interview Questions

### Q1. Walk through the Spring Boot startup lifecycle.
**Good Answer**  
`SpringApplication.run()` triggers environment preparation, creates the
ApplicationContext, evaluates auto-configurations, instantiates beans,
starts the embedded server, and finally publishes ApplicationReady events.

**Bad Answers**
- “Spring scans everything and starts”
- “Boot magically creates beans”

**What Interviewers Listen For**
- Clear sequence
- Awareness of expensive phases

**Follow-ups**
- Which phase slows down large applications?
- Where are conditions evaluated?

---

### Q2. What responsibilities does `SpringApplication` handle?
**Good Answer**  
It loads environment properties, configures logging, creates the application
context, publishes lifecycle events, applies auto-configuration, and starts
the embedded server.

**Bad Answers**
- “It just starts the app”

**What Interviewers Listen For**
- Separation of responsibilities

**Follow-ups**
- How do you customize `SpringApplication`?
- What hooks does it provide?

---

### Q3. Why does Spring Boot startup time increase as applications grow?
**Good Answer**  
Classpath scanning, conditional checks, bean creation, proxying, and
auto-configuration evaluation scale with dependency and bean count.

**Bad Answers**
- “Spring is slow”
- “Java is slow”

**What Interviewers Listen For**
- Systems-level thinking

**Follow-ups**
- Which parts scale linearly vs worse?
- How do starters affect this?

---

### Q4. How do you analyze slow Spring Boot startup?
**Good Answer**  
Enable startup metrics, inspect condition evaluation reports, use profiling,
enable lazy initialization, and remove unused auto-configurations.

**Bad Answers**
- “Increase heap size”
- “Add more CPUs”

**What Interviewers Listen For**
- Diagnostic mindset

**Follow-ups**
- When does lazy initialization hurt?
- How do you detect unused beans?

---

### Q5. Embedded server vs external server – trade-offs?
**Good Answer**  
Embedded servers simplify deployment, version consistency, and testing.
External servers offer centralized control but increase operational coupling.

**Bad Answers**
- “Embedded is always better”
- “External servers are outdated”

**What Interviewers Listen For**
- Trade-off reasoning

**Follow-ups**
- When would embedded servers be problematic?
- How does this affect observability?

---

### Q6. When does an embedded server become a problem?
**Good Answer**  
When centralized governance, shared tuning, or platform-level controls are
required across many applications.

**Bad Answers**
- “Never, embedded is best”

**What Interviewers Listen For**
- Platform-awareness

---

### Q7. Difference between ApplicationContext and WebApplicationContext?
**Good Answer**  
WebApplicationContext extends ApplicationContext with web-specific features
like servlet context and request scopes.

**Bad Answers**
- “They are the same”

**What Interviewers Listen For**
- Context hierarchy understanding

---

### Q8. What is ApplicationReadyEvent used for?
**Good Answer**  
To execute logic after the application is fully initialized and ready to
serve traffic.

**Bad Answers**
- “For startup logging”

**What Interviewers Listen For**
- Lifecycle awareness

---

### Q9. How does classpath size affect startup?
**Good Answer**  
More dependencies increase scanning time, conditional checks, and
auto-configuration evaluation.

**Bad Answers**
- “Classpath doesn’t matter”

**What Interviewers Listen For**
- Dependency hygiene awareness

---

### Q10. How do you design Spring Boot apps for fast cold starts?
**Good Answer**  
Reduce dependencies, enable lazy initialization, avoid heavy startup logic,
and trim auto-configurations.

**Bad Answers**
- “Add more memory”

**What Interviewers Listen For**
- Cold-start optimization thinking
