# 🍷 Savoria Bistro | Frontend Client Application

Modern, responsive web application for the **Restaurant Table Reservation System** built with **React.js**, **Vite**, **Bootstrap 5**, **React Router 6**, and **Axios**.

---

## 🌟 Highlights
- **Fine-Dining UI/UX:** Luxury dark charcoal (`#18191c`), warm amber gold (`#c28833`), and responsive typography (Playfair Display + Outfit).
- **Multi-Role Dashboards:** Customized experiences for **Customers**, **Branch Staff**, and **System Administrators**.
- **1-Click Jury Demo Login:** Dedicated fast-authentication panel on `/login` to test all 3 roles without manual typing.
- **Real-Time Interactive Booking:** Live availability lookup, party-size capacity feedback, and date constraints (30-day window).
- **Official PDF Pass Generation:** Instant printable and downloadable PDF confirmation passes powered by `jspdf` and `jspdf-autotable`.

---

## 🛠️ Technology Stack
- **Framework:** React 18 (Hooks, Context API)
- **Bundler:** Vite 6
- **Styling:** Bootstrap 5.3 + Bootstrap Icons + Custom Savoria CSS
- **Routing:** React Router DOM 6 (Protected role-based routes)
- **HTTP Client:** Axios (automatic JWT injection & 401 handling)
- **Document Generation:** jsPDF + jsPDF-AutoTable

---

## 📂 Project Architecture

```
frontend/src/
├── components/          # Reusable UI components (Navbar, Footer, ProtectedRoute)
├── context/             # Authentication & User state management (AuthContext)
├── pages/               # Application views
│   ├── HomePage.jsx                     # Hero banner, highlights, location cards
│   ├── AboutPage.jsx                    # Culinary story and architecture briefing
│   ├── BranchListPage.jsx               # Branch directory with search and seating filters
│   ├── BranchDetailPage.jsx             # Detailed branch table layout & hours
│   ├── LoginPage.jsx                    # Sign-in form + 1-Click demo jury buttons
│   ├── RegisterPage.jsx                 # Customer self-registration
│   ├── ProfilePage.jsx                  # Personal account information editor
│   ├── CustomerDashboard.jsx            # Active reservations & notification feed
│   ├── NewReservationPage.jsx           # Live slot picker & auto table allocator
│   ├── MyReservationsPage.jsx           # Upcoming, past, and cancelled bookings
│   ├── ReservationConfirmationPage.jsx  # Booking summary & PDF pass trigger
│   ├── StaffDashboard.jsx               # Branch-restricted floor bookings desk
│   ├── StaffTodayPage.jsx               # Today's printable guest run-sheet
│   ├── AdminDashboard.jsx               # Executive KPI counters & branch summaries
│   ├── ManageBranchesPage.jsx           # Branch creator, editor & activation toggle
│   ├── ManageTablesPage.jsx             # Table layout & capacity configurator
│   ├── ManageStaffPage.jsx              # Staff user accounts management
│   ├── AllReservationsPage.jsx          # Master reservation registry with filters
│   └── ReportsPage.jsx                  # Visual operational analytics
├── services/            # Axios API singleton (`api.js`)
├── styles/              # Global luxury theme (`custom.css`)
├── utils/               # PDF pass generator (`pdfGenerator.js`)
├── App.jsx              # Routing definition
└── main.jsx             # DOM mounting
```

---

## 🚀 Getting Started

### 1. Install Dependencies
```bash
npm install
```

### 2. Configure Backend Proxy
The development server proxies `/api` requests to `http://localhost:5000` via `vite.config.js`:
```javascript
export default defineConfig({
  plugins: [react()],
  server: {
    port: 5173,
    proxy: {
      '/api': {
        target: 'http://localhost:5000',
        changeOrigin: true,
      },
    },
  },
});
```

### 3. Run Development Server
```bash
npm run dev
# Running at http://localhost:5173
```

### 4. Build for Production
```bash
npm run build
# Outputs optimized production assets to dist/
```

---

## 🔑 Demo Access Credentials (1-Click on Login Screen)
- **Admin:** `admin@restaurant.com` / `Admin@123`
- **Downtown Staff:** `staff.downtown@restaurant.com` / `Staff@123`
- **Seaside Staff:** `staff.seaside@restaurant.com` / `Staff@123`
- **Customer:** `customer@example.com` / `Customer@123`
