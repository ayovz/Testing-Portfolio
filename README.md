# 🧪 Testing Portfolio — Ayomal Weerasinghe

![Playwright](https://img.shields.io/badge/Playwright-1.42-45ba4b?logo=playwright)
![Cypress](https://img.shields.io/badge/Cypress-13.0-69D3A7?logo=cypress)
![JUnit](https://img.shields.io/badge/JUnit-5.10-25A162?logo=junit5)
![pytest](https://img.shields.io/badge/pytest-8.1-0A9EDC?logo=pytest)
![TypeScript](https://img.shields.io/badge/TypeScript-5.0-3178c6?logo=typescript)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6-F7DF1E?logo=javascript)
![Java](https://img.shields.io/badge/Java-17-ED8B00?logo=openjdk)
![Python](https://img.shields.io/badge/Python-3.11-3776AB?logo=python)
![License](https://img.shields.io/badge/license-MIT-blue)

> A structured QA automation portfolio demonstrating proficiency across
> **5 testing tools**, **4 programming languages**, and **146 test cases** —
> covering E2E testing, form validation, REST API testing, data quality
> validation, and AI output quality assurance.

---

## 📦 Portfolio Overview

| # | Project | Tool | Language | Tests | Domain | Repo |
|---|---------|------|----------|-------|--------|------|
| 1 | PageGuard | Playwright | TypeScript | 42 | Website health monitoring | [→ github.com/ayovz/PageGuard](https://github.com/ayovz/PageGuard) |
| 2 | FormSentry | Cypress | JavaScript | 18 | Form validation testing | [→ github.com/ayovz/FormSentry](https://github.com/ayovz/FormSentry) |
| 3 | ApiSentinel | JUnit 5 | Java | 24 | REST API testing | [→ github.com/ayovz/ApiSentinel](https://github.com/ayovz/ApiSentinel) |
| 4 | DataValidator | pytest | Python | 39 | CSV data quality | [→ github.com/ayovz/DataValidator](https://github.com/ayovz/DataValidator) |
| 5 | AIOutputGuard | Playwright | TypeScript | 23 | AI output validation | [→ github.com/ayovz/AIOutputGuard](https://github.com/ayovz/AIOutputGuard) |

**Total: 5 projects · 5 tools · 4 languages · 146 test cases**

---

---

## 🛠 Projects

---

### 1. PageGuard — Playwright
**🔗 [github.com/ayovz/PageGuard](https://github.com/ayovz/PageGuard)**

Automated website health monitoring suite that verifies availability,
page titles, DOM element rendering, load performance, and console
errors across 5 live websites — with daily scheduled runs via GitHub Actions CI.

```
✅ HTTPBin              ⚡ 400ms   HTTP 200
✅ Wikipedia            ⚡ 986ms   HTTP 200
✅ npm Registry         🟡 3207ms  HTTP 200
✅ MDN Web Docs         ⚡ 1298ms  HTTP 200
✅ Playwright Docs      ⚡ 2851ms  HTTP 200
```

**Key techniques:**
- Multi-browser testing (Chromium + Firefox)
- Performance threshold assertions
- Console error monitoring
- GitHub Actions scheduled daily runs

**Run:**
```bash
cd 01_PageGuard_Playwright
npm install && npx playwright install
npm test
```

---

### 2. FormSentry — Cypress
**🔗 [github.com/ayovz/FormSentry](https://github.com/ayovz/FormSentry)**

Form validation test suite covering field visibility, email format
validation, empty submission handling, boundary conditions, and
output verification against a real web form interface.

```
✓ should reject email without @ symbol
✓ should reject email without domain
✓ should display submitted name correctly in output
✓ should allow form to be cleared and resubmitted
18 passing (14.2s)
```

**Key techniques:**
- Equivalence partitioning on email validation
- Boundary value analysis on input fields
- Custom Cypress commands (`cy.fillForm`, `cy.submitAndVerify`)
- Third-party error suppression in `uncaught:exception`

**Run:**
```bash
cd 02_FormSentry_Cypress
npm install
npm test
```

---

### 3. ApiSentinel — JUnit 5
**🔗 [github.com/ayovz/ApiSentinel](https://github.com/ayovz/ApiSentinel)**

Comprehensive REST API test suite using Java 17's built-in HttpClient —
no external HTTP libraries. Validates status codes, response structure,
data types, CRUD operations, and boundary values against a live API.

```
✅ GET  /posts           5 tests
✅ GET  /posts/{id}      5 tests  (BVA: IDs 1, 50, 100, 9999)
✅ GET  /posts/comments  3 tests
✅ POST /posts           3 tests
✅ DELETE /posts/{id}    2 tests
✅ Data Type Validation  3 tests
✅ GET  /users           3 tests
Total: 24 tests | 0 failed
```

**Key techniques:**
- JUnit 5 `@Nested` class organisation
- Boundary value analysis on resource IDs (1, 50, 100, 9999)
- Data type validation (`Integer` vs `String`)
- Java 17 built-in `HttpClient` — zero HTTP dependencies

**Run:**
```bash
cd 03_ApiSentinel_JUnit
mvn test
```

---

### 4. DataValidator — pytest
**🔗 [github.com/ayovz/DataValidator](https://github.com/ayovz/DataValidator)**

CSV data quality validation suite with a dual-dataset approach —
a clean dataset that should pass all tests, and a dirty dataset with
8 intentional errors that should be detected. 39 tests across 8
validation suites.

```
TestSchemaValidation        ✅  5 passed
TestNullValues              ✅  6 passed
TestDuplicates              ✅  5 passed
TestValueRanges             ✅  7 passed
TestFormatValidation        ✅  6 passed
TestReferentialIntegrity    ✅  3 passed
TestCalculatedFields        ✅  4 passed
TestStatisticalChecks       ✅  3 passed

======================== 39 passed in 1.11s ============================
```

**Key techniques:**
- Dual-dataset testing (clean + dirty)
- pandas vectorised validation operations
- pytest `scope="session"` fixtures
- Statistical outlier detection with mean/std

**Run:**
```bash
cd 04_DataValidator_pytest
pip install -r requirements.txt
python -m pytest
```

---

### 5. AIOutputGuard — Playwright
**🔗 [github.com/ayovz/AIOutputGuard](https://github.com/ayovz/AIOutputGuard)**

The most original project. Validates AI output quality using the same
failure patterns encountered in real prompt engineering workflows —
empty outputs, truncated content, wrong data types, placeholder text,
inconsistency across calls, and delivery failures.

```
✓ response body is not empty
✓ response is valid JSON — not malformed output
✓ title meets minimum length threshold
✓ body does not exceed maximum length threshold
✓ output does not contain placeholder text
✓ same request returns consistent structure across calls
23 passed (8.4s)
```

**Key techniques:**
- Configurable `QUALITY_RULES` threshold object
- Placeholder text pattern detection
- Cross-call consistency validation
- Directly applicable to LLM API output validation

**Run:**
```bash
cd 05_AIOutputGuard_Playwright
npm install && npx playwright install chromium
npm test
```

---

## 🧪 Test Design Methodology

All projects apply formal software testing methodologies:

### Equivalence Partitioning
Used in FormSentry and DataValidator to divide inputs into valid/invalid
classes. Example: email validation tests one representative from each
partition (valid, missing @, missing domain, missing local part).

### Boundary Value Analysis
Used in ApiSentinel (IDs: 1, 50, 100, 9999) and DataValidator
(age: 17, 18, 65, 66) to test at and around boundary conditions
where failures are most likely to occur.

### Dual-Dataset Testing
Used in DataValidator — both a clean dataset (all tests pass) and a
dirty dataset (specific failures detected). Proves the validator
catches real issues, not just that valid data passes.

### Negative Testing
Every project includes tests that verify failure cases are correctly
detected — not just that valid inputs succeed.

---

## 🤖 CI/CD Integration

All 5 projects include GitHub Actions workflows running on every push,
pull request, and on a daily schedule:

| Project | Repo | Schedule |
|---------|------|----------|
| PageGuard | [github.com/ayovz/PageGuard](https://github.com/ayovz/PageGuard) | Daily 8AM UTC |
| FormSentry | [github.com/ayovz/FormSentry](https://github.com/ayovz/FormSentry) | Daily 9AM UTC |
| ApiSentinel | [github.com/ayovz/ApiSentinel](https://github.com/ayovz/ApiSentinel) | Daily 10AM UTC |
| DataValidator | [github.com/ayovz/DataValidator](https://github.com/ayovz/DataValidator) | Daily 11AM UTC |
| AIOutputGuard | [github.com/ayovz/AIOutputGuard](https://github.com/ayovz/AIOutputGuard) | Daily 12PM UTC |

---

## 📊 Portfolio Stats

```
Total test cases:     146
Total test suites:    35
Languages used:       4  (TypeScript, JavaScript, Java, Python)
Frameworks used:      5  (Playwright, Cypress, JUnit 5, pytest, Maven)
CI/CD pipelines:      5  (GitHub Actions — daily automated runs)
```

---

## 🔗 All Repos

| Project | Repository |
|---------|-----------|
| 🧪 This Portfolio | [github.com/ayovz/testing-portfolio](https://github.com/ayovz/testing-portfolio) |
| 🛡️ PageGuard | [github.com/ayovz/PageGuard](https://github.com/ayovz/PageGuard) |
| 🛡️ FormSentry | [github.com/ayovz/FormSentry](https://github.com/ayovz/FormSentry) |
| ⚔️ ApiSentinel | [github.com/ayovz/ApiSentinel](https://github.com/ayovz/ApiSentinel) |
| 📊 DataValidator | [github.com/ayovz/DataValidator](https://github.com/ayovz/DataValidator) |
| 🤖 AIOutputGuard | [github.com/ayovz/AIOutputGuard](https://github.com/ayovz/AIOutputGuard) |

---

## 👤 Author

**Ayomal Weerasinghe**
Final-year IT Undergraduate, SLIIT
Colombo, Sri Lanka

📧 pasinduayomal2001@gmail.com
🔗 [linkedin.com/in/ayomalwee](https://linkedin.com/in/ayomalwee)
💻 [github.com/ayovz](https://github.com/ayovz)

---

## 📄 License

MIT — free to use, modify, and distribute.
