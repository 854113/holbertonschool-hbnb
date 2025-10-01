**High-Level Package Diagram – HBnB Application**

## **Overview**
This document presents a high-level package diagram illustrating the three-layer architecture of the HBnB application.  
It demonstrates how the various components are organized and interact using the **Facade Pattern**.

## **Three-Layer Architecture**
The application is structured into three primary layers, each with defined responsibilities:

### **1. Presentation Layer (Services, API)**
- Handles all interactions with end-users.
- Exposes API endpoints through services such as `UserService`, `PlaceService`, `ReviewService`, and `AmenityService`.
- Communicates exclusively with the Business Logic Layer via the **Facade** to simplify operations.

### **2. Business Logic Layer (Models)**
- Contains the core application logic.
- Defines models representing system entities: `User`, `Place`, `Review`, and `Amenity`.
- Uses the **Facade** as a single interface to interact with the Persistence Layer, encapsulating internal processes.

### **3. Persistence Layer (Database Access)**
- Manages data storage and retrieval operations.
- Includes repositories for each entity: `UserRepository`, `PlaceRepository`, `ReviewRepository`, and `AmenityRepository`.
- Handles all interactions with the `Database`.
- The Business Logic Layer communicates with this layer only via the **Facade**.

## **Package Diagram (Mermaid.js)**
```classDiagram
class Presentation {
    +UserService
    +PlaceService
    +ReviewService
    +AmenityService
}

class BusinessLogic {
    +Facade
    +User
    +Place
    +Review
    +Amenity
}

class Persistence {
    +UserRepository
    +PlaceRepository
    +ReviewRepository
    +AmenityRepository
    +Database
}

Presentation --> BusinessLogic : Facade
BusinessLogic --> Persistence : Database Operations
```
![HBnB High-Level Package Diagram](Resources/HighLevelPackageDiagram.png)

