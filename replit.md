# Automated Business Proposal Generator

A Flask web application that uses the Groq AI API to generate professional business proposals, with editing, export, and dashboard features.

## Features
- AI-powered proposal generation via Groq API (llama3-8b-8192)
- Four proposal types: Startup, Marketing, Investment, Partnership
- Proposal editing page with save functionality
- Export to Word (.docx), PDF, and PowerPoint (.pptx) — all server-side
- Proposals dashboard with list and edit links
- Admin page at /admin?key=SECRETKEY to configure the Groq API key
- Inline notifications (no popups)
- Progressive Web App (PWA) support with manifest and service worker

## Tech Stack
- Backend: Flask + SQLite (database.db)
- AI: Groq API (groq Python SDK)
- PDF Export: ReportLab
- Word Export: python-docx
- PowerPoint Export: python-pptx
- Frontend: HTML/CSS (custom, no framework), SVG icons

## Project Structure
- app.py — Flask app with all routes
- main.py — Gunicorn entry point (calls init_db)
- database.db — SQLite database (auto-created)
- templates/ — Jinja2 templates (base, index, edit, dashboard, admin)
- static/ — CSS, manifest.json, service-worker.js, icons/

## Routes
- / — Generate proposal form
- /edit/<id> — Edit and download proposal
- /dashboard — List all proposals
- /admin?key=SECRETKEY — Set Groq API key
- /download-docx/<id>, /download-pdf/<id>, /download-ppt/<id>

## Setup
1. Visit /admin?key=SECRETKEY and enter your Groq API key (get one free at console.groq.com)
2. Go to / and generate your first proposal
