# NewEdge Manager Dashboard

> Internal management platform for NewEdge restaurant operations — built for Tanger, Morocco.

## 🔐 Access
- **URL**: `https://newedge-manager.vercel.app`
- **Login**: `manager@newedge.ma` / `demo1234`
- **Visibility**: Private — manager only

## 📋 Features
- **Live Team View** — real-time staff status (working / break / leave / absent)
- **Requests Management** — approve/reject salary advances & leave requests
- **Daily Evaluations** — rate each staff member 1–10 with comments
- **Shift Planning** — set individual schedules per employee (Mon–Sun)
- **PIN Management** — configure 4-digit secret codes per employee
- **WiFi Config** — set restaurant IP for staff app access control
- **Auto Alerts** — late arrival, absent, early departure, uncovered shift
- **Invoices** — paid/unpaid tracking with AI anomaly detection
- **Monthly AI Report** — financial analyst + HR + accountant summary
- **Statistics** — revenue, food cost, covers, satisfaction charts

## 🏗️ Architecture

```
newedge-manager (this repo)     — Manager Dashboard
newedge-staff   (private repo)  — Staff App
newedge-qr      (public repo)   — Client QR Interface
```

All 3 apps share the same `window.NEWEDGE_SHARED` state object when opened in the same browser session. **Firebase integration planned for Phase 2** to enable real-time cross-device sync.

## 🗺️ Deployment

| Phase | Status | Description |
|-------|--------|-------------|
| Phase 1 | ✅ Live | Static HTML on Vercel |
| Phase 2 | 🔄 Next | Firebase Firestore + Auth |
| Phase 3 | ⏳ Planned | Custom domain `app.newedge.ma` |
| Phase 4 | ⏳ Planned | PWA — installable on iOS |

## 🔥 Firebase Integration (Phase 2)

Collections to create in Firestore:
```
restaurants/{restaurantId}/
├── staff/          — employees, PINs, salaries
├── shifts/         — weekly schedules per employee
├── clockings/      — time-in/out records
├── requests/       — advances + leave requests
├── evaluations/    — daily scores
├── alerts/         — auto-generated alerts
└── settings/       — WiFi IP, leave quotas, delays
```

## 🛠️ Stack
- **Frontend**: Vanilla HTML/CSS/JS — single file, no dependencies
- **Charts**: Chart.js (CDN)
- **Fonts**: DM Sans + DM Serif Display (Google Fonts)
- **Backend**: Firebase (Phase 2)
- **Hosting**: Vercel

## 📁 Related Repos
- [newedge-staff](https://github.com/yourusername/newedge-staff) — Staff app with PIN + WiFi access
- [newedge-qr](https://github.com/yourusername/newedge-qr) — Public client QR interface

---
Built by **NewEdge** · Tanger, Morocco · 2025
