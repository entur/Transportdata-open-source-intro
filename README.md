# Introduction to "Entur ROR" and its open-source projects

## What is "Entur ROR"?

We are Entur ROR (Open Data and Journey Planning), the team responsible for Entur for collecting, structuring and publishing public transport data across all modes — buses, trains, ferries, trams, bikes and shared mobility. Our mission is to make mobility seamless and easily accessible for everyone. To achieve this, we develop and maintain a range of open-source applications that power national journey planning and open data aggregation in Norway. We choose to publish our tools and services as open source to support transparency, collaboration and innovation across the mobility ecosystem, not just in Norway, but internationally.

This page collects the most essential public repositories maintained by the Entur ROR team, covering everything from data pipelines and APIs to journey planning engines and developer utilities.

For a visual overview, take a look at our [OVERVIEW OF COMPONENTS]() **Make a simple overview**
<img width="2550" height="1429" alt="image" src="https://github.com/user-attachments/assets/0a8ef6c8-85c1-4c86-a912-aa7bff4c0ff5" />


## Table of Contents

- [About Entur ROR](#about-entur-ror)
- [National StopPlace Registry (NSR)](#national-stopplace-registry-nsr)
- [To produce data](#to-produce-data)
  - [NPlan](#nplan)
  - [Extime](#extime)
  - [Avvik](#avvik)
- [Aggregation of data to national dataset](#aggregation-of-data-to-national-dataset)
  - [Real-time hub for dynamic data (Anshar)](#real-time-hub-for-dynamic-data)
  - [Micro Mobility Hub (Lamassu)](#micro-mobility-hub-to-aggregate-data-for-e-scooters-city-bikes-and-shared-cars)
- [Validation](#validation)
  - [NeTEx Validation Library](#netex-validation-library)
  - [Data pipeline validation (Antu)](#data-pipeline-validation)
- [Data use](#data-use)
  - [OpenTripPlanner (OTP)](#opentripplanner-otp)
  - [Geocoder (Photon)](#geocoder-photon)
  - [Ukur](#ukur)
- [Visualization](#visualization)
  - [Vehicle Map](#vehicle-map)
  - [Mobility Map](#mobility-map)
- [A full description of our complete ecosystem](#a-full-description-of-our-complete-ecosystem)

    
 


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

### Avvik

**Avvik* is a light-weight tool for producing real-time data for deviation messages (textual), cancellations and extra-journeys in the form of SIRI-SX and SIRI-ET streams.

It is composed of two components:

- **Backend(enlil)**: [github.com/entur/uttu](https://github.com/entur/enlil)  
- **Frontend (nirgali)**: [github.com/entur/enki](https://github.com/entur/nirgali)
  
---
## Aggregation of data to national dataset

### Real-time hub for dynamic data

**Anshar** is Entur’s real-time hub for aggregating and distributing SIRI data across Norway’s public transport ecosystem. It collects, normalizes, and processes **SIRI-ET (Estimated Timetable)**, **SIRI-VM (Vehicle Monitoring)**, and **SIRI-SX (Situation Exchange)** from multiple operators into a unified and consistent real-time data stream.

Anshar ensures that real-time information is reliable, complete, and harmonized before it is consumed by journey planners, disruption services, and downstream APIs. By centralizing real-time processing, Anshar reduces complexity for operators and provides a stable foundation for high-quality traveller information across all modes.

- **Repository**: [https://github.com/entur/anshar](https://github.com/entur/anshar)

### Micro Mobility Hub, to aggregate data for e-scooters, city bikes and shared cars 

**Lamassu** is Entur’s data-quality and aggreagation service for shared mobility feeds based on **GBFS (General Bikeshare Feed Specification)** — the open standard used globally for bike, scooter, and micromobility data. It validates and distribute GBFS feeds from operators to show available vehicles, station data, real-time updates, fares and pricing models and more, for use in journey planner apis.  

By providing precise diagnostics and continuous monitoring, Lamassu helps operators deliver higher-quality real-time micromobility data, improving availability information and enhancing multimodal journey planning.

- **Repository**: [https://github.com/entur/lamassu](https://github.com/entur/lamassu)

---
## Validation

### NeTEx Validation Library
The **NeTEx Validation Library** is Entur’s open-source tool for validating NeTEx datasets. It analyzes NeTEx files and generates detailed validation reports. The library supports multiple validation layers, including XML Schema checks, XPath rules, and JAXB object-model validations, allowing complex consistency and reference checks. It comes with default validators for ID uniqueness, reference consistency, and other common rules, and can be extended with custom validators. This library can be used by anyone, regardless of national or local NeTEx profiles.

- **Repository**: [github.com/entur/netex-validator-java](https://github.com/entur/netex-validator-java)

### Data pipeline validation
**Antu** is Entur’s validation service for NeTEx datasets, ensuring that timetable and network data meet the requirements of the **Nordic NeTEx Profile**. It uses Entur’s internal **NeTEx Validation Library** to perform structural, semantic, and profile-specific checks, and produces detailed reports that operators and data providers can use to correct issues.

Antu also integrates with the **National StopPlace Registry (NSR)** to validate references to stop places, ensuring that all StopPlace and Quay IDs in NeTEx datasets are accurate and consistent. This coordination between timetable data and core infrastructure data is essential for delivering high-quality journey planning and multimodal routing.

- **Repository**: [github.com/entur/antu](https://github.com/entur/antu)
<img width="1263" height="73" alt="image" src="https://github.com/user-attachments/assets/219c155c-152a-4caf-ae42-f4adff3d9b2b" />


---
## Data use 

### OpenTripPlanner (OTP)

**OpenTripPlanner (OTP)** is an open-source multimodal journey planning engine that supports routing for public transport, walking, cycling, and driving. It uses NeTEx, SIRI, GBFS, GTFS, GTFS RT, GTFS Flex, GTFS Fares and OpenStreetMap data to generate trip plans, including transfers, schedules, and real-time updates where available. OTP is highly configurable and extensible, allowing integration with real-time feeds, custom routing logic, and external services.

OTP has a **successful and active worldwide community** of developers, operators, and researchers who collaborate to continuously improve the software. The project maintains a structured development process, including **monthly product meetings** and **weekly development meetings**, to coordinate contributions, review progress, and plan new features. This strong community ensures that OTP evolves to meet the diverse needs of cities and operators globally.

The project is governed through a **Project Leadership Committee (PLC)** and a central management role, providing strategic guidance, release management, and quality oversight. This combination of open collaboration, structured governance, and active community engagement has made OTP a reliable and widely adopted solution for multimodal journey planning worldwide.

- **Repository**: [github.com/entur/OpenTripPlanner](https://github.com/entur/OpenTripPlanner)

### Geocoder (Photon)
**Geocoder** is Entur’s geocoding service built on top of the open-source [Photon](https://github.com/komoot/photon) project. It translates free-text addresses, place names, or points of interest into geographic coordinates, making it easier to integrate location-based search into journey planners and other mobility applications.

Geocoder can be used with **OpenTripPlanner (OTP)** or any other public transport use case, as well as any application that needs to find points of interest, addresses, or stop places. By running Geocoder internally, we provide a reliable, high-performance geocoder tailored to Norway’s geography, supporting local place names and seamless integration with transport data.

- **Repository**: [github.com/entur/geocoder](https://github.com/entur/geocoder)
### Ukur
**Ukur** is Entur’s real-time monitoring tool for SIRI feeds. It identifies relevant changes in the SIRI data we receive and determines whether these changes are significant enough to push to end users. This is used for subscribers to receive notifications about updates affecting their planned trips or typical commuting times in the app.

By filtering and prioritizing SIRI updates, Ukur ensures that only actionable, meaningful changes are communicated to users, improving the quality and relevance of push notifications while reducing unnecessary alerts.

- **Repository**: [github.com/entur/ukur](https://github.com/entur/ukur)

*legg til flere*

---
## Visualization

### Vehicle Map
**Vehicle Map** was originally developed to visualize errors in **SIRI Vehicle Monitoring (VM)** feeds. It has since evolved into a tool to showcase the high quality and content of the SIRI data we receive. Vehicle Map allows operators and developers to explore vehicle positions, track performance, and verify the completeness and accuracy of real-time public transport data.

- **Repository**: [github.com/entur/vehicle-map-demo](https://github.com/entur/vehicle-map-demo)

### Mobility Map
**MobilityMap** is a demo map that visualizes all vehicles received via **GBFS feeds** through the **Mobility Hub (Lamassu)**. It provides an interactive way to explore micromobility data such as bikes and scooters, helping developers, operators, and stakeholders understand availability, usage, and distribution of shared mobility services.

- **Repository**: [github.com/entur/mobility-map-demo](https://github.com/entur/mobility-map-demo)

---
# A full description of our complete ecosystem

For a graphical view, take a look at our [OVERVIEW OF COMPONENTS](https://app.mural.co/t/entur7578/m/entur7578/1675243352875/f57238026a6daceda8228b7ed10fab1e9dd6a7a2) 

If you are interested in one or more of our projects, we encourage you to contact us at [kollektivdata@entur.org](mailto:kollektivdata@entur.org). Let's make a difference together. 
