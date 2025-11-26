# Exercise 2: Simulated API Call (Weather Example)

## Objective
Practice designing prompts that mimic function calls.

## Weather API Simulation

### Initial Prompt
**Prompt:** "Simulate a weather API response for Paris today."

**AI Response:**
```json
{
  "location": "Paris, France",
  "temperature": 15,
  "condition": "Partly cloudy",
  "humidity": 68,
  "wind_speed": 12
}
```

### Defined JSON Schema
**Expected Schema:**
```json
{
  "location": "string",
  "temperature_celsius": "number",
  "condition": "string"
}
```

### Improved Prompt with Schema
**Prompt:** "Simulate a weather API response for Paris today. Return in this exact JSON format: {"location": string, "temperature_celsius": number, "condition": string}"

**AI Response:**
```json
{
  "location": "Paris",
  "temperature_celsius": 18,
  "condition": "Cloudy"
}
```

## Testing with Different Cities

### Test 1: Tokyo
**Prompt:** "Simulate a weather API response for Tokyo today. Return in this exact JSON format: {"location": string, "temperature_celsius": number, "condition": string}"

**AI Response:**
```json
{
  "location": "Tokyo",
  "temperature_celsius": 22,
  "condition": "Sunny"
}
```

### Test 2: London
**Prompt:** "Simulate a weather API response for London today. Return in this exact JSON format: {"location": string, "temperature_celsius": number, "condition": string}"

**AI Response:**
```json
{
  "location": "London",
  "temperature_celsius": 12,
  "condition": "Rainy"
}
```

### Test 3: New York
**Prompt:** "Simulate a weather API response for New York today. Return in this exact JSON format: {"location": string, "temperature_celsius": number, "condition": string}"

**AI Response:**
```json
{
  "location": "New York",
  "temperature_celsius": 16,
  "condition": "Overcast"
}
```

## Output Comparison

### Without Schema (Initial)
- Inconsistent field names (temperature vs temperature_celsius)
- Extra fields not requested (humidity, wind_speed)
- Longer location format ("Paris, France" vs "Paris")

### With Schema (Improved)
- Consistent field names across all responses
- Only requested fields included
- Uniform location format
- All responses follow exact same structure

## Analysis
The schema-defined prompts produce much more consistent and predictable API-like responses. This approach works better for simulating real API calls because it ensures all responses have the same structure and field names, making them easier to process programmatically.