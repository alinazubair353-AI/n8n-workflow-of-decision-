#  Smart Decision-Based Email Automation — n8n Workflow

An intelligent n8n workflow that automatically reads data from **Google Sheets**, applies conditional logic, and routes personalized **Gmail** messages based on task priority.

---

## 📌 Workflow Overview

| Node | Type | Purpose |
|------|------|---------|
| Google Sheets Trigger | Trigger | Fires when a new row is added |
| If | Condition | Checks if priority is "high" |
| Switch | Router | Routes by priority: high / medium / lowest |
| Send a message (×4) | Gmail | Sends customized email per priority level |

---

##  Flow Diagram

```
Google Sheets Trigger (rowAdded)
        ↓
      [If Node]
     /         \
  true        false
   ↓              ↓
Send Email    [Switch Node]
(High)        /     |     \
           high  medium  lowest
            ↓      ↓       ↓
         Gmail   Gmail   Gmail
```

---

##  Features

- ✅ Auto-triggered when new row is added to Google Sheets
- ✅ Priority-based email routing (high / medium / lowest)
- ✅ 4 separate Gmail messages for different priority levels
- ✅ Fully automated — zero manual work
- ✅ Successfully tested — execution time: **11.208s**

---

##  Tech Stack

- **n8n** — Workflow Automation
- **Google Sheets** — Data Source (Trigger)
- **Gmail** — Email Delivery
- **If Node** — Boolean Condition
- **Switch Node** — Multi-branch Routing (Rules mode)

---

## Input Data (Google Sheets)

| Field | Example Value |
|-------|---------------|
| name | Alina |
| task | todo app |
| email | alinazubair353@gmail.com |
| priority | high |

---

##  Output


<img width="1356" height="677" alt="image" src="https://github.com/user-attachments/assets/d3f0da11-75db-4e27-b7a0-18f0e2a3f06d" />


- Gmail sends the appropriate email based on priority level
- Output returns: `threadId`, `id`, `labelIds: SENT`

---

##  How to Use

1. Clone or import this workflow into your n8n instance
2. Connect your **Google Sheets** account via OAuth2
3. Connect your **Gmail** account via OAuth2
4. Set your Google Sheet ID in the trigger node
5. Add a new row to your Sheet — the workflow fires automatically!

---

##  Nodes Used

```
- Google Sheets Trigger (rowAdded)
- If (Condition Node)
- Switch (Rules mode: high / medium / lowest)
- Gmail → Send a message ×4
```

---

## Author

**Alina Zubair**  
AI Automation Developer | BS Computer Science (AI)  
University of Agriculture, Gujrat, Pakistan  
