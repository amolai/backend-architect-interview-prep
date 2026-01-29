# Spring Boot Auto-Configuration

## Key Concepts (with explanations)

### 1. Auto-Configuration Philosophy
Auto-configuration provides defaults **without removing control**.  
It is designed to be:
- conditional
- overrideable
- non-invasive

At senior levels, you must treat auto-config as **framework code you are implicitly running**.

---

### 2. Conditional Guards
Auto-config is protected using conditional annotations so that it activates
**only when appropriate**, preventing accidental behavior.

---

### 3. Starters & Classpath-Driven Behavior
Starters influence runtime behavior indirectly.
Adding a dependency can **change how your app behaves**, not just what it can compile.

---

## Interview Questions

### Q1. What is Spring Boot auto-configuration?
**Good Answer**  
Auto-configuration conditionally creates beans based on classpath presence,
configuration properties, and existing beans.

**Bad Answers**
- “Boot creates everything automatically”

**What Interviewers Listen For**
- Understanding of conditions and safety

**Follow-ups**
- Why is it considered safe?
- How does Boot avoid overriding user beans?

---

### Q2. Why is `@ConditionalOnMissingBean` critical?
**Good Answer**  
It ensures user-defined beans always override defaults, preserving extensibility.

**Bad Answers**
- “So Boot doesn’t break”

**Listen For**
- Framework extensibility awareness

---

### Q3. Role of starter dependencies?
**Good Answer**  
Starters pull curated dependency sets that activate auto-configurations
implicitly through classpath inspection.

**Bad Answers**
- “They save us from writing dependencies”

---

### Q4. Overriding beans vs excluding auto-config?
**Good Answer**  
Overriding beans is safer. Exclusions tightly couple applications to Boot internals.

**Bad Answers**
- “I always exclude unused auto-configs”

---

### Q5. What is `spring.factories` / `AutoConfiguration.imports`?
**Good Answer**  
Metadata files listing auto-configuration classes loaded during startup.

**Bad Answers**
- “Some internal Boot file”

---

### Q6. How do you debug unexpected auto-configuration?
**Good Answer**  
Enable debug logs, inspect condition evaluation reports, and trace which
conditions matched.

**Bad Answers**
- “Trial and error”

---

### Q7. How does auto-configuration impact startup time?
**Good Answer**  
Each auto-config adds conditional checks and potential bean creation,
increasing startup cost.

**Bad Answers**
- “It doesn’t matter”

---

### Q8. Rules for writing custom auto-configuration?
**Good Answer**  
Always use conditions, never assume presence, and allow overriding.

**Bad Answers**
- “Just define beans”

---

### Q9. Common auto-config anti-patterns?
**Good Answer**  
Eager initialization, ignoring conditions, heavy logic in constructors.

---

### Q10. How do you safely upgrade Spring Boot?
**Good Answer**  
Review auto-config changes, avoid exclusions, rely on overrideable beans,
and test startup logs.

**Bad Answers**
- “Upgrade and fix errors later”
