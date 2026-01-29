# Actuator & Production Readiness

## Key Concepts (with explanations)

### 1. Actuator Philosophy
Expose operational insight without custom tooling.

---

### 2. Health & Readiness
Protects deployments and traffic routing.

---

## Interview Questions

### Q1. What is Spring Boot Actuator?
**Good Answer**  
Provides production-ready endpoints for health and metrics.

---

### Q2. Liveness vs readiness?
**Good Answer**  
Liveness checks process health; readiness checks traffic readiness.

---

### Q3. Why readiness matters?
**Good Answer**  
Prevents traffic to unready instances.

---

### Q4. Securing actuator endpoints?
**Good Answer**  
Restrict exposure and protect with auth.

---

### Q5. Custom health indicators?
**Good Answer**  
Expose dependency health explicitly.

---

### Q6. Actuator in multi-tenant apps?
**Good Answer**  
Avoid tenant data leakage.

---

### Q7. Metrics vs logs?
**Good Answer**  
Metrics show trends; logs show context.

---

### Q8. Startup vs runtime health?
**Good Answer**  
Startup readiness differs from runtime health.

---

### Q9. Disabling endpoints?
**Good Answer**  
Reduce attack surface.

---

### Q10. Actuator production pitfalls?
**Good Answer**  
Overexposure and noisy metrics.
