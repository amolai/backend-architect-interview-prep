# Configuration & Profiles

## Key Concepts (with explanations)

### 1. Externalized Configuration
Separates binaries from environments to support immutable deployments.

---

### 2. Property Precedence
Defines predictable override behavior across environments.

---

### 3. Profiles at Scale
Profiles activate code paths; misuse leads to configuration chaos.

---

## Interview Questions

### Q1. Explain property precedence in Spring Boot.
**Good Answer**  
Command-line args → env vars → config files → defaults.

**Bad Answers**
- “application.yml overrides everything”

---

### Q2. Why externalized configuration?
**Good Answer**  
Enables environment portability and safe deployments.

**Bad Answers**
- “For convenience”

---

### Q3. How do profiles work internally?
**Good Answer**  
They conditionally activate bean definitions and configuration blocks.

---

### Q4. When do profiles become an anti-pattern?
**Good Answer**  
When overused, causing configuration sprawl and unclear behavior.

---

### Q5. Profiles vs feature flags?
**Good Answer**  
Profiles are coarse-grained; feature flags allow runtime control.

---

### Q6. Managing config across many environments?
**Good Answer**  
Centralized config management with minimal profile variance.

---

### Q7. Secrets handling best practices?
**Good Answer**  
Inject via environment or secret stores, never in config files.

---

### Q8. application.yml vs application.properties?
**Good Answer**  
YAML supports structure; properties are simpler and less error-prone.

---

### Q9. How do you validate configuration at startup?
**Good Answer**  
Using configuration properties binding and validation.

---

### Q10. Common configuration mistakes?
**Good Answer**  
Hardcoding values, excessive profiles, unclear precedence.
