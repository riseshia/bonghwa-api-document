# bonghwa api document

## Introduce

This is the api specification for bonghwa backend.
Bonghwa is a simple chat service for small group. It provides:

- Public messaging on channel
- Direct message to specific user
- Upload image

## [Data model](data-model.md)

It describes:

- minimum data scheme to implement backend
- valid string length, regexp is included

## Support protocol

REST API only. May gRPC or WebSocket come...?

- [REST API](rest-api.md)

## Specification Validator

The validator will be comming soon...
It will be implemented based on [Scenario](scenario.md).

### Initialize Endpoint

You need to implement the endpoint which initialize application.
This will make test from validator stable. First state will be defined like:

- Application has one general channel named `general`.
- Application has one admin.
  - email: admin@example.com / password: admin / name: admin
  - admin is a member of `general`.

## What is...???

This is the target application for learning language.
As you know, Rewriting application with another language is a good way
to learn.
For this purpose, I need a concrete and simple specification.
