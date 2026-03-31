# Repair Shop Website (Client Project)

A production website built for a local phone repair business to improve online presence and streamline customer inquiries.

> ⚠️ Note: This is a sanitized case study. Source code and business-specific details are private.

---

## 🚀 Overview

This project focused on delivering a **lightweight, high-performance website** for a repair shop with two primary goals:

- improve customer acquisition through SEO and accessibility  
- simplify customer inquiry and booking flow for repair services  

The solution was designed to be simple, scalable, and easy to maintain.

---

## 🧱 Real-World Constraints

- Non-technical client → required extremely simple content management  
- Low budget → avoided complex backend or CMS setup  
- Mobile-heavy traffic → prioritized performance and responsive UX  
- No internal system → inquiry + booking flow designed for manual processing  

---

## 🧩 Key Features

- Service catalog (screen repair, battery replacement, diagnostics)  
- Customer inquiry form with backend storage  
- Booking section for scheduling repair requests  
- Business information (location, hours, contact details)  
- Fully responsive layout (mobile-first)  
- SEO-optimized structure using Next.js  

---

## 🏗️ System Architecture

### Frontend
- Next.js (SSR / SSG for performance and SEO)  
- Component-based UI for maintainability  

### Backend (Firebase)
- Firestore: stores customer inquiries and bookings  
- Cloud Functions (optional): validation / processing  
- Hosting: production deployment  

---

## 🗄️ Data Model (Firestore)

### inquiries
```text
{
  id: string,
  serviceType: string,
  deviceModel: string,
  issueDescription: string,
  customerName: string,
  contactPhone: string,
  createdAt: timestamp,
  status: "new" | "contacted" | "completed"
}
```
### bookings
```text
{
  id: string,
  serviceType: string,
  deviceModel: string,
  preferredDate: string,
  preferredTime: string,
  customerName: string,
  contactPhone: string,
  notes: string,
  createdAt: timestamp,
  status: "pending" | "confirmed" | "completed"
}
```
---

## 🔄 Data Flow

### Inquiry Flow

1. User submits inquiry form (client-side validation)  
2. Request sent via Firebase SDK  
3. Firestore write operation (secured via rules)  
4. Optional Cloud Function triggers:  
   - input sanitization  
   - notification hook (future)  
5. Data stored in `inquiries` collection  
6. Business manually reviews entries  

### Booking Flow

1. User selects service and preferred time  
2. Inputs device and contact details  
3. Booking request sent to Firestore  
4. Stored in `bookings` collection  
5. Business manually confirms booking  

---

## ⚡ Performance Considerations

- Used SSG for static pages (faster load, better SEO)  
- Optimized images and minimized JS bundle  
- Mobile-first design reduces layout shift  
- Firebase CDN hosting for fast global delivery  

---

## 🔄 Core Workflow

### Inquiry
1. Customer selects service type  
2. Enters device details and issue description  
3. Provides contact information  
4. Form submission is validated and stored  

### Booking
1. Customer selects service  
2. Chooses preferred date and time  
3. Provides device and contact details  
4. Booking request is stored and reviewed  

---

## ⚙️ Key Technical Decisions

### Why Next.js
- SEO is critical for local business discovery  
- SSR/SSG improves search engine indexing vs SPA  

### Why Firebase
- minimal backend setup and maintenance  
- fast deployment cycle  
- suitable for small-scale data workflows  

### Trade-offs
- No admin dashboard (kept scope lean)  
- Manual booking confirmation process  
- Not designed for large-scale multi-branch systems  

---

## 🧠 Challenges & Solutions

**Challenge:** balancing simplicity vs scalability  
→ Designed Firestore schema to support both inquiries and bookings  

**Challenge:** mobile-first traffic  
→ Implemented responsive layout optimized for smaller screens  

---

## 🔮 Future Improvements

- Admin dashboard for inquiry & booking management  
- Email/SMS notification integration  
- Automated booking confirmation system  
- Multi-location support for scaling business  

---

## 🎯 Outcome

- Delivered a live production website for a local business  
- Enabled structured customer inquiries and booking requests  
- Reduced reliance on manual messaging channels  
- Established scalable foundation for future automation  

---

## 👤 My Role

- Led end-to-end delivery from requirements → deployment  
- Translated client needs into a scalable technical solution  
- Designed system architecture and data model  
- Implemented frontend, backend integration, and deployment  

---

## 🔒 Notes

- Business details are generalized for privacy  
- No sensitive data or proprietary logic is included  
