# Best Bike Paths (BBP) - Requirements Engineering and Design Project

## Overview
This repository contains the deliverables for the **Requirement Engineering and Design (R&DD)** project developed for the **Software Engineering 2** course at **Politecnico di Milano** (A.Y. 2025/2026)[cite: 1]. 

The project focuses on **Best Bike Paths (BBP)**, a software system designed to support users in recording cycling trips, collecting community-driven path evaluations, detecting road anomalies (such as potholes) via mobile sensors, and visualizing optimal bike routes[cite: 1].

---

## Repository Structure

The repository is organized into the following directories:

- **`RASD/`**: Contains the *Requirement Analysis and Specification Document*, detailing system scenarios, use cases, UML models (class, sequence, and activity diagrams), and formal verification using **Alloy**[cite: 1].
- **`DD/`**: Contains the *Design Document*, outlining the architectural design, component view, deployment, runtime views, UI design, requirements traceability, and the implementation/testing plan[cite: 1].
- **`DeliveryFolder/`**: Contains the final PDF releases of the project deliverables (`RASD.pdf` and `DD.pdf`) alongside formal modeling files.

---

## Project Scope & Features

Depending on the project requirements, the system covers:
- **Personal Trip Recording:** Tracking distance, speed, and meteorological data[cite: 1].
- **Manual & Automated Path Insertion:** Allowing users to manually submit path conditions or automatically collect telemetry via smartphone GPS, accelerometer, and gyroscope to detect obstacles (with user confirmation to prevent false positives)[cite: 1].
- **Information Merging:** Aggregating reports from multiple users based on data freshness and confirmation count[cite: 1].
- **Route Visualization:** Querying and displaying the best-scored bike paths between a given origin and destination[cite: 1].

---

## Authors
- **Gabriele Martorano**
- **[Nome Coautore/i]**
