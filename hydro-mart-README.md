# Hydro Mart 💧

A cross-platform mobile application that connects customers with local RO (Reverse Osmosis) water plants, enabling seamless water delivery order management with optimized delivery routing.

> **Final Year Project** — Iqra University, BS Computer Science (Batch 2020–2024)  
> **Team:** Arham Ali, Tilal Ahmed, Mirza Humza Saeed  
> **Supervisor:** Syed Jamal Haider Zaidi (Assistant Professor)

---

## Key Features

- **Role-based access** — separate flows for Customers, Supervisors, and Riders
- **Google Maps integration** — customers view nearby RO plants and place orders by location
- **TSP Route Optimization** — Branch & Bound algorithm finds the shortest delivery route across multiple stops, achieving ~25% reduction in travel distance
- **Order lifecycle management** — Pending → Accepted → Assigned → Delivered, with real-time status updates
- **Rider management** — supervisors register riders and assign deliveries
- **Payment options** — Easypaisa, JazzCash, and Cash on Delivery
- **Feedback & ratings** — customers rate both the rider and the supervisor after delivery
- **Firebase real-time sync** — all order and user data syncs instantly across devices

---

## Screenshots

| Choose Role | Login | Place Order (Map) |
|---|---|---|
| ![Choose Role](screenshots/choose_role.png) | ![Login](screenshots/login.png) | ![Map](screenshots/map.png) |

| Customer Orders | Checkout | Feedback |
|---|---|---|
| ![Orders](screenshots/orders.png) | ![Checkout](screenshots/checkout.png) | ![Feedback](screenshots/feedback.png) |

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Flutter (Dart) |
| Backend | Firebase (Firestore, Authentication, Storage) |
| Maps | Google Maps API |
| Algorithm | Branch & Bound (TSP Route Optimization) |
| State Management | Provider |

---

## Architecture

Three user roles with separate dashboards:

- **Customer** — browse RO plants on map, place orders, track status, give feedback
- **Supervisor** — manage incoming orders, assign riders, view payments and inventory
- **Rider** — view assigned deliveries, update delivery status

---

## Route Optimization

The app implements the **Traveling Salesman Problem (TSP)** using a **Branch and Bound** algorithm to calculate the most efficient delivery route for riders handling multiple orders. This resulted in approximately **25% reduction in travel distance** compared to unoptimized routes.

---

## Project Structure

```
hydro-mart/
├── lib/
│   ├── screens/          # UI screens (customer, supervisor, rider)
│   ├── models/           # Data models (Order, User, Rider, etc.)
│   ├── services/         # Firebase services
│   └── algorithms/       # TSP Branch & Bound implementation
├── assets/
├── pubspec.yaml
└── README.md
```

---

## Getting Started

**Prerequisites**
- Flutter SDK 3.0.5+
- Dart 2.17.1+
- Firebase project with Firestore and Authentication enabled
- Google Maps API key

**Run the app**
```bash
git clone https://github.com/YOUR_USERNAME/hydro-mart.git
cd hydro-mart
flutter pub get
flutter run
```

---

## Database Design

Entities: `Supervisor`, `User`, `Rider`, `Order`, `Product`, `Feedback`

Key relationships:
- Supervisor creates/manages Users and Riders
- Users place Orders linked to selected RO Plant
- Orders contain Products and receive Feedback after delivery

---

## Team Contributions

| Member | Role |
|---|---|
| Tilal Ahmed | TSP Branch & Bound route optimization algorithm |
| Arham Ali | Firebase backend, order management |
| Mirza Humza Saeed | Authentication, rider management, testing |

---

## Institution

**Iqra University** — Department of Computer Science, Karachi  
Batch 2020–2024 | Approved: August 2024
