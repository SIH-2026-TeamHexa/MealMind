MealMind: AI-Powered Food Inventory & Waste Optimization Platform FoodSense AI is an intelligent decision-support platform built for Smart India Hackathon 2026 (Problem Statement S11), aimed at solving food wastage and inefficient procurement in hotels, restaurants, and institutional kitchens. By combining demand forecasting, spoilage-risk scoring, and procurement/preparation optimization, FoodSense AI turns raw kitchen data into clear, explainable actions that cut waste and save money.

🚨 Problem

⁠ ⁠Institutional kitchens routinely over-purchase and over-prepare food due to guesswork-based planning.
⁠ ⁠Spoilage is detected too late, after ingredients have already crossed the point of usability.
⁠ ⁠Waste patterns go unexplained, so the same mistakes repeat week after week.
⁠ ⁠Procurement decisions are rarely tied to actual forecasted demand.

Consequences include:

⁠ ⁠Significant financial losses from spoiled inventory
⁠ ⁠Inconsistent stock availability and stockouts
⁠ ⁠Overproduction that goes straight to plate/kitchen waste
⁠ ⁠No feedback loop to improve future planning

🎯 What FoodSense AI Solves

⁠ ⁠Lack of Foresight: Manual inventory tracking without demand prediction.
⁠ ⁠Reactive Waste Management: Waste is measured after the fact, not prevented.
⁠ ⁠Opaque Decisions: Purchase/prep quantities aren't explained or justified.

🌟 Features

⁠ ⁠📦 Smart Inventory Management: FEFO-based tracking with expiry, batch, and supplier data.
⁠ ⁠⚠️ AI Spoilage Risk Score: Multi-factor risk scoring (0–100) with plain-language explanations.
⁠ ⁠📊 AI Demand Forecaster: Predicts meal and ingredient demand using historical + contextual data.
⁠ ⁠🛒 "What Should I Buy Tomorrow?": Forecast-driven procurement recommendations.
⁠ ⁠🍳 Preparation Optimizer: First-batch/second-batch prep quantities to avoid overproduction.
⁠ ⁠♻️ Waste Pattern Detector: Root-cause insights (e.g. "Rice waste is 32% higher on Sundays").
⁠ ⁠💰 Waste Cost Calculator: Real-time financial impact and potential savings estimates.
⁠ ⁠🔥 Waste Heatmap: Visualizes waste hotspots by day, meal, and ingredient.
⁠ ⁠🧪 What-If Simulator: Test scenarios (customer count, prep %, procurement %) before acting.

🛠 Tech Stack Frontend

⁠ ⁠React + Vite
⁠ ⁠Tailwind CSS, Recharts
⁠ ⁠Lucide React, React Router

Backend

⁠ ⁠Python + FastAPI
⁠ ⁠SQLAlchemy + Alembic (migrations)
⁠ ⁠JWT-based Authentication

Database

⁠ ⁠PostgreSQL (inventory, forecasts, waste records, users)

AI & Optimization Tools

⁠ ⁠pandas, numpy, scikit-learn, xgboost (demand forecasting)
⁠ ⁠Prophet (time-series, where applicable)
⁠ ⁠Google OR-Tools / scipy.optimize (procurement & preparation optimization)

🗺 Architecture & Workflow

⁠ ⁠Modular architecture with clear separation between frontend, backend, ML services, and optimization engine.
⁠ ⁠Closed-loop pipeline: Historical Data → Demand Forecasting → Inventory Analysis → Spoilage Prediction → Procurement Optimization → Preparation Optimization → Waste Detection → New Data → Improved Forecast.
⁠ ⁠Future deployment scaling via Docker containers and cloud hosting (AWS/Render/Railway).

Local Development Setup To run the MealMind project locally, follow these steps:

Clone the Repository ⁠ bash git clone https://github.com/<your-org>/foodsense-ai cd MealMind ⁠
Set Up the Database (PostgreSQL) ⁠ bash
Using Docker (recommended for hackathon speed)

docker run --name foodsense-postgres
-e POSTGRES_DB=foodsense_db
-e POSTGRES_USER=foodsense_user
-e POSTGRES_PASSWORD=change_this_password
-p 5432:5432
-d postgres:15 ⁠

⁠ ⁠Or install PostgreSQL locally and create a database named ⁠ foodsense_db ⁠.
Start the Backend (FastAPI + PostgreSQL) The backend handles inventory, forecasting APIs, procurement/preparation logic, and authentication.

⁠ bash cd backend python3 -m venv venv source venv/bin/activate # or venv\Scripts\activate on Windows pip install -r requirements.txt cp .env.example .env ⁠

⁠ ⁠Update ⁠ DATABASE_URL ⁠ and ⁠ SECRET_KEY ⁠ in your ⁠ .env ⁠ file.

Run migrations and seed demo data:

⁠ bash alembic upgrade head python data/generate_synthetic_data.py python -m app.db.init_db --load-sample-data ⁠

Train the demand forecasting model:

⁠ bash python -m app.ml.train_forecast_model ⁠

Start the server:

⁠ bash uvicorn app.main:app --reload --port 8000 ⁠

This will start the backend at ⁠ http://localhost:8000 ⁠ (API docs at ⁠ /docs ⁠).

Start the Frontend (React + Vite) ⁠ bash cd frontend npm install cp .env.example .env npm run dev ⁠
⁠ ⁠Ensure ⁠ VITE_API_BASE_URL ⁠ in ⁠ .env ⁠ points to ⁠ http://localhost:8000 ⁠.

This will start the frontend server at ⁠ http://localhost:5173 ⁠.

📈 Future Enhancements 1.⁠ ⁠Supplier Integration: Auto-generate purchase orders directly to supplier systems. 2.⁠ ⁠Multi-Kitchen Benchmarking: Compare waste/efficiency across branches. 3.⁠ ⁠Mobile App for Kitchen Staff: On-the-floor stock updates and alerts. 4.⁠ ⁠Real Dataset Integration: Replace synthetic data with live POS/inventory feeds.

🚀 Deployment

⁠ ⁠Frontend: Vercel
⁠ ⁠Backend: Railway / Render
⁠ ⁠Planned Scaling:

Docker for containerization AWS for production deployment 📚 References

⁠ ⁠Smart India Hackathon 2026 — Problem Statement S11
⁠ ⁠FAO Reports on Food Loss and Waste
⁠ ⁠Industry benchmarks on institutional kitchen wastage

👥 Contributors This project was proudly built by our team for SIH 2026:
<a href="https://github.com" target="blank">@shivisri12</a> <a href="https://github.com" target="blank">@dhri-tea</a> <a href="https://github.com" target="blank">@phew-phew007</a> <a href="https://github.com" target="blank">@sanskriti56</a> <a href="https://github.com" target="blank">@shivnagiii0611</a> <a href="https://github.com" target="blank">@agarwalyukti06</a>
