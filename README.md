# HackerNews-keyword-tracker  

A **Node-RED flow** for tracking Hacker News stories by keywords, ranking them by hotness (score + comments), and delivering a daily Top-20 digest per keyword via e-mail.  

---

## ✨ Features  
- 🔍 Multi-keyword filtering (comma-separated input)  
- 📈 Hotness score (weighted by points & comments)  
- 🏆 Top 20 stories per keyword (deduplicated)  
- 📧 Daily digest via e-mail (HTML format)  
- 🖥️ Optional front-end dashboard (keyword input, results table)  
- ⏰ Configurable schedule (default: weekdays at 09:30 AM)  
- ✅ Works with official Hacker News API  

---

## 📋 Requirements  
- **Node.js** (LTS)  
- **Node-RED ≥ 3.x**  

### Palettes  
- `node-red-dashboard`  
- `node-red-node-email`  
- `node-red-node-ui-table` *(optional)*  

---

## 🚀 Installation  

### 1. Install Node-RED  
```bash
npm install -g --unsafe-perm node-red
node-red
```

Then open [http://localhost:1880](http://localhost:1880).  

### 2. Import the flow  
- Menu → Import → select `flows/hackernews-keyword-tracker.flow.json`  

### 3. Install required palettes  
Use **Manage palette** to install missing nodes.  

### 4. Configure the e-mail node  
- **SMTP server**: e.g. `smtp.gmail.com`  
- **Port**: `465` or `587`  
- **Username**: your email address  
- **Password**: app-specific password (not your login password)  
- **Recipient address**: target e-mail  

### 5. Deploy and test 🚦  

---

## ⚙️ Configuration  

### Keywords  
- Enter keywords in Dashboard input, or set via `.env`:  
```env
KEYWORDS=AI,IoT,UNS,iOS
```

### Schedule  
- The **Inject** node is preconfigured for `09:30` on weekdays.  
- Adjust if needed.  

### Hotness formula  
- Default:  
```js
score * 0.5 + comments * 0.5
```
- You can edit inside the **function node**.  

### Time window  
- Only includes stories from the **last 24h**.  

---

## 📸 Screenshots  

- Dashboard view
  <img width="1920" height="953" alt="UI" src="https://github.com/user-attachments/assets/800eaca0-05b8-4872-a6b7-8c21894fe893" />
- Daily digest e-mail
  <img width="1600" height="848" alt="image" src="https://github.com/user-attachments/assets/5902a01d-188f-494a-8ec4-81b07e493fc0" />
- Node-RED flow overview
  <img width="1633" height="956" alt="Nodes Flow Diagram" src="https://github.com/user-attachments/assets/0ebf934b-6a15-459c-9698-48035fa61bc4" />


---

## 📄 License  
[MIT License](LICENSE)  
