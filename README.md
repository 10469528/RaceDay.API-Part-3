# RaceDay - Event Management System

**Author:** Nomvelo Zulu  
**Module:** Programming 2B (PROG6212)  
**Parts:** 1, 2 & 3 - System Planning, RESTful API, and MVC Web Application  
**Date:** November 2026

---

## 📖 Project Overview

South Africa has a rich road events culture, from the iconic Comrades Marathon to the Cape Town Cycle Tour and hundreds of community park runs. However, many of these events are still managed through paper-based registration and disconnected spreadsheets.

**RaceDay** is a full-stack web-based event management system designed specifically for the South African road running, walking, and cycling community. This repository contains the complete solution:

- **Part 1**: Planning documents (ERD, API endpoint plan, SQL database script).
- **Part 2**: A fully functional RESTful API built in ASP.NET Core with role-based JWT authentication, Swagger documentation, and comprehensive unit tests.
- **Part 3**: An ASP.NET Core MVC web application that consumes the API, featuring session-based authentication, Azure Blob Storage integration for image uploads, and Docker containerisation.

---

## 👥 User Roles

The system supports two distinct user roles, each with specific permissions and dedicated interfaces in the web application:

### 🏁 Organiser
- **Dashboard**: View a summary of created events.
- **Events**: Create, edit, and delete events (with banner image uploads).
- **Categories**: Define age and distance categories for events.
- **Enrolments**: View all participant enrolments for their events.
- **Results**: Capture and publish finish times and finishing positions.

### 🏃 Participant
- **Profile**: Register and manage their personal profile.
- **Events**: Browse upcoming events with filtering options.
- **Enrol**: Enter events by selecting a category and paying the entry fee.
- **History**: View personal enrolment history and race results.

---

## 📂 Repository Structure

The solution is divided into three projects:

```text
RaceDayDB/
├── .github/
│   └── workflows/
│       └── dotnet.yml                # CI/CD pipeline (builds all projects & runs tests)
├── docs/                             # Planning documents (Part 1)
│   ├── ERD.png                       # Entity Relationship Diagram
│   ├── API_Endpoint_Plan.md          # RESTful API specification
│   ├── RaceDay_Schema.sql            # SQL Server script
│   └── ci-screenshot.png             # Green CI build screenshot
├── RaceDay.API/                      # RESTful API (Part 2)
│   ├── Controllers/                  # Auth, Users, Events, Categories, Enrolments, Results
│   ├── Data/                         # DbContext
│   ├── DTOs/                         # Data Transfer Objects
│   ├── Migrations/                   # EF Core migrations
│   ├── Models/                       # Entity models
│   ├── Services/                     # BlobService (Azure Integration)
│   ├── Program.cs                    # API configuration
│   └── appsettings.json              # Connection strings & JWT config
├── RaceDay.API.Tests/                # Unit tests (Part 2)
│   ├── AuthTests.cs                  # xUnit test files
│   ├── EventTests.cs
│   ├── EnrolmentTests.cs
│   ├── RoleAccessTests.cs
│   └── CustomWebApplicationFactory.cs
├── RaceDay.Web/                      # MVC Web Application (Part 3)
│   ├── Controllers/                  # Account, Events, Organiser, Enrolments
│   ├── Models/                       # DTOs for the web client
│   ├── Services/                     # RaceDayApiClient (HttpClient wrapper)
│   ├── Views/                        # Razor Views (Bootstrap styled)
│   ├── Dockerfile                    # Containerisation setup
│   ├── Program.cs                    # Web app configuration
│   └── appsettings.json              # API Base URL config
└── README.md                         # This file
