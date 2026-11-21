# Wanderlust Concierge

A travel-planning prototype exploring how an AI agent can combine destination information, preferences, and budget tools in a conversation.

**Status:** prototype · **Source repository:** private · **Live demo:** not provided

## What I explored

- Agent orchestration with Google ADK and Gemini, registered tools, and structured A2UI responses.
- A Firestore destination catalog and memory hooks for conversational context.
- Budget calculations and a currency-rate lookup tool.
- A FastAPI frontend proxy that forwards requests to an authenticated A2A agent.
- Image and video generation tools with artifact and Cloud Storage handling.

## How the pieces connect

The browser sends a request through the frontend proxy to the configured agent. The agent selects tools and supporting services, then returns text or structured A2UI content. A callback requests conversation-memory extraction when a compatible memory service is available.

## Current limits

This overview is based on inspected project source and documentation. It does not establish a successful deployment or an end-to-end run. The repository is private, so this page provides an overview rather than a reproducible public demo.

Weather responses are simulated. Catalog access, model calls, generated media, and memory depend on runtime configuration and service permissions. Local-time support is limited to San Francisco. Generated asset URLs also require appropriate storage access.

[Back to my profile](../../README.md)
