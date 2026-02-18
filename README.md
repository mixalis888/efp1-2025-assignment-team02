# private_ergasia

Simple command-line order registration system for an e-shop.

## Overview

This project provides a small CLI application where a manager can:

- Create new customer orders
- Validate input fields (required fields, email format, phone digits)
- View all registered orders in memory
- Receive a terminal notification when an order is registered

## Requirements

- Python 3.13+
- One of the following package managers:
  - uv (recommended)
  - pip + venv

## Quick Start (uv)

1. Install dependencies and create environment:

	uv sync

2. Run the application:

	uv run main.py

3. Run the web app:

	uv run uvicorn web_app:app --reload

## Quick Start (pip)

1. Create virtual environment:

	python3 -m venv .venv

2. Activate it:

	source .venv/bin/activate

3. Run the application:

	python main.py

4. Run the web app:

	uvicorn web_app:app --reload

## How to Use

After launch, choose from the menu:

- 1: Create a new order
- 2: View all orders
- 0: Exit

For a new order, provide:

- Customer full name
- Phone
- Email
- Delivery address

If validation passes, the app generates an order ID in format ORD-0001, ORD-0002, etc.

## Web Interface & API

When the FastAPI server runs, open:

- http://127.0.0.1:8000 for the web page
- http://127.0.0.1:8000/docs for interactive API docs

Available endpoints:

- GET /api/orders: list all orders
- POST /api/orders: create a new order

## Project Structure

- main.py: Application entry point and CLI loop
- web_app.py: FastAPI app with page route and API routes
- ergasia/models.py: Domain models (Customer, EshopManager, Order)
- ergasia/services.py: Business logic (validation, save order, notifications)
- pyproject.toml: Project metadata and dependency configuration

## Notes

- Orders are stored in memory only (not persisted to a database).
- No external dependencies are currently required.

