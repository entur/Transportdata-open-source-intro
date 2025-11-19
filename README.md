# Introduction to team RoR open-source projects

## About Entur ROR

Entur ROR (Routes and Journey Planning) is the team responsible for Entur’s open-source projects that power national journey planning in Norway. We develop and maintain the core components that collect, structure and serve public transport data across all modes — buses, trains, ferries, trams, bikes and shared mobility.

Our mission is to make mobility seamless and accessible. We build and operate the engines behind Entur’s national journey planner, and we publish our tools and services as open source to support transparency, collaboration and innovation across the mobility ecosystem.

This page collects the most essential public repositories maintained by the ROR team, covering everything from data pipelines and APIs to journey planning engines and developer utilities.

For a graphical view, take a look at our [OVERVIEW OF COMPONENTS](https://app.mural.co/t/entur7578/m/entur7578/1675243352875/f57238026a6daceda8228b7ed10fab1e9dd6a7a2) 

## Table of Contents

- [Producing Data](#producing-data)
    - [Libraries](#libraries)
    - [Converters](#converters)
    - [Data Collection and Maintenance Tools](#data-collection-and-maintenance-tools)
    - [Merge Tools](#merge-tools)
    - [Analysis Tools](#analysis-tools)
    - [Timetable Publishing Tools](#timetable-publishing-tools)
    - [Validators](#validators)
- [Realtime](#realtime)
    - [Realtime Libraries & Demo Apps](#realtime-libraries--demo-apps)
    - [Realtime Validators](#realtime-validators)
    - [Realtime and Other Real-time API Archival Tools](#realtime-and-other-real-time-api-archival-tools)
    - [Realtime Converters](#realtime-converters)
    - [Realtime Utilities](#realtime-utilities)
- [Sharing Data](#sharing-data)
- [Using Data](#using-data)
    - [Consumer Apps](#consumer-apps)
        - [Web Apps (open source)](#web-apps-open-source)
        - [Web Apps (closed source)](#web-apps-closed-source)
        - [Native Apps (open source)](#native-apps-open-source)
        - [Native Apps (closed source)](#native-apps-closed-source)
    - [Software for Creating APIs](#software-for-creating-apis)
    - [SDKs](#sdks)
    - [Visualizations](#visualizations)
- [Resources](#resources)
    - [Community](#community)


---

## Producing Data

### Libraries

- **netex-java-model**  
  Java bindings (JAXB) for the NeTEx timetable schema. Provides a programmatic model for reading and writing NeTEx data in Java.

### Converters

- **netex-gtfs-converter-java**  
  Converts NeTEx datasets (using the Nordic NeTEx Profile) into standard GTFS format.

- **damu**  
  Orchestrates conversion of NeTEx exports into GTFS by downloading NeTEx data, running the converter, and storing the resulting GTFS.

### Data Collection and Maintenance Tools

- **marduk**  
  Coordinates the full data-import pipeline for public transport data: validation, import, merging, conversion, and triggering graph rebuilds.

- **tiamat**  
  Backend service for Norway’s national Stop Place Register. Handles import, validation, versioning, and GraphQL/NeTEx export of stop-place data.

### Merge Tools

*(No publicly listed specific tools in this category yet.)*

### Analysis Tools

*(No publicly listed specific tools in this category yet.)*

### Timetable Publishing Tools

*(No publicly listed specific tools in this category yet.)*

### Validators

- **antu**  
  Validates NeTEx PublicationDelivery files against the Nordic NeTEx Profile. Splits validation jobs, aggregates results, and exposes results via a REST API.

---

## Realtime

### Realtime Libraries & Demo Apps

*(No publicly listed libraries or demos yet.)*

### Realtime Validators

*(No publicly listed validators yet.)*

### Realtime and Other Real-time API Archival Tools

*(No publicly listed archival tools yet.)*

### Realtime Converters

- **kishar**  
  Converts incoming SIRI data (via Pub/Sub) to GTFS-RT (Trip Updates, Vehicle Positions, Alerts) and provides standard GTFS-RT endpoints for consumption.

### Realtime Utilities

*(No publicly listed utilities yet.)*

---

## Sharing Data

*(No publicly listed specific tools in this category yet.)*

---

## Using Data

### Consumer Apps

#### Web Apps (open source)

- **OpenTripPlanner-LegacyHSLFork**  
  Entur’s fork of OpenTripPlanner v2. Provides multimodal journey planning using GTFS and OSM, with support for real-time updates and disruption handling.

#### Web Apps (closed source)

*(None publicly available in this category.)*

#### Native Apps (open source)

*(None publicly available in this category.)*

#### Native Apps (closed source)

*(None publicly available in this category.)*

### Software for Creating APIs

*(No publicly listed tools in this category.)*

### SDKs

*(No publicly listed SDKs yet.)*

### Visualizations

*(No publicly listed visualization tools yet.)*

---

## Resources

### Community

*(To be added if applicable.)*

