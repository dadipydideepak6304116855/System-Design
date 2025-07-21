# 🌩️ Disaster Recovery in System Design

---

## 🔹 What is Disaster Recovery?

**Disaster Recovery (DR)** is the process of **preparing for and recovering from unexpected failures** such as data center outages, natural disasters, cyberattacks, or system crashes.

> 📌 It focuses on ensuring **business continuity**, minimizing downtime, and restoring services/data as quickly and safely as possible.

---

## 🔹 Why Disaster Recovery Matters

- ✅ Protects against **data loss**
- ✅ Ensures **service availability**
- ✅ Supports **business continuity**
- ✅ Reduces **revenue loss and SLA violations**
- ✅ Builds **customer trust and compliance readiness**

---

## 🔹 Common Disaster Scenarios

- 🌪️ Natural disasters (earthquakes, floods)
- 🔥 Data center fire or power outage
- 🛠️ Hardware/software failure
- 🦠 Malware/ransomware attacks
- 🧑‍💻 Human error (e.g., accidental data deletion)
- 🌍 Region-wide cloud outages

---

## 🔹 Key Metrics in DR Planning

| Metric                | Description                                                      |
|------------------------|------------------------------------------------------------------|
| **RTO (Recovery Time Objective)** | Maximum time the system can be down                     |
| **RPO (Recovery Point Objective)** | Maximum tolerable data loss (in time)                  |

> 📌 Example: RTO = 30 min, RPO = 5 min → System must be restored in 30 min, with at most 5 min of data loss.

---

## 🔹 Disaster Recovery Strategies

| Strategy                | Description                                              |
|-------------------------|----------------------------------------------------------|
| **Backup & Restore**    | Periodic backups stored offsite/cloud                    |
| **Active-Passive**      | Secondary site is idle until failure                     |
| **Active-Active**       | Both sites handle traffic; failover is instant           |
| **Pilot Light**         | Minimal setup running at DR site, scaled up when needed  |
| **Warm Standby**        | Partially running secondary environment                  |
| **Geo-Redundancy**      | Deploy services across multiple regions/zones            |

---

## 🔹 Architecture Example: Active-Passive

```plaintext
[Primary Region]
     ↑ Active Traffic
     ↓ Data Sync
[Secondary Region]
     ↑ Passive until failover

