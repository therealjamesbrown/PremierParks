# Premier Parks Unified Guest Experience and Commerce Platform

## Purpose

Premier Parks is building a unified guest experience and operating model across its portfolio of parks and attractions.  
The goal is to connect best-in-class systems into one modern ecosystem that improves guest journeys and enables enterprise-grade reporting into Oracle and NetSuite.

This initiative is not just a system replacement effort. It is a transformation program to:

- unify fragmented guest interactions across web, mobile, and on-property touchpoints
- modernize commerce and entitlement infrastructure
- improve operational consistency across diverse properties
- enable reliable roll-up reporting and financial visibility

## What Premier Parks Is Looking to Solve

- Disconnected systems create friction in booking, admissions, and on-property experiences
- Guest identity and entitlement validation are fragmented across channels
- Commerce flows differ by property, product, and legacy platform
- Reporting and financial controls are difficult to aggregate centrally
- Teams need a scalable framework that supports both current operations and future acquisitions

## Our Role in This Puzzle

We are both:

- a **ticketing and entitlement platform partner**
- an **orchestration and integration partner**

We power core portfolio capabilities including:

- season passes
- ticketing
- entitlement control
- access control
- unified payments and commerce integrations

We provide the connective ecosystem that allows specialized systems to validate guest entitlements and exchange operational context in real time.

## Why This Partnership Matters

Guest experience is the center of the attractions business.  
Premier Parks needs a connected journey from online booking through post-purchase mobile and in-person interactions.

A unified architecture reduces operational complexity while delivering:

- smoother checkout and package booking
- cleaner handoff between lodging, activities, ticketing, and POS
- consistent onsite servicing and room-charge workflows
- stronger analytics and financial governance

## Why We Believe We Are the Right Partner

- proven ability to deliver at scale
- domain expertise in ticketing, entitlements, and commerce
- integration-first mindset across hospitality, attractions, and retail/F&B ecosystems
- practical execution team with experience in payments and platform modernization

### Team (Draft Placeholders)

- Kari - blurb TBD
- Tim - blurb TBD
- John - blurb TBD
- Chris - blurb TBD
- James - payments and commerce platforms, including PayPal background
- Chad - blurb TBD

## Target Guest Interactions to Solve

- Online checkout (new and returning guests)
- Mobile app journey (new and returning guests)
- In-person experiences across admissions, dining, retail, and services
- Post-visit engagement and lifecycle interactions

## Program Timeline and Milestones

- **May:** Architecture, system ownership, and integration design finalized
- **June-July:** System configuration and integration build
- **July-August:** Testing, training, and operational readiness
- **September:** Guest-facing systems go live
- **Late October:** NetSuite financial cutover

## Phased Delivery Approach

### Phase 1: Foundation (Now - May)

Establish system ownership, finalize integration architecture, and align data models across all platforms.

### Phase 2: Configuration and Integration Build (May - July)

Configure NetSuite, Opera PMS, Inntopia, Ticketing, POS, and website. Begin integration development and initial testing.

### Phase 3: Testing and Training (July - August)

Execute end-to-end testing, train operational teams, and validate real-world and edge-case scenarios.

### Phase 4: Operational Go-Live (September)

Launch website, booking systems, ticketing, and POS with a focus on seamless guest experience.

### Phase 5: Financial Cutover (September - October)

Stabilize operations and transition financial reporting and control to NetSuite.

## Current Technology Landscape

### Corporate

- Moneybags
- SSRS
- Great Plains

### Canada

- **Valcartier Vacation Village:** IQware, Siriusware, Anemone (campground), Booker (spa), OpenTable
- **Calypso:** Siriusware, Braintree, Coretech
- **La Ronde:** Accesso Passport, Siriusware

### USA

- **Coretech footprint:** POS, ecommerce, payment plans, F&B, passholder benefits, birthdays, cabanas
- **Nashville Shores:** Coretech, ResNexus (campground), FareHarbor (boat rentals)
- **City Museum:** Square for online retail with shipping

## Portfolio Product Coverage

- **Valcartier Vacation Village (VVV):** lodging, indoor/outdoor waterpark, spa, winter playground, ice hotel, dining reservations
- **Calypso / WnW Toronto / Ocean Breeze / Rapids / Magic Springs / Hawaiian Waters (The Colony + Garland) / Wet n Wild Hawaii:** mix of dated tickets, any-day tickets, season passes, birthdays, cabanas, group tickets, and select add-ons
- **La Ronde:** ticketing plus parking, souvenir cups, meal deals, fast pass
- **Nashville Shores:** campground (ResNexus), marina (FareHarbor), plus Coretech ticketing products
- **City Museum:** ticketing and season passes, birthdays, group tickets, online shop, potential waiver experience
- **Elitch Gardens:** core ticketing products plus Halloween/holiday events and OTA lodging (A Res Travel)
- **Wild Waves Theme and WaterPark:** scheduled closure in 2026 (EOL Nov 1, 2026)

