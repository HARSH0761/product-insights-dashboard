 # Container Image Vulnerability Scanner – Product Requirement Document & Wireframes


## 🚀 Overview

 This product aims to provide visibility into container image vulnerabilities stored in a repository. The system allows users to quickly identify which images are vulnerable, assess their severity, and take remediation actions.
With thousands of container images to manage, the product offers smart grouping, filtering, and alerting to ensure users can act effectively and efficiently.


---
## Goals

- Enable users to scan container images and view associated vulnerabilities.
- Prioritize vulnerabilities by severity (Critical, High, Medium, Low).
- Allow users to filter, search, and sort container images based on vulnerability data.
- Provide remediation suggestions.
- Offer insights into compliance status and security trends over time.
- Enable dashboard customization based on roles and teams.

---

## Target Users

- DevOps Engineers
- Security Engineers
- Engineering Managers
- Compliance Officers

---
## Key Features

### 1. Image Vulnerability Dashboard

- Summary cards for:
  - Total container images
  - Total vulnerabilities
  - Critical/High/Medium/Low vulnerability counts
  - Images requiring immediate attention
- Graph: Vulnerability trend over time
- Compliance score widget

### 2. Image List View

- Table format showing:
  - Image name
  - Last scanned date
  - Number of vulnerabilities by severity
  - Compliance status (Pass/Fail)
- Filtering options:
  - By severity
  - By compliance status
  - By namespace/repository
- Sorting by last scanned, severity, image name

### 3. Image Detail Page

- Image metadata: name, tag, size, last updated, base image
- Vulnerability list with:
  - CVE ID
  - Severity level
  - Description
  - Fix version (if available)
- Button to trigger re-scan
- Remediation suggestions

### 4. Compliance Insights

- Map each image’s vulnerabilities to compliance frameworks (e.g., CIS Benchmarks, NIST)
- Compliance scoring
- Downloadable compliance reports

### 5. Trends and Analytics

- Vulnerability trend over time (line chart)
- Top 5 most vulnerable images
- Vulnerability distribution by repository/team
- Weekly delta in vulnerability count

### 6. Customizable Dashboard

- Widgets can be rearranged based on user preference
- Team-based dashboards with access controls
- Exportable views (PDF/CSV)

---


## Additional (Bonus) Deliverables

### Suggested Dev Action Items

- Build backend image scanning scheduler using open-source scanner (like Trivy or Clair).
- Store scan results in a time-series database for trend tracking.
- Implement REST APIs for frontend consumption.
- Build frontend in React or Vue.js for dynamic filtering and data rendering.
- Integrate compliance rule engine (mapping CVEs to frameworks).
- Set up CI/CD pipeline for continuous scanning of new images.

---

## Tech Stack Recommendations

- **Frontend**: React + Redux
- **Backend**: Node.js or GoLang
- **Scanning Tool**: Trivy or Clair
- **Database**: PostgreSQL + InfluxDB (for time-series trends)
- **Auth**: OAuth2.0 / SSO integration
- **Deployment**: Kubernetes with Helm Charts

---

## Success Metrics

- Time taken to identify and resolve critical vulnerabilities.
- Reduction in non-compliant images over time.
- User adoption across teams.
- Reduction in Mean Time to Remediation (MTTR).
- Increase in compliance score.

---

## Future Enhancements

- SLA tracking for vulnerabilities.
- Slack/Email alerts for critical vulnerabilities.
- AI-based prioritization engine for vulnerabilities.
- Integration with CI pipelines for pre-deployment checks.

---

 ## 🧭 User Flow

 graph LR
A[User Logs In] --> B[Views Dashboard Summary]
B --> C[Checks Scanned Images List]
C --> D["Applies Filters (Severity, Compliance, Date)"]
D --> E[Opens Image Details Page]
E --> F[Reviews CVE List & Fix Recommendations]
F --> G[Downloads Fix Scripts / Applies Patches]
G --> H[Triggers Re-Scan or Schedules Future Scan]
H --> I[Monitors Security Trends & Compliance Reports]

