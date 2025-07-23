
# 🔄 Rolling Deployments

## ✅ What is a Rolling Deployment?

**Rolling Deployment** is a software release strategy where **application updates are deployed incrementally**, one server or instance at a time, **without downtime**.

Instead of taking down the whole application, only a **subset of instances** are updated while the rest continue serving users.

---

## 🚀 How It Works

1. Divide your application instances (pods, VMs, containers) into small batches.
2. Replace each batch with the **new version**, while others continue running the old one.
3. Monitor health checks for each batch.
4. Continue rolling forward until **all instances** are running the new version.

---

## 🧱 Example (With 4 Instances)

| Step | Version Running           |
|------|----------------------------|
| 1    | A A A A                    |
| 2    | A A A **B**                |
| 3    | A A **B B**                |
| 4    | A **B B B**                |
| 5    | **B B B B** (complete)     |

- A = Old version  
- B = New version

---

## 📦 Tools That Support Rolling Deployments

- **Kubernetes** (rolling updates for Deployments)
- **AWS ECS / Elastic Beanstalk**
- **Spinnaker**
- **Argo CD**
- **Jenkins pipelines**

---

## ✅ Benefits

- 🔄 **Zero downtime** (or near-zero)
- 🔁 **Easy rollback** (stop rollout, redeploy old version)
- 📊 **Canary-style monitoring** possible during rollout
- 💬 **Better user experience** during deployments

---

## ⚠️ Drawbacks

- Complexity in **managing mixed versions** during rollout.
- If not monitored properly, issues may **propagate gradually**.
- Needs **stateless services** or **careful state management**.

---

## 🔁 Rolling vs Blue-Green vs Canary

| Strategy         | Downtime | Risk    | Speed  | Rollback |
|------------------|----------|---------|--------|----------|
| **Rolling**       | ❌ No     | Medium  | Medium | Medium   |
| **Blue-Green**    | ❌ No     | Low     | Fast   | Easy     |
| **Canary**        | ❌ No     | Very Low | Slow   | Very Easy|

---

## 🧠 Best Practices

- Use **health checks** and **readiness probes**.
- Monitor metrics (CPU, latency, errors) during rollout.
- Use **feature flags** if logic needs to toggle between versions.
- Automate rollback on failure.

---

## 📌 Summary

> **Rolling deployment** helps you deploy software updates gradually with minimal risk and no downtime. It's ideal for highly available systems and works well with containerized platforms like Kubernetes.

---
