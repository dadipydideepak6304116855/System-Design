# 🚀 CI/CD in System Design

---

## 🔹 What is CI/CD?

**CI/CD** stands for:

- **CI – Continuous Integration**
- **CD – Continuous Delivery** or **Continuous Deployment**

CI/CD is a **DevOps practice** that automates the process of **building, testing, and deploying** code to ensure **faster and more reliable software delivery**.

---

## 🔹 Breakdown of CI/CD

### ✅ Continuous Integration (CI)

- Developers frequently push code to a shared repo (e.g., GitHub)
- Every commit triggers an **automated build + test pipeline**
- Helps detect bugs early, ensures team integration

**Goals:**
- Catch issues early
- Automated testing
- Fast feedback loop

### ✅ Continuous Delivery (CD)

- Builds on CI
- Ensures code is always in a **deployable state**
- **Manual trigger** to deploy to production or staging

**Goals:**
- Release-ready code at any time
- Automate everything except the deploy decision

### ✅ Continuous Deployment (CD)

- Fully automated end-to-end deployment to production
- Every code change that passes tests gets deployed automatically

**Goals:**
- Zero manual intervention
- Faster release cycles

---

## 🔹 CI/CD Pipeline Example

```plaintext
Developer Pushes Code
        ↓
  CI Pipeline Starts
        ↓
  1. Build the project
  2. Run unit/integration tests
  3. Run code quality checks
        ↓
   CD Pipeline Starts
  4. Deploy to staging
  5. Run E2E tests
  6. (Optional: Manual approval)
  7. Deploy to production

