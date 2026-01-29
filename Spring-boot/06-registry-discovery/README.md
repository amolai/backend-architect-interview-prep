# Registry & Discovery

## Key Concepts (with explanations)

### 1. Service Discovery
Dynamic resolution of service instances.

---

### 2. Boot vs Platform Responsibility
Discovery may be redundant on modern platforms.

---

## Interview Questions

### Q1. What is service discovery?
**Good Answer**  
Dynamic lookup of service instances at runtime.

---

### Q2. How does Boot integrate with registries?
**Good Answer**  
Via Spring Cloud abstractions during startup.

---

### Q3. Client-side vs server-side discovery?
**Good Answer**  
Client-side gives control; server-side simplifies clients.

---

### Q4. When is discovery unnecessary?
**Good Answer**  
When platform provides DNS-based resolution.

---

### Q5. Boot vs platform ownership?
**Good Answer**  
Prefer platform-managed discovery.

---

### Q6. Startup failures & discovery?
**Good Answer**  
Failure to register should fail fast.

---

### Q7. Health propagation?
**Good Answer**  
Health affects registration visibility.

---

### Q8. Why Eureka is often removed?
**Good Answer**  
Redundant with platform capabilities.

---

### Q9. Discovery in monorepos?
**Good Answer**  
Often unnecessary due to local wiring.

---

### Q10. Discovery anti-patterns?
**Good Answer**  
Overusing discovery for static services.
