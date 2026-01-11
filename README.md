# AI Data Analyst - Production-Ready SaaS Platform

A complete AI-powered data analysis platform that transforms raw data into actionable insights instantly.

## 🏗️ Architecture Overview

```
┌─────────────────────────────────────────────────────────────────┐
│                        FRONTEND                                  │
│                   (index.html - SaaS Landing)                   │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐             │
│  │   Hero      │  │ AI Assistant│  │  Features   │             │
│  │  Section    │  │    Chat     │  │   Pricing   │             │
│  └─────────────┘  └──────┬──────┘  └─────────────┘             │
└──────────────────────────┼──────────────────────────────────────┘
                           │ REST API
                           ▼
┌─────────────────────────────────────────────────────────────────┐
│                    JAVA SPRING BOOT BACKEND                      │
│                      (Port 8080)                                 │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐             │
│  │  Controller │  │   Service   │  │    File     │             │
│  │    Layer    │──│    Layer    │──│   Storage   │             │
│  └─────────────┘  └──────┬──────┘  └─────────────┘             │
│                          │                                       │
│  Endpoints:              │                                       │
│  POST /api/v1/upload     │  Security & Validation               │
│  POST /api/v1/chat       │  Session Management                  │
│  POST /api/v1/analyze    │  Result Caching                      │
│  POST /api/v1/visualize  │                                       │
│  POST /api/v1/pivot      │                                       │
│  POST /api/v1/export     │                                       │
└──────────────────────────┼──────────────────────────────────────┘
                           │ HTTP/REST
                           ▼
┌─────────────────────────────────────────────────────────────────┐
│                    PYTHON AI BRAIN                               │
│                      (Port 5000)                                 │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐             │
│  │   AIBrain   │  │   Pandas    │  │ Matplotlib  │             │
│  │    Core     │──│  Analysis   │──│   Charts    │             │
│  └─────────────┘  └─────────────┘  └─────────────┘             │
│                                                                  │
│  Capabilities:                                                   │
│  • Natural Language Understanding                                │
│  • Data Loading (CSV, Excel, JSON)                              │
│  • Automatic Data Cleaning                                       │
│  • Smart Pivot Table Generation                                  │
│  • Statistical Analysis                                          │
│  • Trend Detection                                               │
│  • Visualization Generation                                      │
│  • Insight Generation                                            │
└─────────────────────────────────────────────────────────────────┘
```

## 📁 Project Structure

```
ai-data-analyst/
├── index.html                          # Frontend - SaaS Landing Page
├── README.md                           # This file
│
├── backend/
│   ├── python/
│   │   ├── ai_brain.py                 # AI Brain - Core Intelligence
│   │   ├── requirements.txt            # Python dependencies
│   │   └── uploads/                    # Temporary file storage
│   │
│   └── java/
│       ├── pom.xml                     # Maven configuration
│       └── src/
│           └── main/
│               ├── java/
│               │   └── com/aidataanalyst/
│               │       ├── AiDataAnalystApplication.java
│               │       ├── controller/
│               │       │   └── AnalysisController.java
│               │       ├── service/
│               │       │   ├── AnalysisService.java
│               │       │   └── FileStorageService.java
│               │       └── dto/
│               │           ├── ApiResponse.java
│               │           └── DTOs.java
│               └── resources/
│                   └── application.yml
```

## 🚀 Quick Start

### Prerequisites

- Java 17+ (for Spring Boot)
- Python 3.9+ (for AI Brain)
- Maven 3.8+ (for Java build)

### 1. Start Python AI Brain

```bash
cd backend/python

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install flask flask-cors pandas numpy matplotlib seaborn openpyxl xlrd

# Start the AI Brain
python ai_brain.py
```

The AI Brain will start on `http://localhost:5000`

### 2. Start Java Spring Boot Backend

```bash
cd backend/java

# Build the project
mvn clean install

# Run the application
mvn spring-boot:run
```

The backend will start on `http://localhost:8080`

### 3. Open the Frontend

Simply open `index.html` in a web browser, or serve it with a local server:

```bash
# Using Python
python -m http.server 3000

# Using Node.js
npx serve .
```

## 🧠 AI Brain Capabilities

### Message Processing

The AI Brain understands natural language and can:

| Request Type | Example Messages |
|--------------|------------------|
| **Greetings** | "Hello", "Hi", "Hey there" |
| **Help** | "What can you do?", "Help me" |
| **Analysis** | "Analyze my data", "Show insights" |
| **Visualization** | "Create a bar chart", "Show me a pie chart" |
| **Pivot Tables** | "Create pivot table", "Summarize by category" |
| **Statistics** | "Show statistics", "Calculate average" |
| **Data Cleaning** | "Clean my data", "Remove duplicates" |
| **Trends** | "Find trends", "Show patterns" |
| **Export** | "Export to CSV", "Download as Excel" |

