# AI-Emergency-Pressure-Ambulance-Load-Prediction-System

1. Project Objective

This system was built to provide a scalable, AI-driven solution for hospitals to:

Predict Emergency Department (ED) overloads before they occur.

Identify accident-prone hotspots using geospatial clustering.

Trigger early alerts based on real-time thresholds for better resource allocation

2. Technology Stack

Consistent with the required industry standards:

Backend API: Python + FastAPI (for high-performance asynchronous requests).

ML Pipeline: Python + Scikit-learn (Random Forest Regressor for time-series patterns).

Validation: Pydantic (for strict data type enforcement and security auditing).

Geospatial: Scikit-learn DBSCAN (for hotspot detection).

3. System Architecture

The system follows a Strict Isolation model to ensure modularity and scalability:

Data Ingestion: Processes historical logs, weather, and seasonal data.

Database Layer: Clean schema design for storing incident reports and predictions.

ML Prediction Engine: Processes features through a trained Random Forest model.

Alert Engine: Monitors if predictions cross the established "Critical" threshold.

REST API: Serves JSON responses to the frontend or hospital dashboards.

4. Phase 3 Design Decisions & Security Audit

As per the Phase 3: Completion requirements:

Security & Integrity
Data Sanitization: Implemented Pydantic schemas to audit incoming requests. This prevents malformed data or injection attempts from crashing the prediction engine.

Error Handling: Replaced generic errors with specific, descriptive messages that guide the user without exposing system internals.

User Experience (UX)
Actionable Intelligence: The API doesn't just return a number; it provides an "Action Plan" (e.g., "Mobilize extra ambulances") to assist decision-makers immediately.

Real-time Status: Included alert levels (STABLE/CRITICAL) to allow for instant visual recognition on dashboards.

5. Folder Structure (Industry Standard)

The project is organized as follows to ensure it is deployment-ready:

project_root/

│

├── app/

│   ├── main.py          # FastAPI application & routes

│   ├── engine.py        # ML Model & Prediction logic

│   ├── database.py      # SQLAlchemy connections

│   └── models/

│       ├── schemas.py   # Pydantic validation models

│       └── accident.py  # Database entities

├── requirements.txt     # Dependency list

└── README.md            # This documentation
