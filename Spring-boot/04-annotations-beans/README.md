# Annotations & Bean Lifecycle

## Key Concepts (with explanations)

### 1. Stereotype Annotations
They convey intent and affect exception handling.

---

### 2. @Configuration & Proxying
Ensures singleton behavior across @Bean methods.

---

### 3. Lifecycle & Proxy Side Effects
Proxying affects transactions and equality.

---

## Interview Questions

### Q1. @Component vs @Service vs @Repository?
**Good Answer**  
Semantic roles; @Repository enables exception translation.

---

### Q2. @Configuration vs @Component?
**Good Answer**  
@Configuration proxies @Bean methods.

---

### Q3. Why are @Bean methods proxied?
**Good Answer**  
To ensure consistent singleton instances.

---

### Q4. When does @Lazy help or hurt?
**Good Answer**  
Helps startup; hurts error visibility.

---

### Q5. Bean lifecycle callbacks?
**Good Answer**  
@PostConstruct, @PreDestroy, InitializingBean.

---

### Q6. Constructor vs field injection?
**Good Answer**  
Constructor injection improves immutability and testability.

---

### Q7. Circular dependency handling?
**Good Answer**  
Spring resolves some via early references; constructor cycles fail.

---

### Q8. @Primary vs @Qualifier?
**Good Answer**  
@Primary sets default; @Qualifier is explicit.

---

### Q9. Proxy impact on equals/hashCode?
**Good Answer**  
Proxies can break equality assumptions.

---

### Q10. Annotation misuse patterns?
**Good Answer**  
Overusing stereotypes, hiding logic in annotations.
