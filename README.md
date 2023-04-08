---
title: oai-reverse-proxy
emoji: 🔁
colorFrom: green
colorTo: purple
sdk: docker
pinned: false
---
<!-- -->
# OAI Reverse Proxy Server

Simple reverse proxy server for the OpenAI API.

## What is this?
If you have an API key you want to share with a friend, you can use this to keep your key safe while still allowing them to generate text with the API.

## Why?
OpenAI keys have full permissions to themselves. They can revoke themselves, generate new keys, modify your spend quotas, and so forth. You absolutely should not share them.

So, if you still want to share access to your key, you can use this to do so safely.  You can also set a separate key just for this proxy server if you want to gatekeep access.

## How to use

### 1. Get an API key
- Go to [OpenAI](https://openai.com/) and sign up for an account.

### 2. Clone this Huggingface repository to your account
- Go to [Huggingface](https://huggingface.co/) and sign up for an account.
- Once logged in, click on the `+` button in the top right corner and select `Duplicate this Space`.

![Duplicate Space](https://files.catbox.moe/3n6ubn.png)

### 3. Set your OpenAI API key as a secret
- Click the Settings button in the top right corner of your repository.
- Scroll down to the `Repository Secrets` section and click `New Secret`.

![Secrets](https://files.catbox.moe/irrp2p.png)

- Enter `OPENAI_KEY` as the name and your OpenAI API key as the value.

![New Secret](https://files.catbox.moe/ka6s1a.png)

**Do not paste the key into `server.js`!** That file is public and anyone can see it. Leave it alone; it will load the key from the secret you just created.

### 4. Deploy the server
- Your server should automatically deploy when you add the secret, but if not you can select `Factory Reset` from that same Settings menu.

### 5. Share the link
- The Service Info screen should show the URL for your server. You can share this with anyone to safely give them access to your OpenAI API key.
- If you want to protect access to the server, add another secret with the key `PROXY_KEY` using the method as for `OPENAI_KEY`.