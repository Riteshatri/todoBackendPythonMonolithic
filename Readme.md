# 🐍 PyTodo Backend (Monolith) – FastAPI + SQL Server on Azure VM

A simple and powerful Python ToDo backend built with **FastAPI**, connected to **SQL Server** via **PyODBC**, and deployable on an **Azure Ubuntu VM**.

---

## 🚀 Features

✨ FastAPI-based REST API  
🛠️ CRUD operations on tasks  
🗄️ SQL Server integration (ODBC Driver 17)  
☁️ Azure VM deployment-ready (Ubuntu 20.04)

---

## ✅ Prerequisites

Before starting, ensure you have:

🔹 Azure Virtual Machine (Ubuntu 20.04)  
🔹 Python 3.x installed  
🔹 pip installed  
🔹 SQL Server instance & credentials  

**Sample Azure Image Configuration:**

```hcl
source_image_reference = {
  publisher = "Canonical"
  offer     = "0001-com-ubuntu-server-focal"
  sku       = "20_04-lts"
  version   = "latest"
}
```

---

## 📦 Getting Started

### 🔧 Step 1: Clone the Repository

```bash
git clone https://github.com/Riteshatri/todoBackendPythonMonolithic.git
cd todoBackendPythonMonolithic
```

---

### 🔑 Step 2: Update Database Connection

Edit the `app.py` file with your SQL Server connection:

```python
connection_string = (
  "DRIVER={ODBC Driver 17 for SQL Server};"
  "SERVER=<your-server>;"
  "DATABASE=<your-database>;"
  "UID=<your-username>;"
  "PWD=<your-password>"
)
```

✅ Ensure you're using **ODBC Driver 17**.

---

### ⚙️ Step 3: Install Dependencies

Run these commands on your **Ubuntu VM**:

```bash
sudo su
apt-get update && apt-get install -y unixodbc unixodbc-dev
curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add -
curl https://packages.microsoft.com/config/debian/10/prod.list > /etc/apt/sources.list.d/mssql-release.list
apt-get update
ACCEPT_EULA=Y apt-get install -y msodbcsql17
apt install python3-pip
pip install -r requirements.txt
```

---

### ▶️ Step 4: Run the Application

```bash
uvicorn app:app --host 0.0.0.0 --port 8000
```

---

## 🌐 Access the Application

You can now access the app via:

🔸 `http://<your-vm-public-ip>:8000`  
🔸 `http://localhost:8000` (local access)

📘 **Swagger Docs:**  
Access Swagger UI at: `http://<your-ip>:8000/docs`

---

## 🔗 API Endpoints

| Method | Endpoint               | Description               |
|--------|------------------------|---------------------------|
| GET    | `/api/tasks`           | List all tasks            |
| GET    | `/api/tasks/{task_id}` | Retrieve task by ID       |
| POST   | `/api/tasks`           | Create a new task         |
| PUT    | `/api/tasks/{task_id}` | Update task by ID         |
| DELETE | `/api/tasks/{task_id}` | Delete task by ID         |

---



## ✅ Conclusion

You've successfully deployed a modern Python backend using FastAPI and Microsoft SQL Server on an Azure VM.  
Now it's ready for customization, scaling, and production!

---

## 👨‍💻 Author

**Ritesh Sharma**  
🔗 [My LinkedIn Profile](https://www.linkedin.com/in/riteshatri)
