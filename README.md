# Astra Automotive Intelligence System

## Overview
This project aims to build a comprehensive data intelligence system for the automotive industry, specifically designed to support Astra International's automotive business division. The system integrates various automotive data sources (vehicle prices, sales, consumer sentiment, news) into a unified platform for real-time market insights and data-driven decision making.

### Expected Outputs
1. Interactive dashboard for market trend monitoring
2. Automated reporting system for sales analysis
3. Predictive analytics for sales forecasting
4. Sentiment analysis for brand monitoring

## Project Architecture
![Architecture Diagram](docs/images/architecture.png)

### Technology Stack
- **Data Ingestion**: Selenium, BeautifulSoup4, Requests
- **Processing**: Apache Spark, Pandas, DuckDB
- **Storage**: PostgreSQL, MinIO
- **Orchestration**: Apache Airflow
- **Containerization**: Docker
- **Visualization**: Metabase, Streamlit

## Data Sources

### Web Scraping
1. [Carmudi](https://www.carmudi.co.id/)
   - Used vehicle data
   - Price trends
   - Vehicle specifications

2. [Oto.com](https://www.oto.com/)
   - New vehicle specifications
   - Price listings
   - Market comparisons

3. [Google News](https://news.google.com/)
   - Automotive news
   - Astra-related news
   - Industry trends

### API Integration
1. [News API](https://newsapi.org/)
   - Automotive industry news
   - Market sentiment analysis

2. [Bank Indonesia API](https://www.bi.go.id/)
   - Exchange rates
   - Economic indicators

### Public Datasets
1. [GAIKINDO](https://www.gaikindo.or.id/)
   - Wholesale vehicle data
   - Retail sales data
   - Market statistics

2. [BPS (Statistics Indonesia)](https://www.bps.go.id/)
   - Economic indicators
   - Consumer confidence index
   - Market research data

## Project Structure
```
astra-automotive-intelligence/
├── airflow/
│   ├── dags/
│   │   ├── scraping_dag.py
│   │   ├── processing_dag.py
│   │   └── analytics_dag.py
│   └── plugins/
├── src/
│   ├── scrapers/
│   │   ├── carmudi_scraper.py
│   │   ├── oto_scraper.py
│   │   └── news_scraper.py
│   ├── transformers/
│   │   ├── price_transformer.py
│   │   ├── sales_transformer.py
│   │   └── sentiment_transformer.py
│   ├── loaders/
│   │   ├── postgres_loader.py
│   │   └── minio_loader.py
│   └── utils/
├── tests/
├── notebooks/
├── config/
├── data/
│   ├── raw/
│   ├── processed/
│   └── final/
├── docs/
├── docker/
└── dashboard/
```

## Data Model
Our data warehouse follows a star schema design with the following key tables:

### Fact Tables
1. sales_fact
2. price_fact
3. sentiment_fact

### Dimension Tables
1. vehicle_dim
2. brand_dim
3. time_dim
4. location_dim
5. customer_dim

## Getting Started

### Prerequisites
- Python 3.10+
- Docker & Docker Compose
- Git

### Installation Steps

1. Clone the repository
```bash
git clone https://github.com/abilfarabil/astra-automotive-intelligence.git
cd astra-automotive-intelligence
```

2. Create and activate virtual environment
```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
# or
.\venv\Scripts\activate  # Windows
```

3. Install dependencies
```bash
pip install -r requirements.txt
```

4. Start Docker services
```bash
docker-compose up -d
```

5. Initialize Airflow
```bash
docker-compose run airflow airflow db init
docker-compose run airflow airflow users create \
    --username admin \
    --password admin \
    --firstname Admin \
    --lastname User \
    --role Admin \
    --email admin@example.com
```

## Project Progress
- [x] Project Setup and Documentation
- [x] Data Source Identification
- [x] Infrastructure Setup
- [ ] Data Pipeline Implementation
- [ ] Testing and Quality Assurance
- [ ] Dashboard Development
- [ ] Production Deployment

## Contributing
This project is maintained by abilfarabil. For major changes, please open an issue first to discuss what you would like to change.

## License
[MIT](LICENSE)