🚀 **Hello-World Project with UV & Docker**

===========================================

This guide will walk you through setting up a **Python project** using **UV** for package management and running it inside a **Docker container**.

**🛠 Prerequisites**

--------------------

Before you start, ensure you have the following installed:
* **Windows** & **Linux** [https://github.com/AnupCloud/uv/tree/main/uv_details]
* **MacOS** with **Homebrew** installed (brew)

* **Docker** (for containerization)

**📌 Setting Up the Project Using UV**

--------------------------------------

UV is a fast Python package manager that helps manage dependencies efficiently.

### **1️⃣ Install UV**

` brew install uv `

### **2️⃣ Create a New UV Project**

` uv init hello-world ` # Creates a new project named "hello-world" 

` cd hello-world ` # To go inside the directory

### **3️⃣ Project Structure**

After initialization, your project structure will look like this:
```
├── .python-version 
├── README.md 
├── main.py 
└── pyproject.toml 
```

### **4️⃣ Running the Project**

Run the project using uv:

` uv run main.py `

**📦 Managing Dependencies in UV**

----------------------------------

UV allows you to manage dependencies in your **pyproject.toml** file.

### **5️⃣ Installing Dependencies**

To add a package (e.g., requests):

` uv add requests `

### **6️⃣ Removing Dependencies**

To remove a package (e.g., requests):

` uv remove requests `

### **7️⃣ Install Dependencies from requirements.txt**

If you have a requirements.txt file, install all dependencies at once:

` uv add -r requirements.txt `

**🛠 Virtual Environment & Project Structure**

----------------------------------------------

Once you start adding dependencies, UV will create a **virtual environment (.venv)**, and your project structure will update:

```
├── .venv 
│   ├── bin 
│   ├── lib 
│   └── pyvenv.cfg 
├── .python-version 
├── README.md 
├── main.py 
├── pyproject.toml 
└── uv.lock 
```

### **8️⃣ Example pyproject.toml Configuration**

This file defines the project metadata and dependencies.

``` 
[project] 
name = "hello-world" 
version = "0.1.0" 
description = "Add your description here" 
readme = "README.md" 
dependencies = [] 
```

# Stages Of An Efficient Dockerfile

**Before running each dockerfile, place it in the leadspotr directory and the run the commands below in the same directory**

### Build `Dockerfile`
If you run into problems here, run the following commands before in your terminal:
```
export DB_PASSWORD="mydbpassword"
export DB_USER="mydbuser"
export DB_NAME="mydbname"
export DB_HOST="mydbhost"
export ACCESS_TOKEN_SECRET_KEY="mysecretkey"
```

```
docker build --secret id=DB_PASSWORD \
             --secret id=DB_USER \
             --secret id=DB_NAME \
             --secret id=DB_HOST \
             --secret id=ACCESS_TOKEN_SECRET_KEY \
             --target=production \
             -f Dockerfile.10_final . -t 10_final
```
**Running the image**
```
docker run -p 8080:8080 fast-api:1.0.01
```