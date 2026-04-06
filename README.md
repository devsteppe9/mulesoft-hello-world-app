# Hello World MuleSoft App

This repository contains a simple Mule 4 APIKit-based Hello World application.

It is aligned with the API-led connectivity tutorial concepts:
https://docs.mulesoft.com/general/api-led-overview

## What this app does

- Exposes an HTTP API on port 8081.
- Routes requests with APIKit.
- Implements a Hello World endpoint.
- Includes global APIKit error handling for common API errors (400, 404, 405, 406, 415, 501).
- Demonstrates validation using Mule Validation Module.

## API endpoints

Base URL:

- http://localhost:8081

Main API:

- GET /api/greeting

API Console (APIKit):

- /console

## Example request

```bash
curl -i http://localhost:8081/api/greeting
```

Expected response body:

```text
Today the greeting is Hello.
```

## Validation behavior in greeting flow

The greeting flow validates payload size:

- Minimum length: 6
- Maximum length: 30

If validation fails, the flow propagates the validation error description as the payload.

## Prerequisites

- Java 17
- Mule runtime 4.11.0
- Maven 3.8+
- Anypoint Studio (recommended for local development)

## Run locally

### Option 1: Anypoint Studio (recommended)

1. Import this project into Anypoint Studio.
2. Run the application.
3. Call the endpoint at http://localhost:8081/api/greeting.

### Option 2: Maven

From the project root:

```bash
mvn clean package
```

Then run the generated Mule application using your Mule runtime environment.

## Project structure

- src/main/mule/hello-world-api.xml: Main Mule flows, HTTP listener, APIKit router, endpoint implementation.
- src/main/resources: Runtime resources (logging config, API resources if included).
- src/test/munit: MUnit tests (add/extend as needed).
- pom.xml: Build configuration and dependencies.

## Notes

- The app listens on 0.0.0.0:8081.
- API definition is resolved through Exchange dependency in pom.xml.
- This sample is intended as a starter for API-led learning and can be extended into separate Experience, Process, and System APIs.
