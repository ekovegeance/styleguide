# Commenting Practices

Effective commenting is an essential practice in software development to ensure code clarity, maintainability, and collaboration among developers. This document outlines rules and best practices for writing comments in codebases.

## 1. General Guidelines

- **Keep It Relevant:** Comments should explain the "why" behind code, not the "what" if the code is self-explanatory.
- **Be Concise:** Write clear and concise comments that are easy to understand.
- **Use Proper Grammar:** Maintain professionalism by using correct spelling, grammar, and punctuation.
- **Update Comments:** Always update or remove outdated comments when modifying the associated code.

---

## 2. Types of Comments

### 2.1. Single-Line Comments

- Use for brief explanations or notes.

```javascript
// Check if the user is authenticated
if (!user.isAuthenticated) redirectToLogin();
```

### 2.2. Multi-Line Comments

- Use for detailed explanations or documentation.

```javascript
/*
 * This function calculates the factorial of a number.
 * It uses a recursive approach to multiply all positive integers up to the given number.
 */
function factorial(n) {
    if (n <= 1) return 1;
    return n * factorial(n - 1);
}
```

### 2.3. Documentation Comments

- Use for functions, classes, and modules with standardized tags like `@param` and `@return`.

```javascript
/**
 * Calculates the sum of two numbers.
 * @param {number} a - The first number.
 * @param {number} b - The second number.
 * @return {number} The sum of the two numbers.
 */
function add(a, b) {
    return a + b;
}
```

---

## 3. Writing Effective Comments

### 3.1. Explain Complex Logic

- Use comments to clarify non-obvious logic or algorithms.

```python
# Use binary search to improve performance on sorted data
while left <= right:
    mid = (left + right) // 2
    if data[mid] == target:
        return mid
```

### 3.2. Highlight Important Decisions

- Provide context for design choices, trade-offs, or deviations from standard practices.

```java
// Using a LinkedHashMap to maintain insertion order for predictable iteration
Map<String, String> map = new LinkedHashMap<>();
```

### 3.3. Warn About Side Effects or Limitations

- Alert developers to potential issues or constraints.

```php
// This function assumes $array is sorted; behavior is undefined otherwise.
function binarySearch($array, $key) {
    // ... implementation ...
}
```

---

## 4. Avoiding Common Mistakes

### 4.1. Avoid Redundant Comments

- Do not repeat information already evident from the code.

```c++
// BAD: Adds two numbers
int sum = a + b;

// GOOD: Add numbers to calculate the total expense
int totalExpense = foodCost + transportCost;
```

### 4.2. Avoid Hard-Coding Comments

- Do not include static values that may change.

```ruby
# BAD: Set the timeout to 5000ms
config.timeout = 5000;

# GOOD: Set the timeout for the network request
config.timeout = NETWORK_TIMEOUT;
```

---

## 5. Tools and Conventions

- **Use Linters:** Enforce commenting standards using tools like ESLint, Pylint, or JSDoc.
- **Follow Style Guides:** Adhere to project-specific or language-specific guidelines, such as Google Style Guide or PEP 8.
- **Automate Documentation:** Use tools like JSDoc, Sphinx, or Doxygen to generate documentation from comments.

---

## 6. Commenting for Collaboration

- Encourage team members to leave meaningful comments during code reviews.
- Use TODOs and FIXMEs to track unfinished work.

```typescript
// TODO: Implement error handling for API requests
fetchData();

// FIXME: Resolve memory leak issue in the caching mechanism
cache.clear();
```

