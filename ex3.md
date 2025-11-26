# Exercise 3: Chaining Prompts for Agent Flow

## Objective
Combine multiple prompts to simulate a tool-using agent workflow.

## Agent Flow Simulation

### Step 1: Ask for User's Query
**Prompt:** "What's the temperature in Paris?"

**AI Response:**
```
I'll help you get the current temperature in Paris. Let me check the weather data for you.
```

### Step 2: Simulate Weather API Call
**Prompt:** "Simulate a call to the weather API for Paris. Return the response in JSON format: {"location": string, "temperature_celsius": number, "condition": string}"

**AI Response:**
```json
{
  "location": "Paris",
  "temperature_celsius": 18,
  "condition": "Cloudy"
}
```

### Step 3: Format Final Answer
**Prompt:** "Based on this weather API response: {"location": "Paris", "temperature_celsius": 18, "condition": "Cloudy"}, format a final answer for the user who asked about Paris temperature."

**AI Response:**
```
The current temperature in Paris is 18°C and it's cloudy outside.
```

## Complete Chained Process Documentation

### Input
User Query: "What's the temperature in Paris?"

### Processing Chain
1. **Step 1** → Acknowledge user query
2. **Step 2** → Simulate API call to get weather data
3. **Step 3** → Format final response for user

### Output
Final Response: "The current temperature in Paris is 18°C and it's cloudy outside."

## Analysis
The chained prompt approach simulates a tool-using agent by:

1. **Step 1** - Handles the user interaction and query understanding
2. **Step 2** - Simulates external tool/API usage to get data
3. **Step 3** - Processes the tool output into a user-friendly response

This demonstrates how agents can break down complex tasks into smaller steps, use external tools, and provide coherent responses to users.