```
# Multi-Agent Customer Service System - A2A ADK MCP Implementation

## Overview
This project implements a multi-agent customer service system using Google's Agent Development Kit (ADK) with Agent-to-Agent (A2A) communication protocol and Model Context Protocol (MCP) for database access.

## System Architecture

### Components
1. **MCP Server** (Port 8000)
   - Provides HTTP API layer over SQLite database
   - Handles CRUD operations for customer accounts and support tickets

2. **Customer Information Agent** (Port 9300)
   - Specializes in data retrieval and customer record management
   - Performs lookups, updates, and complex queries

3. **Support Specialist Agent** (Port 9301)
   - Handles customer service inquiries
   - Creates and manages support tickets with priority levels

4. **Orchestration Agent** (Port 9400)
   - Main entry point for user requests
   - Routes queries to appropriate specialist agents
   - Coordinates multi-agent workflows



## Installation

1. Clone or download all project files to a directory
2. Install required packages 
### Required Python Packages
```bash
pip install google-adk
pip install a2a
pip install httpx
pip install uvicorn
pip install starlette
pip install python-dotenv
pip install nest-asyncio
pip install pandas  # Optional, for database inspection
```
3. Create `.env` file with your HF_TOKEN

## Running the System

### Option 1: Command Line
```bash
python main.py
```

This will:
- Initialize the SQLite database with seed data
- Start all four servers (MCP + 3 A2A agents)
- Run the integration test suite automatically
- Keep servers running until interrupted (Ctrl+C)

