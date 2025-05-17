# SOC Analyst Project: Endpoint Detection - Login Analysis

This project demonstrates the use of Elastic Search and Kibana to analyze login activity data and detect signs of credential misuse within an enterprise environment

# Overview
YOLP.com's security team uses a commercial vulnerability scanner. The vulnerability scanner periodically logs on to every machine in the company to perform routine scanning. The vulnerability scanner is located on SEC01.YOLP.com with IP address: 10.5.55.11 . The login  id is vulscan. 
An attacker has performed a successful attack and obtained the credential of the vulnerability scanner. 
Find compromised machines by analyzing login activities of the vulnerability scanner

# Objectives

* Detect unauthorized use of the vulscan login
* Identify potentially compromised endpoints
* Determine possible source machines used in the attack

# Tools & Technology

* Elastic
* Kibana
* Log file (svclog) – Contains login event data

# Analysis Workflow

* Log Ingestion: Imported the svclog file into Elastic Cloud for investigation
 ![Log Ingestion](IngestLog.png)
* Kibana Querying: Built targeted queries to isolate logins by the vulscan account
 ![Kibana Query](images/kibana_query.png)
* Behavioral Analysis: Reviewed timestamps, source IPs, and workstation names to identify unusual login patterns
   ![Behavioral Analysis](images/behavioral_analysis.png)
* Compromised Endpoint Identification:  Pinpointed machines that were accessed using the stolen vulscan credentials outside of normal scanner behavior
  ![Compromised Endpoint](images/compromised_endpoint.png)
