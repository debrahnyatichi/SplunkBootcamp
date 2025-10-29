🧠 **DAY 3: Mastering Splunk Searching**

**1️⃣ Fundamentals of Splunk Search Syntax**

Splunk’s Search Processing Language (SPL) is key to finding, analyzing, and visualizing data.  
SPL consists of commands, functions, and operators.

**Use search keywords such as:**
- index  
- sourcetype  
- source  
- host  

Combine searches with logical operators AND, OR, and NOT for precision.

**Example searches:**
index=* index=test status=200 OR action=purchase

**2️⃣ Filtering and Precise Field Extraction**

Use the **where** command for advanced filtering of events.  
Use the **rex** command to extract custom fields using regular expressions.

**Examples:**
index="main" | where status=404  
index="web_logs" | rex "user=(?<username>\w+)"

**3️⃣ Transforming Data into Actionable Reports**

Use the **stats** command for data aggregation.  
Functions like count, sum, avg, max, and min are helpful.  

The **timechart** command supports time-series analysis, with functions like avg() and sum().  

Generate reports with tables and fields, and make visuals with charting commands.  
Goal: Aggregate → Analyze → Visualize  

**Examples:**
index="main" | stats count by code  
index="main" | stats count by host  
index="main" | chart count by status, clientip  
index="main" | timechart span=1d count by status  
index="firewall" | where src_ip="10.0.0.5" AND action="blocked"  
index="firewall" | stats sum(bytes) by src_ip  
index="main" | timechart span=1h count by status  
index="main" | chart count by status, clientip  

**4️⃣ Website Tracking**

For web traffic analysis, use logs from Apache or Nginx web servers.

**Examples:**
index="web" sourcetype="access_combined" status=200 | stats count by uri_path  
index="web" sourcetype="access_combined" | timechart count by status
