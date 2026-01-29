# Spring Data JPA (Boot Context)

## Key Concepts (with explanations)

### 1. Repository Auto-Configuration
Repositories are proxies created at runtime.

---

### 2. Defaults & Hidden Costs
Boot defaults simplify setup but hide performance risks.

---

### 3. Persistence Context
Large contexts increase memory and CPU usage.

---

## Interview Questions

### Q1. How does Boot auto-configure JPA?
**Good Answer**  
Detects JPA and configures DataSource, EntityManager, repositories.

---

### Q2. Defaults Boot applies to Hibernate?
**Good Answer**  
Dialect inference, transaction integration, optional DDL auto.

---

### Q3. Why is JPA risky at scale?
**Good Answer**  
Hidden lazy loading, N+1 queries, large persistence contexts.

---

### Q4. N+1 problem causes & fixes?
**Good Answer**  
Lazy loading in loops; fix with fetch joins or DTOs.

---

### Q5. Persistence context pitfalls?
**Good Answer**  
Memory leaks and delayed writes.

---

### Q6. @Transactional behavior in Boot?
**Good Answer**  
Proxy-based AOP manages transaction boundaries.

---

### Q7. Why internal calls break transactions?
**Good Answer**  
Internal calls bypass proxies.

---

### Q8. Pagination pitfalls?
**Good Answer**  
Offset-based pagination degrades at scale.

---

### Q9. When to avoid JPA?
**Good Answer**  
High-write or reporting-heavy workloads.

---

### Q10. Repository abstraction trade-offs?
**Good Answer**  
Productivity vs performance transparency.