### Supported File Types

| Format | Extensions | Description |
|--------|------------|-------------|
| CSV | .csv | Comma-separated values |
| Excel | .xlsx, .xls | Microsoft Excel files |
| JSON | .json | JSON data files |

### Auto-Detection Features

1. **Column Types**: Automatically detects numeric, text, and date columns
2. **Dimensions vs Metrics**: Identifies categorical (dimensions) and numerical (metrics) columns
3. **Best Aggregations**: Suggests sum, average, or count based on data types
4. **Data Quality Issues**: Finds missing values, duplicates, and outliers

## 🔌 API Reference

### Upload File
```http
POST /api/v1/upload
Content-Type: multipart/form-data

file: <binary>
```

### Chat with AI
```http
POST /api/v1/chat
Content-Type: application/json

{
  "message": "Analyze my sales data",
  "sessionId": "optional-session-id"
}
```

### Create Visualization
```http
POST /api/v1/visualize
Content-Type: application/json

{
  "chartType": "bar",
  "options": {}
}
```

### Create Pivot Table
```http
POST /api/v1/pivot
Content-Type: application/json

{
  "rows": "category",
  "columns": null,
  "values": "amount",
  "aggFunc": "sum"
}
```

### Export Data
```http
POST /api/v1/export
Content-Type: application/json

{
  "format": "csv"
}
```

## 🔒 Security Considerations

### File Security
- File type validation (whitelist approach)
- File size limits (100MB max)
- Temporary storage with automatic cleanup
- No permanent data storage

### API Security
- CORS configuration
- Input validation
- Error handling without exposing internals
- Rate limiting ready

### Data Privacy
- Files deleted after processing
- No user data stored
- Session-based isolation
- Secure file paths

## 📈 Scaling Strategy

### Horizontal Scaling

```
                    ┌─────────────────┐
                    │  Load Balancer  │
                    └────────┬────────┘
                             │
         ┌───────────────────┼───────────────────┐
         │                   │                   │
         ▼                   ▼                   ▼
┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
│ Java Backend 1  │ │ Java Backend 2  │ │ Java Backend 3  │
└────────┬────────┘ └────────┬────────┘ └────────┬────────┘
         │                   │                   │
         └───────────────────┼───────────────────┘
                             │
                    ┌────────┴────────┐
                    │  Message Queue  │
                    │   (RabbitMQ)    │
                    └────────┬────────┘
                             │
         ┌───────────────────┼───────────────────┐
         │                   │                   │
         ▼                   ▼                   ▼
┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
│ Python Worker 1 │ │ Python Worker 2 │ │ Python Worker 3 │
└─────────────────┘ └─────────────────┘ └─────────────────┘
```

### Database Integration (Future)

- PostgreSQL for user data
- Redis for caching
- S3 for file storage
- Elasticsearch for search

## 🎨 Frontend Features

### Theme System
- Light/Dark mode toggle
- 10 accent color presets
- Custom background images
- Persistent settings

### AI Chat Interface
- Real-time messaging
- Typing indicators
- File upload support
- Image processing
- Quick action buttons
- Conversation history

### Responsive Design
- Mobile-first approach
- Tablet optimization
- Desktop layouts
- Touch-friendly controls

## 📊 Data Flow

```
1. User uploads file through frontend
                    │
                    ▼
2. Java backend receives file
   - Validates type and size
   - Stores temporarily
   - Generates file ID
                    │
                    ▼
3. Java sends file path to Python AI Brain
                    │
                    ▼
4. Python AI Brain processes file
   - Loads data with Pandas
   - Detects column types
   - Performs initial analysis
   - Generates insights
                    │
                    ▼
5. AI Brain returns JSON response
   - Statistics
   - Data preview
   - Recommendations
                    │
                    ▼
6. Java backend caches result
   - Returns to frontend
                    │
                    ▼
7. Frontend displays results
   - Shows insights
   - Enables further queries
```

## 🛠️ Development

### Running Tests

```bash
# Java tests
cd backend/java
mvn test

# Python tests
cd backend/python
python -m pytest tests/
```

### Building for Production

```bash
# Java
cd backend/java
mvn clean package -DskipTests
java -jar target/ai-data-analyst-1.0.0.jar

# Python
cd backend/python
gunicorn -w 4 -b 0.0.0.0:5000 ai_brain:app
```

## 📝 License

MIT License - Feel free to use for commercial projects.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

---

Built with ❤️ for data analysts everywhere.
