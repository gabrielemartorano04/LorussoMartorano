# 🚴 Best Bike Paths (BBP) — Software Engineering II Project (A.Y. 2025–2026)

Requirements Engineering and Design project developed for the **Software Engineering 2** course at **Politecnico di Milano**.

* **University:** Politecnico di Milano — Department of Electronics, Information and Bioengineering (DEIB)
* **Advisor:** Prof. Matteo Giovanni Rossi
* **Authors:** [Gabriele Martorano](https://github.com/gabrielemartorano04) & [Luca Lorusso](https://github.com/Luc4Lo)

---

## 📋 Project Overview

Best Bike Paths (BBP) is a software system designed to support cyclists in creating, evaluating, and browsing an inventory of urban bike paths. The platform aggregates user-generated data and automatically collected sensor information to build a shared, reliable representation of the bike path network. 

### Core Features
* **Trip Recording & Metrics:** Registered users can record their rides to keep track of their personal cycling activities. The system computes performance metrics such as total distance and average speed. Trips are automatically enriched with meteorological data (e.g., temperature and wind speed) retrieved from an External Weather Service (EWS).
* **Manual & Automated Reporting:** Users can manually report street conditions and obstacles. Alternatively, they can activate an "Automated Mode" where the mobile client utilizes the smartphone's GPS, accelerometer, and gyroscope to infer the presence of anomalies like potholes.
* **Mandatory Validation Workflow:** Data gathered automatically through device sensors must be explicitly reviewed, confirmed, or corrected by the user before it is published to the community dataset.
* **Path Search & Ranking:** Any user, including unregistered guests, can specify an origin and destination to view available bike paths on an interactive map. BBP evaluates feasible routes using a "Path Score," which ranks alternatives based on path effectiveness and the published reports of obstacles and road conditions.

---

## ⚙️ System Architecture

The BBP platform is built upon a Service-Oriented **3-Tier Architecture** deployed in a cloud environment.

* **Presentation Tier (Mobile Client):** Implemented as a mobile application optimized for smartphones. It is responsible for touch interactions, map visualization, real-time GPS tracking, and local sensor data acquisition during automated recording.
* **Application Tier (Cloud Backend):** Hosted on cloud-based virtual machines (e.g., AWS EC2 instances) behind a Load Balancer to ensure high availability. It exposes its functionalities through an API Gateway and is structurally decomposed into specialized macro-components:
  * *User & Trip Management System:* Handles authentication, role-based access control, and trip lifecycle persistence.
  * *Auto Detection System:* Processes raw sensor data to detect anomalies and generates candidate reports.
  * *Report & Validation System:* Enforces the mandatory user-validation workflow and manages the publication of path information.
  * *Recommendation & PathScore Engine:* Computes the routing scores by penalizing path segments with reported hazards.
  * *Routing & Map Integration System:* Interfaces with an External Map Service (EMS) to retrieve base map layers and candidate routes.
* **Data Tier:** Managed via a Relational DBMS hosted on a managed cloud storage infrastructure. It ensures the relational integrity of user profiles, path segments, trip records, and validation states.

---

## 🔬 Formal Analysis

To guarantee the logical consistency of the reporting system, the project includes a formal mathematical verification.
* **Alloy Analyzer:** The lifecycle of obstacle reports and the path recommendation constraints were modeled using the Alloy language.
* **Verified Properties:** The formal models successfully verified that automatic reports cannot bypass the validation state machine, and that recommended paths strictly avoid segments with published obstacles whenever clean alternative routes exist.

---

## 📁 Repository Structure

```text
.
├── RASDv1.pdf              # Requirements Analysis and Specification Document
├── DDv1.pdf                # Architectural Design Document
└── README.md               # Project documentation
