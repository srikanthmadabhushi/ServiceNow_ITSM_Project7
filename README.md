# ServiceNow_ITSM_Project7
AI-Simulated Incident Auto-Categorization
# ServiceNow Project: AI-Simulated Incident Auto-Categorization

## 📘 Objective
Simulate Predictive Intelligence functionality in ServiceNow to automatically categorize incidents based on keywords in the short description, and generate an AI-style summary for better analyst visibility.

## ⚙️ Steps
1. **Open Flow Designer → Create New Flow**
   - Name: `AI_Simulated_Incident_AutoCategorization`
   - Table: Incident
   - Trigger: When record created

2. **Flow Logic (If / Else If)**
   - If Short Description contains “VPN” or “Network” → Category = Network
   - Else If contains “Email” or “Outlook” → Category = Email
   - Else If contains “Password” or “Login” → Category = Access
   - Else → Category = General

3. **Update Record**
   - Set `category` = predicted_category
   - Set `u_ai_summary` =  
     ```
     AI Suggestion: Based on '${short_description}', Category auto-assigned as '${category}'.
     ```

4. **Save → Activate → Test**
   - Create a new Incident: “VPN not connecting” → Category auto-fills as *Network*  
   - “Email not working” → Category auto-fills as *Email*  

## 🤖 AI Integration
| Type | Function |
|------|-----------|
| Rule-based AI (Simulation) | Keyword logic mimics Predictive Intelligence |
| GenAI Summary | Adds readable incident summary text |
| Future Integration | Replace keyword logic with real Predictive Intelligence or REST API call to OpenAI |

## 🎯 Outcome
- Reduced manual data entry  
- Intelligent auto-categorization  
- AI-style summary improves analyst understanding  

## 🧩 Future Upgrade
When Predictive Intelligence (`com.snc.prediction_builder`) becomes available, replace the logic block with:
> **Action → Predict Classification → Model = Incident Categorization Model**

## 🖼️ Diagram
![AI-Simulated Flow](./Diagrams/Flow Diagram.png)

## 🧠 Learning Highlights
- Designed Flow Designer logic for classification  
- Applied AI concept in no-plugin PDI  
- Built scalable foundation for true GenAI automation 
