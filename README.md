
---

# 📥 Telegram Media Downloader (Jupyter Notebook)

This Jupyter notebook provides a complete solution to **download all media files** (photos, videos, documents, etc.) from a **Telegram group or chat**, using the powerful [Telethon](https://github.com/LonamiWebs/Telethon) Python library.

## 🧩 Features

* Connect to Telegram using your own API credentials.
* Join a group using an invite link (even private groups).
* Automatically download **all available media** in a chat or group.
* Support for **both group invitation links** and **username/chat ID targeting**.
* Compatible with **Jupyter Notebooks** and standalone `.py` execution.

---

## ⚙️ Setup Instructions

### 1. Install Required Libraries

Run these commands to install dependencies:

```bash
!pip install telethon
!pip install nest_asyncio
```

### 2. Prepare Your Telegram API Credentials

Go to [https://my.telegram.org](https://my.telegram.org), log in, and generate:

* **API ID**
* **API Hash**

Replace `your_api_id` and `your_api_hash` in the code accordingly.

---

## 📂 Usage

### Option A: Download media from a group invite link

```python
invite_link = 'https://t.me/+someInviteHash'
```

* The notebook will:

  * Try to join the group.
  * Search for the group.
  * Download media to the `downloaded_media` folder.

To run inside Jupyter:

```python
await main()
```

To run as a standalone script, replace the final line with:

```python
asyncio.run(main())
```

---

### Option B: Download media from a normal chat

```python
chat_target = 'username_or_chat_id'
```

* This allows downloading from:

  * Public groups
  * Channels
  * Private chats (if you are a participant)

---

## 💾 Output

All downloaded files will be saved in the `downloaded_media` folder with filenames like:

```
<message_id>_<timestamp>
```

Example:

```
123456_20240523_145300.jpg
```

---

## 🔐 Session Info

The session is created in-memory using `StringSession`. You can optionally save the session string:

```python
print("Session string:", session.save())
```

This allows you to resume sessions without re-login.

---

## 🧠 Notes

* This notebook is designed for educational and personal backup purposes only.
* Make sure to comply with Telegram’s Terms of Service when downloading content.
* If using `.py` scripts, replace `await main()` with `asyncio.run(main())`.

---

## 📜 License

This project is provided as-is under the MIT License.

---


