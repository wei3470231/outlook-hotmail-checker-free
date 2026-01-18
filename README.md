# Outlook/Hotmail Account Checker

A high-performance, stable, and easy-to-use tool for verifying the validity of Microsoft accounts (Outlook, Hotmail, Live, MSN).

## ✨ Key Features
- **Fully Automated**: Handles complex multi-stage OIDC login flows automatically.
- **Concurrent Processing**: Supports multi-threaded checking (Free version is hardcoded to 5 threads).
- **Account Intelligence**: Automatically fetches account region (`CountryCode`) and subscription info (`Expires`) upon successful login.
- **Cookie Management**: Optional saving of session cookies for post-check usage.
- **Smart Result Categorization**: Automatically sorts accounts into `output/` directory (Success, Locked, Password Error, Not Exist, etc.).
- **Security & Stability**: Built-in single-instance detection and console "Quick Edit" prevention to ensure uninterrupted execution.
- **Debug Ready**: Sequential raw POST response logging for deep protocol analysis and failure HTML source dumping.

## 🚀 Quick Start
1. **Prepare Accounts**: Put your accounts in `hotmail.txt` (or your custom file) using the format `email:password`.
2. **Setup Proxies**: Add your proxies to `proxy.txt` (one per line). Leave empty for direct connection.
3. **Configure**: Update `config.json` to set your thread count and file paths.
4. **Run**: Double-click `hotmail_checker.exe` or `hotmail_checker_5threads.exe` to start.

## ⚙️ Configuration Detail (`config.json`)
```json
{
    "threads": 10,              // Number of concurrent threads for processing accounts.
    "accounts_file": "hot.txt", // Source file for accounts (Format: email:password).
    "proxy_file": "proxy.txt",  // Proxy list file (one per line). Supports empty/direct.
    "ok_file": "output/ok.txt", // Storage for successfully authenticated accounts.
    "lock_file": "output/lock.txt",     // Storage for accounts detected as 'Locked'.
    "pwd_err_file": "output/pwd_err.txt", // Storage for 'Password Incorrect' results.
    "not_exist_file": "output/not_exist.txt", // Storage for accounts that do not exist.
    "retry_over_file": "output/retry_over.txt", // Results that failed after max retries.
    "err_file": "output/err.txt",       // Other unexpected error logs.
    "retry_count": 10,          // Max retries for network/proxy failures before giving up.
    "save_html_log": true,      // If true, dumps full HTML on failure to 'log/' directory.
    "save_cookies": true,       // If true, saves session cookie JSON to 'output/cookies/'.
    "enable_log": false         // Toggle detailed console [DEBUG] output for packet analysis.
}
```

## 📂 Project Structure
- `output/`: Categorized results (`ok.txt`, `lock.txt`, etc.).
- `output/cookies/`: Session cookies for successful accounts.
- `debug/`: Raw protocol response logs for each step.
- `log/`: HTML source files of failed login attempts.

## 🔗 Contact & Links
- **GitHub Repo**: [outlook-hotmail-checker-free](https://github.com/wei3470231/outlook-hotmail-checker-free)
- **Telegram Channel**: [@DAMOMANIS_MAIL](https://t.me/DAMOMANIS_MAIL)

---
*Note: The free version is strictly limited to a maximum of 5 threads.*
