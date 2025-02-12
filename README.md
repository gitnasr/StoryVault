# StoryVault 📸 

> Your intelligent Instagram stories archive companion 🚀

A Python script that automatically monitors and archives Instagram stories from accounts you follow. It periodically checks for new stories, downloads them, and maintains a local database of archived content. Never miss a story again! ✨

## ✨ Features

- 🔄 Automatic monitoring of Instagram stories every 30 minutes
- 🎯 Intelligent duplicate detection using image hashing
- 💾 Local database storage of story metadata
- 🚀 Multithreaded image downloading
- 🔁 Automatic retry mechanism for failed requests
- 🎨 Console logging with color-coded status messages

## 🧠 Algorithm Overview

The script follows this process to archive stories:

1. **Story Discovery** 🔍
   - Fetches the list of available stories from followed accounts
   - Filters out previously archived stories using the local database
   - Groups user IDs in batches of 30 to optimize API requests

2. **Content Processing** ⚡
   - Downloads story media (currently supporting image type)
   - Generates hash of each image to prevent duplicates
   - Stores metadata including username, story ID, and timestamp
   - Saves media files in an organized directory structure

3. **Periodic Execution** ⏰
   - Runs every 30 minutes using the `schedule` library
   - Maintains persistent session with automatic retries
   - Displays next execution time after each run

## 📦 Requirements

```
requests
schedule
termcolor
colorama
```

## 🚀 Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/storysense.git
cd storysense
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Set up your Instagram cookies in the `Cookies` class implementation

## 💫 Usage

Simply run the script:
```bash
python stories.py
```

The script will:
- ▶️ Start monitoring stories immediately
- 🗃️ Create a local database if it doesn't exist
- 💾 Download new stories to a configured directory
- 🎯 Display colored console output for monitoring

## ⚙️ Configuration

The script requires several utility classes that should be implemented:
- `utils.api.API`: Instagram API endpoint management 🔌
- `utils.cookies.Cookies`: Cookie handling for authentication 🔑
- `utils.database.InstagramCache`: Local storage management 💽
- `utils.images.Images`: Image processing and saving 🖼️

## 📁 Output Structure

Stories are saved with the following structure:
```
├── stories.db         # SQLite database with metadata
└── images/           
    └── username/     
        └── story_id_timestamp.jpg
```

## ⚠️ Limitations

- Currently only supports image stories (type 1)
- Requires valid Instagram authentication cookies
- Instagram API rate limits may apply

## 🤝 Contributing

Feel free to submit issues, fork the repository, and create pull requests for any improvements.


## ⚖️ Disclaimer

This tool is for personal use only. Please respect Instagram's terms of service and content creators' rights when using this script.

---
<div align="center">
Made with ❤️ by NASR
</div>