## System Ownership and Design Rules

- **Opera PMS** owns the guest record and is the guest system of record
- **Inntopia** is the primary orchestration layer for package and bundled bookings
- **TBD Ticketing** owns catalog, issuance, and entitlements
- **TBD POS** owns onsite F&B, retail, and commerce transactions
- **Booker** owns spa scheduling and service reservations
- **Anemone** owns campground inventory and campground reservations
- Payments and settlement should remain abstracted from operational systems

## Core Integration and API Flows

- Website -> Inntopia (booking request and package creation)
- Inntopia -> Opera PMS (lodging reservation + guest context)
- Inntopia -> TBD Ticketing (ticket issuance)
- Inntopia -> Booker (spa booking)
- Inntopia -> Anemone (campground booking)
- Opera PMS -> TBD Ticketing (guest sync, stay context, ticket linkage)
- Opera PMS -> TBD POS (room charge, guest identity, stay context)
- TBD Ticketing -> TBD POS (entitlement validation)
- Booker / Anemone -> Opera PMS (guest matching or guest reference alignment, as needed)
- Opera PMS / TBD Ticketing / TBD POS -> Payments layer

## Architecture Principles

- Treat Opera as the central guest and stay-context platform
- Keep ticketing and POS as the onsite entitlement and commerce layer
- Avoid unnecessary direct peer-to-peer integrations between Booker and Anemone
- Keep Inntopia in the orchestration center for packaged experiences
- Prevent package logic sprawl across domain systems

## API Team Focus Areas

- Confirm real-time vs batch requirements for Opera -> Ticketing and Opera -> POS
- Define guest identifier strategy with Opera as authoritative source
- Define entitlement validation between Ticketing and POS
- Clarify Booker and Anemone guest matching needs relative to Opera
- Document payload ownership, event triggers, and retry/error handling by interface

## End-to-End Data Flow (Narrative)

### 1) E-Commerce Hub (Inntopia)

Inntopia acts as the master booking engine. It queries Opera (rooms), Anemone (RV/campground), Booker (spa), and Ticketing (park admission) so guests can complete multi-product packages in one cart.

### 2) Accommodation Nodes (Opera and Anemone)

Opera and Anemone maintain the source of truth for stays and inventory. They publish availability/pricing upward and consume reservation updates after checkout.

### 3) Experience Nodes (Booker and Ticketing)

These systems govern spa and admission capacity. They provide inventory/slots upstream and receive confirmed bookings downstream.

### 4) On-Property Commerce Node (TBD POS)

POS primarily handles onsite purchases (F&B, retail, ancillary services). It integrates laterally with Opera/Anemone for room-charge posting and unified folio settlement.

## Partner Landscape (Working Notes)

### Vantage

- Focus: cashless stored value, loyalty, integrated commerce, mobile app
- Type: potential new partner
- Strategic angle: opportunities in zoo and whitewater/park integrations
- Risks/questions: bandwidth, Quebec constraints, Opera Cloud fit
- Website: <https://vantage.co/>

### Spotlio

- Focus: dynamic pricing, integrated commerce, mobile app
- Type: existing partner
- Strategic angle: known integration history, Inntopia + CRM + app capabilities
- Risks/questions: potential ownership changes
- Website: <https://www.spotlio.com/>

### Toast

- Focus: F&B and restaurant operations
- Type: new partner option
- Strategic angle: offload F&B complexity with strong product ecosystem
- Risks/questions: Quebec tax/stacking considerations
- Website: <https://pos.toasttab.com/>

### Inntopia

- Focus: integration and package commerce orchestration
- Type: strategic platform partner
- Strategic angle: opens broader resort/package opportunities
- Risks/questions: cost, UX concerns, integration complexity
- Website: <https://corp.inntopia.com/>

### Lightspeed

- Focus: F&B alternative
- Type: alternate F&B path
- Strategic angle: Quebec readiness and potential fit
- Risks/questions: pivot complexity vs existing Toast commercial path

## Supporting References

- HubSpot deal record: <https://app.hubspot.com/contacts/2450177/record/0-2/7001789571>
- Landscape image: `Gemini_Generated_Image_u4pcgau4pcgau4pc (1).png`
- Pass benefits screenshot: `Screenshot 2026-04-14 at 4.51.24 PM.png`
- Valcartier purchasing flow reference: room + activities + spa bundled purchase flow

## Draft Positioning Statement

Premier Parks is unifying the guest journey across lodging, admissions, activities, and onsite commerce by connecting best-in-class systems under a modern orchestration model.  
Our platform serves as the entitlement and commerce backbone, enabling seamless guest experiences, operational efficiency, and enterprise-ready financial/reporting consolidation into NetSuite and Oracle.
