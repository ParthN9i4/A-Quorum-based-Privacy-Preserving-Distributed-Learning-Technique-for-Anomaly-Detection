# Quorum-Based Privacy-Preserving Distributed Anomaly Detection

**Implementation of quorum-consensus federated anomaly detection using Isolation Forests.**  
Clients train local Isolation Forest models and share models or scores to reach a quorum-based decision on anomalies while keeping raw data local.

---

## Table of contents
- [Overview](#overview)  
- [Repository structure](#repository-structure)  
- [Requirements](#requirements)  
- [Quickstart](#quickstart)  
- [Notebooks & usage](#notebooks--usage)  
- [Data](#data)  
- [Experimental notes](#experimental-notes)  
- [Citation](#citation)  
- [License & Contact](#license--contact)  

---

## Overview
This project demonstrates two practical approaches for federated anomaly detection:

- **Equal-weight quorum:** every client’s model contributes equally to the aggregated decision.  
- **Weighted quorum:** client contributions are weighted (e.g., by local dataset size or validation reliability) for more robust aggregation in heterogeneous settings.

These methods preserve client privacy by sharing only models, scores, or secure aggregates — no raw data leaves clients.

---

## Repository structure
