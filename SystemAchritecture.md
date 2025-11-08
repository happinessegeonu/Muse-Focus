# System Architecture — Muse-Focus

## Overview
- Muse-Focus is a web application that connects with the **Muse headband** to measure calmness and focus signals.
- The system collects sensor data, processes it, and presents simple insights to users, helping them build consistent calm-focus habits.
- The architecture ensures smooth communication between the device, frontend, backend, and database while keeping the system **scalable** and **maintainable**.

---

## Architecture Summary
- **Frontend:** React.js (Next.js optional)  
- **Backend:** Node.js + Express  
- **Database:** MongoDB  
- **Device Integration:** Muse SDK (BLE / OSC data stream)  
- **Hosting:** Vercel (Frontend), Render / Railway (Backend)  
- **Authentication:** JWT (JSON Web Tokens)  

---

## System Flow

### Device Connection
- User connects **Muse headband** via Bluetooth  
- SDK streams **EEG signal** + **calmness markers** to browser  

### Data Collection & Processing
- Real-time data captured in **frontend**  
- **Scoring algorithm** converts signal into **Focus Score**  
- Session summary sent to **backend** for storage  

### Backend Processing
- User authentication via **JWT**  
- Receive session data  
- Save session logs

# System Architecture — Muse-Focus

## Overview
- Muse-Focus is a web application that connects with the **Muse headband** to measure calmness and focus signals.
- The system collects sensor data, processes it, and presents simple insights to users, helping them build consistent calm-focus habits.
- The architecture ensures smooth communication between the device, frontend, backend, and database while keeping the system **scalable** and **maintainable**.


## Architecture Summary
- **Frontend:** React.js (Next.js optional)  
- **Backend:** Node.js (Express) 
- **Database:** PostgreSQL 
- **Device Integration:** Muse SDK (BLE / OSC data stream)  
- **Hosting:** Vercel (Frontend), Render / Railway (Backend)  
- **Authentication:** JWT (JSON Web Tokens)  



## System Flow

### Device Connection
- User connects **Muse headband** via Bluetooth  
- SDK streams **EEG signal** + **calmness markers** to browser  

### Data Collection & Processing
- Real-time data captured in **frontend**    
- Session summary sent to **backend** for storage  

### Backend Processing
- User authentication via **JWT**  
- Receive session data  
- Save session logs, mood notes, and streaks  
- Handle score history requests  

### Database Structure
**Collections:**
- Users  
- Sessions  
- Scores  
- Reflections  
- Streaks  
- Achievements (future enhancement)  

**Each Focus Session document contains:**
```json
{
  "userId": "string",
  "timestamp": "ISODate",
  "duration": "number",
  "focusScore": "number",
  "calmnessTrend": "array",
  "userReflectionText": "string (optional)"
}

## Key Integrations
- **Muse SDK / Bluetooth Web API:** Captures EEG and calmness signals from the Muse device
- **Chart.js / Recharts:** Visualize weekly focus trends and progress
- **Mongoose:** Database schema management and queries


**Explanation:**
- Muse Device streams EEG data to the browser in real time
- Frontend handles visualization and user interaction
- Backend API processes session data, calculates scores, and stores logs
- MongoDB serves as the persistent storage for user history and analytics
- JWT Auth ensures secure user sessions


## Technical Feasibility
- Muse hardware already provides accurate EEG and focus metrics
- Node.js + MongoDB stack is lightweight, scalable, and easy to maintain
- React frontend can handle real-time updates using Web Bluetooth API
- Cloud hosting (Vercel / Render) ensures high availability and easy deployment
- Modular architecture allows adding new features (notifications, analytics) without major refactoring

## MVP Scope (Engineering)
- Connect the **Muse device**
- Start/stop focus sessions
- Convert signal → **Focus Score**
- Save session data
- Show streaks + weekly chart

---

## Later Enhancements
- Guided breathing audio
- Leaderboards (optional)
- AI-generated focus insights


## Conclusion
This architecture ensures **Muse-Focus** is technically feasible, lightweight, and scalable.  
We rely on **proven tools and existing SDKs**, keeping our focus on delivering a **calm and intuitive experience** for students and professionals.
