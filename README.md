# TokenDesk  
### Service Token & WhatsApp-Based Document Request System

---

## 📌 PROJECT OVERVIEW

**TokenDesk** is a web-based service token management system designed to handle certificate and application requests in a **controlled, real-world workflow**.

Users create a token and wait.  
Admins manage the queue and request documents **only through WhatsApp**.

⚠️ The website **never handles file uploads**.

---

## 🎯 CORE GOALS

- Simple experience for users
- Full control for admin
- No website file uploads
- WhatsApp-based document handling
- Minimal, professional UI
- AI-friendly and scalable architecture

---

## 🎨 DESIGN PHILOSOPHY (LOCKED 🔒)

- Glassmorphism UI
- Dark gradient background
- Rounded cards
- Subtle animations
- Mobile-first responsiveness

🚫 **Design is FINAL**
- No CSS changes
- No color changes
- No layout refactors
- No animation changes

---

## 🧰 TECHNOLOGY STACK

### Frontend
- HTML5
- CSS3 (custom glassmorphism)
- Vanilla JavaScript

### Libraries
- Bootstrap (grid & utilities only)

### Storage
- Browser `localStorage`

### Integration
- WhatsApp Deep Links (`https://wa.me/`)

### AI Tools Used
- GitHub Copilot
- Google Antigravity

---

## 📁 PROJECT STRUCTURE

/
├── index.html # Home page
├── create.html # Create Token page
├── status.html # User Status page
├── admin.html # Admin Dashboard
├── style.css # FINAL locked design
├── logic.js # All business logic
├── motion.js # Cursor glow animation
├── onboarding.js # Hint / onboarding modal
└── README.md # Project documentation

yaml
Copy code

---

## 👥 USER ROLES

### 👤 USER
- Creates a token
- Views token status
- Uploads documents via WhatsApp only
- Has no admin controls

### 👑 ADMIN
- Manages token queue
- Requests documents
- Updates token status
- Rejects tokens
- Clears entire queue

---

## 📄 PAGES & FEATURES

### 1️⃣ Home Page (`index.html`)
- Entry point
- Buttons:
  - Create Token
  - Check Status
- No admin link visible

---

### 2️⃣ Create Token Page (`create.html`)
User inputs:
- Name
- Phone number
- Service type

On submit:
- Token generated (TD-001, TD-002…)
- Saved to localStorage
- Redirected to:
status.html?token=TD-001

yaml
Copy code

---

### 3️⃣ Status Page (`status.html`)
User sees:
- Token number
- Name
- Service
- Status text ONLY

Possible statuses:
- Waiting
- Documents Required
- Documents Uploaded
- Rejected

🚫 No upload button  
🚫 No WhatsApp trigger  
🚫 No admin actions  

Status updates dynamically via `logic.js`.

---

### 4️⃣ Admin Dashboard (`admin.html`)
Admin sees token cards with:
- Token number
- Name
- Service
- Phone number

🚫 Token status text is NOT shown in admin UI.

Admin actions:
- Request Documents
- Mark Documents Uploaded
- Reject Token
- Clear All Queue

---

## 🔁 TOKEN WORKFLOW

### User Flow
1. Create token
2. Wait
3. Receive WhatsApp message
4. Upload documents via WhatsApp
5. Check status on website

---

### Admin Flow
1. View token list
2. Request documents → WhatsApp opens
3. Mark documents uploaded
4. Reject if needed
5. Clear queue when required

---

## 📊 TOKEN DATA MODEL

```json
{
"token": "TD-001",
"name": "Rahim",
"phone": "9876543210",
"service": "Income Certificate",
"userType": "Public",
"status": "Waiting",
"requiredDocs": []
}
Stored in:

localStorage.tokens

localStorage.tokenCount

📱 WHATSAPP INTEGRATION
Uses WhatsApp deep links:

ruby
Copy code
https://wa.me/{PHONE}?text={ENCODED_MESSAGE}
Message template:

python
Copy code
Hello {Name} 👋

Your token {Token} is now active.

Please upload the following documents:
• Aadhaar Card
• Income Certificate
• Photo

Kindly send clear photos or PDFs here.
Thank you.
🚫 STRICT RULES
❌ No website file uploads

❌ No backend / database

❌ No authentication yet

❌ No design changes

❌ No token status shown in admin UI

⚠️ CURRENT LIMITATIONS
Admin page accessible via URL

Data stored locally in browser

No multi-device sync

🚀 FUTURE ENHANCEMENTS
Admin access code

Daily token limits

Family / Friends priority queue

Backend database

Cloud sync

Multi-admin support

Analytics dashboard

🤖 AI TOOL GUIDELINES (IMPORTANT)
For Antigravity, Copilot, or other AI tools:

Treat README.md as source of truth

Do NOT modify CSS without permission

Do NOT add file upload UI

Do NOT show status text in admin UI

Keep status page URL-driven

Extend logic only
