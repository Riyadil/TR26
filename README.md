# Security Desk UI

This is the browser prototype for the CSC 4402 Cybersecurity Incident and Vulnerability Tracking System. The download uses the same HTML, CSS, and JavaScript as the hosted prototype.

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
