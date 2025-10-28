# **Day 2: Splunk Architecture & Setup**

## **1️⃣ Overview of Splunk Architecture**
Splunk’s architecture is designed to efficiently collect, index, search, and visualize large volumes of data in real time.  
It is built on a **distributed system** that allows scalability, reliability, and high performance.

### **Key Workflow Stages**
1. **Data Ingestion:**  
   - Splunk collects data from a variety of sources such as servers, firewalls, applications, and IoT devices.  
   - Data can be ingested through **Forwarders**, APIs, or manual uploads.  

2. **Parsing & Indexing:**  
   - Once data is collected, Splunk parses, normalizes, and stores it in indexes for fast search and retrieval.  

3. **Searching & Reporting:**  
   - The **Search Head** allows users to query the indexed data using SPL (Search Processing Language).  
   - Results can be visualized, reported, or used to trigger alerts.  

4. **Visualization & Dashboards:**  
   - Dashboards present the analyzed data visually through charts, graphs, and panels for easy interpretation.

---

## **2️⃣ Core Components of Splunk**
Splunk consists of several components that work together to collect, process, and visualize data.

### **a) Forwarders**
- **Purpose:** Collect and send data to the Splunk Indexer.  
- **Types:**
  - **Universal (Lightweight) Forwarder:**  
    - Minimal resource usage.  
    - Used for forwarding raw data from clients or endpoints.  
  - **Heavy Forwarder:**  
    - Performs parsing and filtering before sending data to the indexer.  
    - Used in environments that require pre-processing or routing of specific logs.

### **b) Indexer**
- **Function:**  
  - Receives and processes incoming data from forwarders.  
  - Indexes the data and makes it searchable.  
- **Importance:**  
  - The heart of Splunk — it transforms raw data into searchable events.  
  - Handles storage, data compression, and metadata management.  
- **Interdependence:**  
  - Works closely with forwarders for input and the search head for queries.  
- **Performance:**  
  - Efficient indexing ensures fast searches even on large datasets.

### **c) Search Head**
- **Purpose:**  
  - Provides the web interface and processes user search requests.  
  - Distributes search queries to indexers and consolidates results.  
- **Functions:**  
  - Runs SPL queries.  
  - Generates visualizations, reports, and alerts.  
  - Manages user authentication and access control.

### **d) Cluster Master (Deployment Server)**
- **Role:**  
  - Manages indexer clustering and replication.  
  - Ensures high availability and data redundancy across indexers.  
  - Distributes configuration updates and controls deployment topology.

### **e) User Interface (Web UI)**
- **Purpose:**  
  - Provides a graphical interface for interacting with Splunk.  
  - Used to search, build dashboards, and manage configurations.  
  - Accessible via web browser at `http://<hostname>:8000`.

---
## **3️⃣ Key Features of Splunk**

- **Scalable Data Ingestion:** Handles large and diverse data sources efficiently.  
- **Powerful Search Engine:** SPL enables flexible data exploration and correlation.  
- **Custom Dashboards & Alerts:** Visualize data and get notified about key events.  
- **Machine Learning Support:** Built-in models for anomaly detection and prediction.  
- **Data Security:** Role-based access control and encryption support.  
- **Integration Capabilities:** Connects with external tools like AWS, Azure, and Kubernetes.  
- **Real-Time Analytics:** Processes live data streams for immediate insights.  

---

## **4️⃣ Splunk Installation & Configuration**

### **A. On Linux**

Splunk can be easily installed using package management tools.

**Steps:**
1. **Download Splunk:**
   wget -O splunk-10.0.1-c486717c322b-linux-amd64.deb "https://download.splunk.com/products/splunk/releases/10.0.1/linux/splunk-10.0.1-c486717c322b-linux-amd64.deb"

2. **Install Splunk:**
sudo dpkg -i splunk-10.0.1-c486717c322b-linux-amd64.deb

3. **Start Splunk Service**
sudo /opt/splunk/bin/splunk start

4. During the first startup, Splunk will prompt you to accept the license and set admin credentials.
5. Once setup is complete, open your browser and access Splunk via: URL: http://localhost:8000

**B. On Windows**

**Install and Configure Splunk**
1. Download the Installer from the Splunk official website
2. Run the Installer and follow the setup wizard.
3. Accept the License Agreement.
4. Create an Admin Account.
5. Access Splunk Web Interface:
6. Open your browser and go to: URL: http://localhost:8000
