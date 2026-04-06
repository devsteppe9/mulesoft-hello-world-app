# Hello World API

This asset provides a simple Mule 4 APIKit-based Hello World API.

It is intended as a starter implementation aligned with API-led connectivity fundamentals:
https://docs.mulesoft.com/general/api-led-overview

## Overview

The API exposes a greeting endpoint and demonstrates:

- HTTP Listener configuration
- APIKit routing from RAML
- Standardized APIKit error handling
- Basic payload validation with Mule Validation Module

## Base URL

http://localhost:8081

## Resources

### GET /api/greeting

Returns the current greeting message.

Sample response:

Today the greeting is Hello.

## API Console

Interactive APIKit console:

/console

## Error handling

The API includes mapped responses for common APIKit errors:

- 400 Bad Request
- 404 Not Found
- 405 Method Not Allowed
- 406 Not Acceptable
- 415 Unsupported Media Type
- 501 Not Implemented

## Validation

The greeting flow validates payload size:

- Minimum: 6
- Maximum: 30

On validation failure, the error description is returned as the payload.

## Run and test locally

1. Start the Mule application in Anypoint Studio.
2. Send a request to /api/greeting.
3. Open /console for API console documentation.

## API-led connectivity note

This project is a learning-friendly API implementation that can be evolved into API-led layers:

- Experience API for channel-specific consumption
- Process API for orchestration and business logic
- System API for backend system access
