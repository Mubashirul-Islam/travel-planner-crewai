# Multi-Agent AI Travel Planner (CrewAI)

This project implements a CrewAI-based travel planner with the required architecture and tooling:

- Agents: Destination Researcher, Budget Planner, Itinerary Designer, Validation Agent
- Mandatory search: Serper Dev API
- LLM connectivity: Groq API
- Custom calculator logic for budget computations
- Structured markdown output in `report.md`
- Execution logging in `execution.log`

## Input and Output

### Required input

- Destination
- Travel Dates
- Budget

### Optional input

- Preferences

### Output sections

1. Travel Plan: `<Destination>`
2. Destination Overview
3. Budget Breakdown
4. Day-wise Itinerary
5. Validation Summary

## Setup

Python requirement: `>=3.10,<3.14`

Install dependencies:

```bash
crewai install
```

Set environment variables:

```bash
export GROQ_API_KEY="your_groq_api_key"
export SERPER_API_KEY="your_serper_api_key"
export GROQ_MODEL="llama-3.3-70b-versatile"  # optional
```

## Run

### Interactive mode

```bash
crewai run
```

The CLI prompts for destination, travel dates, budget, and optional preferences.

### Non-interactive mode

```bash
crewai run --destination "Tokyo" --travel-dates "2026-05-10 to 2026-05-15" --budget "USD 2200" --preferences "Food, museums, walkable routes"
```

or via environment variables:

```bash
export TRAVEL_DESTINATION="Tokyo"
export TRAVEL_DATES="2026-05-10 to 2026-05-15"
export TRAVEL_BUDGET="USD 2200"
export TRAVEL_PREFERENCES="Food, museums, walkable routes"
crewai run
```

## Notes

- No other search tool is configured besides Serper.
- Budget estimates are expected to be sourced from researched context; unknown values are marked as assumptions.
