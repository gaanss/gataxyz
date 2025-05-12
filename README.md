<p align="center">
  <a href="https://t.me/gans_software">
    <img src="https://img.shields.io/badge/Telegram-Channel-blue?style=for-the-badge&logo=telegram" alt="Telegram Channel">
  </a>
  <a href="https://t.me/ganssoftwarechat">
    <img src="https://img.shields.io/badge/Telegram-Chat-blue?style=for-the-badge&logo=telegram" alt="Telegram Chat">
  </a>
</p>

# GATA.xyz Automation 🚀
<p align="center">
  <img src="interface.png" alt="Interface Screenshot" />
</p>

> **⚠️ Paid Script**  
> This tool is paid. To purchase a license, please contact us via Telegram DM: @gaansss

A fully asynchronous Python 3.11+ tool that perfectly replicates the GATA.xyz AI model's functionality. This automation tool interacts with the GATA ecosystem with identical logic as the official GATA.xyz platform.

## Features ✨
- ⏱️ **Random Breaks**: Setting breaks throughout the day to simulate real user behavior
- 🔐 **Authentication**: Authentication with token management
- 🤖 **AI Model Integration**: Local ONNX runtime for advanced AI model processing 
- 🔄 **Asynchronous Operation**: Efficient concurrent processing with rate limiting
- 🌐 **Proxy Support**: Per-account proxy assignment
- 🔒 **Captcha Solving**: CapSolver integration for Turnstile
- 🗄️ **Database Storage**: PostgreSQL for secure credential and token storage
- 📊 **Stats Tracking**: Complete points and task completion tracking
- 📜 **Comprehensive Logging**: Detailed error handling and process tracking

## Prerequisites 📋
- Python 3.11
- PostgreSQL database
- CapSolver API key for captcha solving
- Required input files in `data/` directory

## Installation ⚙️
1. **Clone repository**:
   ```bash
   git clone https://github.com/gaanss/gataxyz.git
   cd gataxyz
   ```

2. **Create a virtual environment**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

## Configuration 📝
Edit `settings.yaml` to match your environment:
```yaml
db:
  url: postgresql://user:password@host:port/database

throttle:
  min_delay: 10
  max_delay: 20

concurrency:
  max_concurrent_accounts: 3

invite:
  use_database: false  # Set to true to source invites from the database instead of file

farming:
  keys_file: "data/farming.txt"
  result_delay: 300
  capsolver_api_key: "YOUR_CAPSOLVER_API_KEY"
  random_breaks_enabled: false  # Enable random breaks per day to mimic real user behavior
  breaks_per_day: 3            # Number of breaks per 24h
  min_break_duration: 300      # Minimum break duration in seconds
  max_break_duration: 1800     # Maximum break duration in seconds
```

## Data Files Structure 📂
- **`data/private_key.txt`**: One private key per line for authentication
- **`data/farming.txt`**: One private key per line for farming accounts
- **`data/proxies.txt`**: One proxy per line in format `user:pass@host:port`
- **`data/invite_code.txt`**: One invite code per line for registration invitations (used when `invite.use_database` is `false`)

## Usage 🚀
```bash
python main.py
```

The interactive menu allows you to:
1. Authorize accounts
2. Start farming mode
3. Export statistics
4. Exit

## Important Note ⚠️
This code completely replicates the functionality of the GATA.xyz AI model with 1:1 logic. It uses the same authentication flow, interaction patterns, and AI processing capabilities as the official platform.

## License 📄
This project includes a license verification system. A valid license key is required to run the application.

## Logging 📜
- Uses `loguru` with extensive logging
- Logs stored in `logs/app.log`
- Console output with colorized level indicators