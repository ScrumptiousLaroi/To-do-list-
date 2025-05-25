# ✅ ToDo List Java App

A simple and elegant **To-Do List application** built using **JavaFX** for the user interface and **MySQL** for backend database operations. This project is developed with **IntelliJ IDEA**, **SceneBuilder**, and utilizes **JDBC** for database connectivity.

---

## 🔧 Features

- Add, edit, and delete tasks
- Material design UI with **JFoenix**
- Persistent data storage using **MySQL**
- Modular structure managed with **Maven**

---

## 📦 Tech Stack

- **JavaFX** – GUI
- **MySQL** – Relational database
- **JDBC** – Database connectivity
- **Maven** – Dependency management
- **IntelliJ IDEA** & **SceneBuilder** – Development tools

---

## 📁 Project Setup

1. **Clone the Repository**
   ```bash
   git clone https://github.com/ScrumptiousLaroi/thetodolist-java-project.git
2.	**Set up the MySQL database:**
    Open MySQL (via CLI or a tool like MySQL Workbench) and execute the following SQL commands to create the database and table:
    ```bash
    CREATE DATABASE todo_app;
    USE todo_app;
    CREATE TABLE tasks (
        id INT AUTO_INCREMENT PRIMARY KEY,
        title VARCHAR(100) NOT NULL,
        description TEXT,
        completed BOOLEAN NOT NULL DEFAULT FALSE
    );
3.  **Configure JDBC connection:**
    In the project source (e.g., a configuration file or database utility class), update the JDBC connection settings to match your MySQL setup:
    ```bash
    String url = "jdbc:mysql://localhost:3306/todo_app";
    String user = "root";
    String password = "your_mysql_password";
    ```
    Ensure the URL, username, and password correspond to your local MySQL instance.
4.	**Install dependencies with Maven:**
    ```bash
    mvn clean install
    ```
    This command will download and install all necessary dependencies defined in the pom.xml.
5.	**Run the application:**
    ```bash
    mvn javafx:run
    ```
    You can also open the project in IntelliJ IDEA and run the Main class directly.

## 📚 Resources Used

- [OpenJFX (JavaFX) Documentation](https://openjfx.io/) – Official JavaFX documentation  
- [MySQL Documentation](https://dev.mysql.com/doc/) – Official MySQL reference manuals  
- [Scene Builder (Gluon)](https://gluonhq.com/products/scene-builder/) – Tool for designing JavaFX user interfaces  
- [Maven Official Site](https://maven.apache.org/) – Documentation for Maven build tool  
- [Java JDBC Tutorial (Oracle)](https://docs.oracle.com/javase/tutorial/jdbc/) – Guide to JDBC connectivity  
- [StackOverflow](https://stackoverflow.com/) – Community forum for troubleshooting and solutions  
- [Flaticon](https://www.flaticon.com/) and [Icons8](https://icons8.com/) – Free icons for UI design

## ⚠️ Known Issues

- **JLink & JDBC Compatibility:**  
  The MySQL JDBC driver is an automatic module (lacking a `module-info.java` file), which makes it incompatible with `jlink`. As a result, creating a custom runtime image using `jlink` fails. A common workaround is to use `jpackage`, which can include the JDBC driver by specifying it via the `--input` flag.

- **UI Thread Blocking:**  
  Currently, all database operations are executed on the JavaFX Application Thread. This may cause the UI to freeze during long-running database interactions. Future versions will offload these operations to background threads.

- **Local Database Only:**  
  The application is currently configured to work only with a local MySQL instance. Support for remote databases (e.g., cloud-hosted MySQL on AWS or Azure) is not implemented yet.

## 📄 License

This project is licensed under the [MIT License](LICENSE).  
You are free to use, modify, and distribute this software with proper attribution.
   
