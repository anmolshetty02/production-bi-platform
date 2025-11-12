# 🏭 AI-Powered Production BI Analytics Platform

**Natural language to SQL business intelligence system for manufacturing operations**

Transform 14+ years of legacy data into actionable insights using AI-powered analytics and real-time dashboards.

[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.28+-red.svg)](https://streamlit.io/)
[![DuckDB](https://img.shields.io/badge/DuckDB-Latest-yellow.svg)](https://duckdb.org/)
[![LangChain](https://img.shields.io/badge/LangChain-Latest-green.svg)](https://langchain.com/)

---

## 🎯 Problem Statement

A ₹100+ Crore manufacturing operation was running on **15-year-old MS Access databases** with:
- ❌ 4+ hour manual report generation time
- ❌ No real-time visibility into operations
- ❌ Critical business insights buried in 98 disconnected tables
- ❌ Executive decisions delayed by data bottlenecks

**This system eliminated those bottlenecks.**

---

## 💡 Solution Overview

Built an end-to-end AI-powered BI platform that:

✅ **Migrated 98 tables** (295K+ records) from legacy MS Access to modern analytics stack  
✅ **Cut reporting time from 4+ hours to <30 minutes** with automated dashboards  
✅ **Enabled natural language queries** - Ask "Show me top 5 customers by revenue" → Get instant SQL + results  
✅ **Uncovered critical insights** - Revenue concentration, delivery performance, cost analysis  
✅ **Real-time operational dashboards** - Sales, inventory, production, costing at a glance

---

## 🚀 Key Features

### 1. **AI-Powered Query Interface**
- 🤖 Natural language to SQL using **LangChain + Llama 3**
- 📊 Automatic query generation from 98-table schema
- 🎯 Business-context-aware responses (sales vs production vs purchasing)
- ⚡ Real-time execution with smart error handling

### 2. **Automated ETL Pipeline**
- 📥 Extract from MS Access (mdb-tools)
- 🧹 Clean and validate data
- 💾 Load into DuckDB analytics warehouse
- 📅 Scheduled daily/weekly refreshes

### 3. **Executive Dashboards**
- 📈 Daily operations report (sales, invoices, customers)
- 📊 Customer performance analysis
- 💰 P&L and profitability tracking
- 🚚 On-time delivery metrics

### 4. **Pre-built SQL Reports**
- Daily sales summaries
- Monthly customer performance
- Weekly trend analysis
- Yearly costing breakdown

---

## 📊 Business Impact

### Quantifiable Results

| Metric | Before | After | Improvement |
|--------|--------|-------|-------------|
| **Report Generation Time** | 4+ hours | <30 minutes | **87.5% faster** |
| **Data Accessibility** | Manual queries only | Natural language + dashboards | **Self-service** |
| **Historical Analysis** | Limited to recent data | 14 years (2012-2025) | **Full history** |
| **Decision Latency** | Days | Real-time | **Instant insights** |

### Key Insights Uncovered

📌 **Revenue Concentration:** 50% of revenue from top 3 customers  
📌 **Delivery Performance:** 82% on-time delivery rate  
📌 **Data Volume:** ₹148+ Crore total revenue processed  
📌 **Customer Base:** 1,364 active customers across operations

---

## 🛠️ Tech Stack

**Core Technologies:**
- **Python 3.9+** - Core application logic
- **Streamlit** - Interactive web dashboards
- **DuckDB** - High-performance analytics database
- **LangChain** - LLM orchestration framework
- **Ollama (Llama 3)** - Local LLM for SQL generation

**Data Processing:**
- **Pandas** - Data manipulation
- **mdb-tools** - MS Access extraction
- **Plotly** - Interactive visualizations

**AI/ML:**
- Natural language processing for query understanding
- Schema-aware prompt engineering
- Context-based SQL generation

---

## 📁 Project Structure

```
production-bi-platform/
├── app.py                      # Main Streamlit application
├── ai/
│   ├── schema_context.py       # Comprehensive schema documentation
│   └── insights_engine.py      # Business insights generator
├── etl/
│   ├── jobs/
│   │   ├── export_mdb_to_csv.py      # MS Access extraction
│   │   ├── clean_raw_to_stage.py     # Data cleaning
│   │   ├── load_stage_to_duckdb.py   # DuckDB loading
│   │   └── scheduler.py              # Automated scheduling
│   └── utils/                   # ETL utilities
├── data/
│   ├── raw/                     # Raw CSV exports
│   ├── stage/                   # Cleaned intermediate data
│   └── warehouse/               # DuckDB analytics warehouse
├── reports/
│   ├── sql/                     # SQL report templates
│   └── output/                  # Generated report CSVs
├── logs/                        # ETL and app logs
└── requirements.txt
```

---

## 🚦 Quick Start

### Prerequisites

```bash
# Install mdb-tools (for MS Access reading)
# macOS:
brew install mdb-tools

# Linux:
sudo apt-get install mdb-tools

# Install Ollama (for local LLM)
# macOS/Linux:
curl https://ollama.ai/install.sh | sh
ollama pull llama3
```

### Installation

```bash
# Clone repository
git clone https://github.com/anmolshetty02/production-bi-platform.git
cd production-bi-platform

# Create virtual environment
python3 -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### Running the Application

```bash
# Activate virtual environment
source .venv/bin/activate

# Run Streamlit app
streamlit run app.py
```

Navigate to `http://localhost:8501` in your browser.

---

## 🔄 ETL Pipeline

### Data Migration Process

```
MS Access Database (98 tables)
         ↓
[Extract] - mdb-tools → CSV exports
         ↓
[Clean] - Data validation, type casting, deduplication
         ↓
[Load] - DuckDB warehouse (optimized for analytics)
         ↓
[Report] - Pre-aggregated summary tables
```

### Running ETL Jobs

```bash
# Full pipeline
cd etl/jobs

# Step 1: Export from MS Access
python export_mdb_to_csv.py

# Step 2: Clean and stage
python clean_raw_to_stage.py

# Step 3: Load into DuckDB
python load_stage_to_duckdb.py

# Step 4: Generate reports
python run_reports.py
```

---

## 🤖 AI Query Interface

### How It Works

1. **User Input:** Natural language question
   - Example: "Show me top 5 customers by revenue in 2024"

2. **Schema Context:** 98-table schema with business logic injected into LLM prompt

3. **SQL Generation:** Llama 3 generates optimized DuckDB SQL

4. **Execution:** Query runs on analytics warehouse

5. **Results:** Interactive table + auto-generated visualizations

6. **Insights:** AI-powered business insights from results

### Example Queries

```
"What were our total sales in June 2024?"
"Compare revenue between 2022 and 2024"
"Show me customers with declining orders"
"What's our average delivery time?"
"Top 10 products by profitability"
```

### Smart Features

✅ **Context-aware:** Distinguishes sales vs production vs purchasing queries  
✅ **Date handling:** Understands various date formats and ranges  
✅ **Error recovery:** Retries with fallback strategies on SQL errors  
✅ **Query optimization:** Generates efficient JOINs and aggregations

---

## 📈 Dashboard Features

### Daily Operations Report
- Real-time sales metrics (total sales, invoices, customers)
- Sales breakdown by customer
- Interactive date selector
- Auto-refresh capability

### Pre-built Reports
- Daily sales summaries
- Monthly customer performance
- Weekly trend analysis
- Yearly costing breakdown

### Query AI
- Natural language interface
- Generated SQL preview
- Auto-visualization
- Business insights generation

---

## 🔧 Configuration

### Database Connection

Edit paths in `app.py`:
```python
WAREHOUSE = Path("data/warehouse/metcut.duckdb")
REPORTS = Path("reports/output")
```

### LLM Settings

Modify in Query AI section:
```python
llm = Ollama(model="llama3:latest")  # Change model here
```

### ETL Paths

Update in `etl/jobs/export_mdb_to_csv.py`:
```python
MDB_PATH = "path/to/your/database.mdb"
RAW_DIR = "data/raw"
```

---

## 📊 Sample Insights

### Revenue Analysis
- **Total Revenue (14 years):** ₹148.40 Crore
- **Annual Average:** ₹10.6 Crore
- **Peak Year:** [Query to find]
- **Growth Trend:** [Query to analyze]

### Customer Metrics
- **Total Customers:** 1,364 active
- **Top Customer Concentration:** 50% revenue from top 3
- **Geographic Distribution:** [Query by state]
- **Retention Rate:** [Query year-over-year]

### Operational Performance
- **On-Time Delivery:** 82% rate
- **Invoice Processing:** 39,306 invoices (14 years)
- **Average Order Value:** [Query to calculate]
- **Production Efficiency:** [Query work orders]

---

## 🎯 Technical Highlights

### Schema-Aware AI
- 98 tables with full column documentation
- Business logic encoded in prompts
- Join patterns for common queries
- Date format handling (MM/DD/YY)

### Query Optimization
- Table aliases for clarity
- Proper date parsing (STRPTIME)
- Efficient aggregations
- Smart error handling

### Real-Time Performance
- DuckDB columnar storage
- Pre-aggregated summary tables
- Indexed lookups
- Query caching

---

## 📚 Documentation

- **[Technical Documentation](docs/TECHNICAL_DOCUMENTATION.md)** - Detailed system architecture
- **[API Reference](docs/API_REFERENCE.md)** - Function and class documentation
- **[Deployment Guide](docs/DEPLOYMENT.md)** - Production deployment instructions

---

## 🚀 Future Enhancements

- [ ] Multi-user authentication and role-based access
- [ ] Real-time data streaming from production systems
- [ ] Advanced ML models for demand forecasting
- [ ] Mobile-responsive dashboard
- [ ] Export to Excel/PDF with branding
- [ ] Email/Slack alerts for KPI thresholds
- [ ] Multi-language support for queries

---

## 📄 License

MIT License - see [LICENSE](LICENSE) file for details.

---

## 👤 Author

**Anmol Shetty**
- LinkedIn: [linkedin.com/in/anmol-shetty-5b9195171](https://www.linkedin.com/in/anmol-shetty-5b9195171/)
- Email: shetty.anm@northeastern.edu
- GitHub: [@anmolshetty02](https://github.com/anmolshetty02)

---

## 🙏 Acknowledgments

- Built for a ₹100+ Crore manufacturing operation
- 14 years of operational data migrated and analyzed
- Serving executive decision-making and operational efficiency

---

## ⚠️ Note

This is a production-grade BI system. Database paths and company-specific details have been anonymized for privacy. Sample data and queries are representative of the actual system capabilities.
