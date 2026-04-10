#  Security Metrics and Executive Reporting (SOC Project)

##  Objective
This project focuses on evaluating Security Operations Center (SOC) performance using key metrics such as Mean Time to Detect (MTTD), Mean Time to Respond (MTTR), and False Positive Rate. The dashboard was built using Wazuh (Elastic Stack), and analysis was performed using Google Sheets.



##  Tools Used
- Wazuh (Elastic Security Dashboard)
- Google Sheets
- Google Docs



##  Metrics Dashboard

A time-series dashboard was created in Wazuh to visualize alert trends and severity distribution.

### Key Metrics:
- **MTTD (Mean Time to Detect):** 2 hours  
- **MTTR (Mean Time to Respond):** 4 hours  
- **False Positive Rate:** 15%  



##  Dashboard Features
- Alerts Timeline (Date Histogram with hourly interval)
- Severity-based filtering (`rule.level >= 5`)
- Line chart visualization (non-stacked for clarity)
- SOC trend analysis over 7 days


##  Metrics Analysis
Dwell time was calculated using detection timestamps from Wazuh alerts.

- Example:
  - Attack Start Time: 10:00 AM
  - Detection Time: 12:00 PM
  - Dwell Time: 2 hours



##  Key Insights
- Detection performance is moderate (MTTD = 2 hrs)
- Response time needs improvement (MTTR = 4 hrs)
- False positives indicate need for alert tuning



##  Recommendations
- Implement automated incident response (SOAR)
- Improve detection rules in Wazuh
- Reduce false positives via tuning
- Integrate threat intelligence feeds


This project demonstrates the ability to analyze SOC performance metrics and present actionable insights using real-time security monitoring tools.
