# Multithreaded-Webserver-
# Multithreaded Web Server & Deadlock Detector

This repository contains a **Multithreaded System Project** implemented in **Java** using **Java Swing** for the graphical user interface. The project demonstrates core concepts of concurrent programming, including creating a multithreaded web server and simulating/detecting deadlocks.

---

## 🚀 Features

The project is divided into two main components accessible via the GUI: a **Multithreaded Web Server** and a **Deadlock Simulator & Detector**.

### 1. Multithreaded Web Server (`multi/Server.java`, `multi/Client.java`, `multi/Frontend.java`)

* **Multithreaded Server:** The `Server` class listens on a specified port and handles each incoming client connection (`java.net.Socket`) by launching a **new `Thread`**. This ensures that the server can handle multiple clients concurrently.
* **Client Implementation:** The `Client` class can connect to the server and send a message.
* **GUI Frontend:** The `Frontend` class provides a user-friendly Swing interface to:
    * Specify the **port number** (default: 8080).
    * **Start the server** in a separate thread.
    * Specify the **number of requests** (concurrent clients) to send.
    * **Send multiple concurrent client requests** to test the server's multithreading capability.

### 2. Deadlock Simulator & Detector (`multi/Sharedresource.java`)

* **Deadlock Simulation:** The `Sharedresource` class simulates a classic **deadlock scenario** involving two threads (`Thread-1` and `Thread-2`) that attempt to acquire two locks (`lock1` and `lock2`) in a cyclic order.
    * Thread 1: `synchronized(lock1)` then `synchronized(lock2)`.
    * Thread 2: `synchronized(lock2)` then `synchronized(lock1)`.
* **Deadlock Detection:** The application uses Java's **`ThreadMXBean.findDeadlockedThreads()`** method to detect if a deadlock has occurred among the JVM's threads. The output pane reports whether a deadlock was detected and lists the names and blocked resources of the involved threads.

---

## 🛠️ Getting Started

### Prerequisites

* **Java Development Kit (JDK) 8 or newer** is required.
* An IDE (like IntelliJ IDEA, Eclipse, or VS Code) is recommended for easy compilation and execution.

### Running the Project

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/akshatpant/Multithreaded-Webserver-.git](https://github.com/akshatpant/Multithreaded-Webserver-.git)
    cd Multithreaded-Webserver-/Multithreaded-Webserver--main
    ```

2.  **Compile the Java files:**
    ```bash
    # Assuming you are in the Multithreaded-Webserver--main directory
    javac multi/*.java
    ```

3.  **Execute the main application:**
    The entry point is the `Front` class, which launches the initial Welcome GUI.
    ```bash
    java multi.Front
    ```

### Usage Steps

1.  **Welcome Screen:** Click **"Move to Next Page"** to access the main application interface (`Frontend`).
2.  **Server Frontend:**
    * Enter a **Port** number (e.g., `8080`).
    * Click **"Start Server"**.
    * Enter the desired number of **Requests** (e.g., `5`).
    * Click **"Send Requests"** to see multiple clients connect concurrently.
3.  **Deadlock Detector:**
    * From the **Server Frontend**, click the **"Next"** button to open the Deadlock Detector (`Sharedresource`).
    * Click **"Start Deadlock Simulation"** to initiate the two competing threads.
    * Click **"Check Deadlock"** to determine if the threads have entered a deadlock state.

---

## 📂 Project Structure
