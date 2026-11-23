# Singapore HDB Carpark Availability & Explorer (OutSystems)

A full-stack OutSystems web and mobile-ready application that integrates live parking availability telemetry and static HDB carpark datasets from **data.gov.sg**. Users can locate nearby carparks via GPS, explore real-time lot availability on an interactive Google Map, bookmark favorite carparks, and contribute community driver reviews.

---

## 1. Live Application & Access

* **OutSystems Web Application URL:** https://noloty.outsystemscloud.com/CarPark/
* **Demo Test Account (for Reviews):**
  
  * **Username:** johndoe@test.com,MaxWilsonSmith@test.com
  * **Password:** P@ssw0rd123

> **Note:** Public browsing of the map, live availability, and reviews is enabled. Logging in with the demo credentials unlocks posting star ratings/comments and saving favorite carparks.

---

## 2. Repository Structure

______________________________________________________________________________________________________________________________________________
+-------------------------------------------------------------------+
|  End-User Layer: CarPark                                          |
|  - Interactive Dashboard, Paginated Data Grid, Slide-out Sidebar  |
+---------------------------------+---------------------------------+
                                  |
                 +----------------+----------------+
                 v                                 v
+---------------------------------+ +-------------------------------+
|  Core Services: Carpark_CS      | |  Library: Carpark_UI_Lib      |
|  - Data Model & Entities        | |  - CarparkMap_Block (GMaps)   |
|  - Background Sync Timers       | |  - CarparkReviews_Block       |
|  - data.gov.sg REST Consumer    | |  - ConvertSVY21ToWGS84 (JS)   |
|  - Server-Side Paginated SQL    | |                               |
+---------------------------------+ +-------------------------------+
