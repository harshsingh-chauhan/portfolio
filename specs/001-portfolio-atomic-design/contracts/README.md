# API Contracts

## Overview

This project is a frontend-focused single-page application. It does not have a dedicated backend with REST or GraphQL APIs that it owns.

## Third-Party Integrations

The only external service interaction is with **EmailJS** for the contact form.

- **Service**: EmailJS
- **Purpose**: To send an email from the contact form without a custom backend.
- **Contract**: The "contract" is the data payload expected by the EmailJS `send` function. This payload is defined in the `data-model.md` as the `ContactFormData` interface.

No OpenAPI or GraphQL schemas are required for this project.
