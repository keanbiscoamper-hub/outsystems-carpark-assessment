# Singapore HDB Carpark Availability & Explorer (OutSystems)

A full-stack OutSystems web -ready application that integrates live parking availability telemetry and static HDB carpark datasets from **data.gov.sg**. Users can locate nearby carparks via GPS, explore real-time lot availability on an interactive Google Map, and contribute community driver reviews.

---

## 1. Live Application & Access

* **OutSystems Web Application URL:** https://noloty.outsystemscloud.com/CarPark/
* **Demo Test Account (for Reviews):**
  
  * **Username:** johndoe@test.com,MaxWilsonSmith@test.com
  * **Password:** P@ssw0rd123

> **Note:** Public browsing of the map, live availability, and reviews is enabled. Logging in with the demo credentials unlocks posting star ratings/comments and saving favorite carparks.

---

## 2.Technical Documentation
*  https://docs.google.com/document/d/1FMeBSg8sFqKsq7Busc4EDeyvvwu530bWKQ7yKpxsaTE/edit?usp=sharing

## 3. Google Cloud Platform (GCP) & Maps API Governance

To render interactive map telemetry and live marker clustering while preventing unauthorized quota abuse, the mapping integration is governed by strict Google Cloud security controls:

* **Enabled API Scope:** Provisioned under a dedicated GCP project with **Maps JavaScript API** enabled and a billing account linked to support production map loads.
* **Application & HTTP Referrer Restrictions:** The API key is locked down using **Website (HTTP Referrer)** restrictions (`*noloty.outsystemscloud.com/*`), preventing unauthorized third-party domains from consuming the key if inspected in browser network traffic.
* **API-Level Restrictions:** Key permissions are scoped strictly to the **Maps JavaScript API** (principle of least privilege), blocking access to unrelated billable GCP services.
* **Secret Management:** The API key is never hardcoded inside `.oml` source modules or committed to Git; it is injected at runtime via the OutSystems **Service Center** `Effective Value` configuration on `OutSystemsMaps.GoogleMapsAPIKey`.

