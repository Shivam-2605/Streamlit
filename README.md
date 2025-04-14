## 📊 Streamlit Visualization App with Docker

### 🚀 Quick Start

Run the app in three simple steps:

```bash
docker build -t streamlit-visualization .  # Build the container
docker run -p 8501:8501 streamlit-visualization  # Launch the app
# Open http://localhost:8501 in your browser 🌐
```

---

### 🛠 Tech Stack

-   **Python**
-   **Streamlit**
-   **Docker**
-   **Pandas**
-   **NumPy**
-   **Matplotlib**
-   **Plotly**

---

### 📁 Project Structure

```
project_root/
│── .streamlit/
│   └── config.toml   # Streamlit server configuration
│── src/
│   └── main.py       # Application logic
│── Dockerfile        # Container blueprint
│── requirements.txt  # Dependency manifest
│── README.md         # Project documentation
```

---

### 🔍 Key Components

#### 🐋 Dockerfile - Container Setup

```dockerfile
FROM python:3.9-slim  # Using slim Python 3.9 image
WORKDIR /app          # Define working directory
COPY requirements.txt /app/
RUN pip install --no-cache-dir -r requirements.txt
COPY . /app/
EXPOSE 8501          # Expose Streamlit's port
CMD ["streamlit", "run", "src/main.py", "--server.port=8501", "--server.address=0.0.0.0"]
```

#### ⚙️ config.toml - Streamlit Settings

```toml
[server]
headless = true
runOnSave = true
fileWatcherType = "poll"
```

---

### 🎨 Features of `main.py`

-   **Home Page**: Introduction with an interactive welcome message.
-   **Data Explorer**: Allows CSV upload and displays data with summary statistics.
-   **Visualization Page**:
    -   Generates sample sine wave plots.
    -   Displays an interactive line chart with random data.
    -   Uses `matplotlib` and `streamlit` to create visualizations dynamically.

---

### 🔄 Development Workflow

#### 🚀 Run Locally with Hot-Reload

```bash
docker build -t streamlit-visualization:v1.0 .
docker run -p 8501:8501 --name my-visualization streamlit-visualization
```

#### 🔧 Troubleshooting

-   **Port Conflict?** Use `-p 8502:8501` to change the port.
-   **Need to Remove a Stuck Container?**

```bash
docker ps -a  # Find container ID
docker rm -f <container_id>
```

-   **Shell Access for Debugging?**

```bash
docker exec -it my-visualization /bin/bash
```

---

### 🎯 Next Steps

Enhance the app by adding:

-   More interactive visualizations
-   User-defined dataset uploads
-   Advanced charting with `plotly` and `seaborn`

📜 **License**
MIT License - Free to use, modify, and share!

Made by Omi Kumari🚀
