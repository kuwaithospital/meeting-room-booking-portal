# Kuwait Hospital — Meeting Room Booking Portal

**Live URL:** https://kuwaithospital.github.io/meeting-room-booking-portal/

A browser-based meeting room booking system hosted on GitHub Pages, powered by Google Apps Script as the backend.

---

## Files

| File | Purpose |
|------|---------|
| `index.html` | Main booking form — staff fill this to request a room |
| `room.html` | Tablet display — mounted outside each meeting room, shows live status |
| `coordinator.html` | Coordinator dashboard — approve/reject booking requests |
| `js/config.js` | GAS backend URL + `google.script.run` shim for GitHub Pages |
| `js/api.js` | fetch() wrapper that routes `google.script.run` calls to GAS |
| `apps-script/Code.gs` | Google Apps Script backend — paste into your GAS project |
| `logo.png` | Kuwait Hospital logo **(copy from old repo — not included)** |

---

## Tablet URLs

Open these on the tablet mounted outside each room:

| Room | URL |
|------|-----|
| Executive Hall | `https://kuwaithospital.github.io/meeting-room-booking-portal/room.html?room=Executive%20Hall` |
| Basement Meeting Hall | `https://kuwaithospital.github.io/meeting-room-booking-portal/room.html?room=Basement%20Meeting%20Hall` |
| Meeting Hall 1015 | `https://kuwaithospital.github.io/meeting-room-booking-portal/room.html?room=Meeting%20Hall%201015` |
| KHC Meeting Hall | `https://kuwaithospital.github.io/meeting-room-booking-portal/room.html?room=KHC%20Meeting%20Hall` |

---

## Setup

1. Create a new GitHub repository named `meeting-room-booking-portal` under the `kuwaithospital` organisation
2. Upload all files keeping the same folder structure (`js/` subfolder intact)
3. Copy `logo.png` from the old repository (`mdsirajudeen/meetingroom.booking`)
4. Go to **Settings → Pages → Source → Deploy from branch → main / root**
5. The site will be live at `https://kuwaithospital.github.io/meeting-room-booking-portal/`

---

## Backend

Google Apps Script (`apps-script/Code.gs`) handles all data — bookings are saved to Google Sheets and emails are sent automatically.

- Only `@kuwaithospital.com.kw` email addresses are accepted
  - Enforced in the booking form (client-side)
  - Enforced in `Code.gs` `submitBooking()` (server-side) — direct API calls are also blocked
- Bookings require coordinator approval before confirmation emails are sent

---

*Developed by Mohamed Sirajudeen — Kuwait Hospital IT Department*
