# Security Desk

This is the browser prototype for the CSC 4402 Cybersecurity Incident and Vulnerability Tracking System. The download uses the same HTML, CSS, and JavaScript as the hosted prototype.

## System features

Security Desk gives an IT security team one place to record what happened, identify affected assets, assign investigations, and track fixes.

| Screen | What you can do |
| --- | --- |
| **Overview** | See counts of unresolved incidents, critical vulnerabilities that still need remediation, and active assets. Review recent incidents and see the percentage of remediation tasks completed. |
| **Incidents** | Report a security event, set its severity, link an affected asset, and assign an analyst. Track the investigation from **Open** to **Investigating** to **Resolved**. |
| **Vulnerabilities** | Log a finding against an asset, rate it **Low**, **Medium**, **High**, or **Critical**, and track it as **Open**, **In progress**, or **Remediated**. |
| **Assets** | Maintain an inventory of servers, databases, endpoints, and services. Mark assets **Active** or **Retired** and select them when recording incidents and findings. |
| **Analysts** | Maintain the personnel directory used to assign incidents and remediation work. Each analyst record includes a name and a job role such as **Incident responder** or **Security engineer**. |
| **Remediation** | Create a task for a vulnerability, assign it to an analyst, and track it as **Open**, **In progress**, or **Completed**. |
| **Reports** | Review unresolved incidents, critical vulnerabilities that still need remediation, and completed tasks as a share of all remediation tasks. Reports update as demo records change. |

The five record screens support searching by record ID, name or title, and linked names where available. Status and severity filters appear where those fields apply. Administrators can add, edit, and delete records. The demo blocks deletion of a record while other records still reference it.

The sign-in screen demonstrates three levels of access. **Administrators** manage all five record screens and assign work. **Security analysts** can report incidents, log vulnerabilities, and change the status of their assigned incidents and remediation tasks. **Viewers** can browse, search, and filter records and read reports.

### Example workflow

Sign in as **Administrator**, add a vulnerability linked to an asset, and create a remediation task for it. Assign that task to **Maya Chen**. Log out and sign in as **Security analyst** to mark the task **Completed**. Open **Reports** to see the updated remediation count.

## Run on Windows

1. Right-click the ZIP in File Explorer and choose **Extract All**.
2. Open the extracted **Security-Desk-UI** folder and double-click **index.html**. Windows will open it in your default browser. You can also right-click the file and choose **Open with** to select Edge or Chrome.
3. Under **Fill in demo credentials**, choose **Administrator**, **Security analyst**, or **Viewer**. Click **Sign in**. Use **Log out** to switch roles.

Opening the file requires no Node.js, npm, PostgreSQL, or build step. If the browser limits storage for locally opened files, use the local server below. The page uses web fonts when available and falls back to system fonts.

### Run on localhost with Python if installed

In File Explorer, open the folder containing **index.html**. Click the address bar, type **powershell**, and press Enter. Run:

```powershell
py -m http.server 8000 --bind 127.0.0.1
```

Open **http://127.0.0.1:8000/** in your browser. Press **Ctrl+C** in PowerShell to stop the server. If Windows does not recognize **py** and you have Python installed as **python**, replace **py** with **python**. If you do not have Python, open **index.html** directly.

## Try the three roles

| Role | What to check |
| --- | --- |
| Administrator | Open **Assets**, select **Add asset**, save a sample asset, and confirm it appears in the table. Administrators can also assign incidents and remediation tasks. |
| Security analyst | Sign in as Maya Chen. Edit **Suspicious sign-in activity** to change its status. **Unusual outbound traffic**, assigned to Jordan Ellis, appears as **View only**. |
| Viewer | Open **Incidents** or **Reports**. You can browse and filter records, with read-only access. |

Demo changes use browser storage when available. The hosted URL, local file, and localhost can show separate saved data. This is a demo login. Real sessions and permission checks will be implemented in the Node.js API backed by PostgreSQL. Use synthetic data in this version.

## Edit the UI

Open **index.html** in VS Code. The HTML defines the sign-in form and workspace. The **style** block controls the layout and colors. The **script** block handles demo accounts, sample records, forms, filters, and reports. Search for **defaults** to find the sample records, **specs** for form fields, and **canCreate** and **canEdit** for the demo permission rules. Save the file and refresh the browser.
