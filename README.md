# Introduction to team RoR open-source projects

## About Entur ROR

Entur ROR (Routes and Journey Planning) is the team responsible for Entur’s open-source projects that power national journey planning in Norway. We develop and maintain the core components that collect, structure and serve public transport data across all modes — buses, trains, ferries, trams, bikes and shared mobility.

Our mission is to make mobility seamless and accessible. We build and operate the engines behind Entur’s national journey planner, and we publish our tools and services as open source to support transparency, collaboration and innovation across the mobility ecosystem.

This page collects the most essential public repositories maintained by the ROR team, covering everything from data pipelines and APIs to journey planning engines and developer utilities.

For a graphical view, take a look at our [OVERVIEW OF COMPONENTS]() **Make a simple overview**
<img width="2550" height="1429" alt="image" src="https://github.com/user-attachments/assets/0a8ef6c8-85c1-4c86-a912-aa7bff4c0ff5" />


## Table of Contents


    
 


### National StopPlace Registry (NSR)

The **National StopPlace Registry (NSR)** provides a centralized system for managing information about public transport stops across Norway. It consists of **tiamat** (backend) and **abzu** (frontend).  

NSR ensures that stop data is consistent, up-to-date, and accessible for all operators, planners, and third-party applications. It supports versioning, validation, and export to standard formats like **NeTEx**, making it easier to integrate stop information into journey planners, scheduling tools, and public APIs.  

Fixing core data issues is crucial for the entire public transport ecosystem, and stop places are at the very heart of this infrastructure. By establishing a **unique description and ID for each stop**, NSR resolves many downstream problems, enabling more reliable journey planning, scheduling, and data sharing across operators and applications.  

- **Backend (tiamat)**: [github.com/entur/tiamat](https://github.com/entur/tiamat)  
- **Frontend (abzu)**: [github.com/entur/abzu](https://github.com/entur/abzu)

---
## To produce data 
Here we describe our most useful tools to produce data to be sent to the National Access Point (NAP) 

### NPlan

**NPlan** is a lightweight planning tool consisting of two components: **uttu** (backend) and **enki** (frontend). It was developed to produce flexible transport services and has been extended to support scheduling for small operators’ networks.  

NPlan is designed as a simple planning solution for operators who currently do not have dedicated planning software — many rely on Excel sheets, PDFs, or printed timetables at stops. With NPlan, these operators can manage and maintain their schedules more efficiently.  

The tool supports **export to NeTEx**, making it possible to share standardized timetable data with national systems or other transport tools. Its focus on small operators and flexible services fills a crucial gap in public transport planning, enabling more consistent, data-driven operations even for networks with limited resources.  

- **Backend (uttu)**: [github.com/entur/uttu](https://github.com/entur/uttu)  
- **Frontend (enki)**: [github.com/entur/enki](https://github.com/entur/enki)

### Extime

**Extime** is a tool for producing NeTEx datasets from aviation data provided by Avinor. It converts raw flight and airport information into structured NeTEx, enabling journey planners and other systems to integrate aviation connections into multimodal travel planning.  

- **Data source**: [Avinor Flydata](https://partner.avinor.no/tjenester/flydata/)  
- **Repository**: [github.com/entur/extime](https://github.com/entur/extime)


### OSRM (Open Source Routing Machine)

**OSRM** is used ~~a high-performance routing engine for street networks. At Entur, we use OSRM~~ to generate **ServiceLinks** when they are missing in the received NeTEx datasets, and automatically add them back to the dataset. This ensures that journey planners have complete routing information, even when the source data is incomplete.  

- **Repository**: [github.com/entur/osrm-backend](https://github.com/entur/osrm-backend)

### Ninkasi
skal vi ta denne med?

### Operator
skal vi ta denne med?

---
## Aggregation of data to national dataset

### Real-time hub for dynamic data
Anshar

### Micro Mobility Hub, to aggregate data for e-scooters, city bikes and shared cars 
Lamassu

---
## Validation

### Library

### Antu

---
## Data use 

### OpenTripPlanner

### Ukur

legg til flere

---
## Visualization

### Vehicle Map

### Mobility Map

---
# A full description of our complete ecosystem

For a graphical view, take a look at our [OVERVIEW OF COMPONENTS](https://app.mural.co/t/entur7578/m/entur7578/1675243352875/f57238026a6daceda8228b7ed10fab1e9dd6a7a2) 

