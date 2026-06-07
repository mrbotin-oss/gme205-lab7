# GmE 205 - Laboratory 7: PostGIS to REST API to GIS Clients

# Overview
- This Laboratory introduces spatial data that comes from an actual PostGIS database and is accessed through a REST API.

# Environment Setup
- Python 3.x    
- PostgreSQL with PostGIS
- flask, flask-cors, psycopg2-binary, python-dotenv

# How to run
1. Activate the virutal environment
2. Run test_connection.py to test the database connection
3. Run app.py to create REST API endpoints using Flask for valid GeoJSON FeatureCollections
4. Open API endpoints directly in QGIS

# Reflections
1. In this architecture, PostGIS functions as the spatial database layer, storing parcel and road datasets. By connecting to the database and executing queries, the application can retrieve the spatial information needed for its operations.
2. Flask serves as the backend framework that handles requests from the application, communicates with the PostGIS database, and returns the requested data to users. It acts as an intermediary between the frontend and the database, processing queries and exposing spatial data through API endpoints.
3. GeoJSON is useful for spatial web services because it has become a widely adopted standard for exchanging geographic data. One of its key advantages is that it is both human-readable and machine-readable, making it easy to understand, parse, and process across different applications and platforms.
4. The ST_AsGeoJSON() function in PostGIS converts spatial geometries into GeoJSON, a widely used standard for exchanging geographic data over networks. By transforming database-stored geometries into a format that can be easily transmitted and understood by different systems.
5. QGIS is considered a heavy client because it is a full-featured desktop GIS application that runs locally on a user's computer. It includes a wide range of built-in tools, supporting libraries, and plugins, and requires significant processing power, memory, and storage to perform advanced spatial analysis and visualization tasks. Although QGIS can connect to web-based services, much of the data processing and rendering is performed on the client machine. This contrasts with lightweight web mapping solutions such as Leaflet, Mapbox, and MapLibre, which are designed to run efficiently in web browsers and rely more heavily on server-side resources for data delivery and processing.
6. A REST API is preferable to manually exporting shapefiles because it eliminates the need for repetitive data copying, file transfers, and manual distribution of spatial datasets. Instead, data can be accessed directly from a centralized source through automated requests, enabling near real-time updates and ensuring that users always work with the most current information. This approach also reduces the likelihood of human errors, such as using outdated files, duplicating data, or introducing inconsistencies during the export and sharing process.
7. This laboratory demonstrates distributed geospatial computing by making geospatial data and functions available through web APIs. Clients on different machines can access these services remotely, allowing spatial data and processing capabilities to be shared across a network rather than being restricted to a single computer.
8. Service-based GIS architecture improves data accessibility, consistency, and scalability by delivering geospatial data and functions through network services. This allows multiple users and applications to access centralized, up-to-date data, reduces duplication of datasets, and enables seamless integration across different platforms and systems.
9. In a service-based spatial system, scalability is achieved by decoupling the database, backend services, and client applications. PostGIS handles centralized storage and spatial querying, while a backend service such as Flask exposes these capabilities through APIs. The architecture scales well because data and processing are centralized on servers, while users access them through APIs.

