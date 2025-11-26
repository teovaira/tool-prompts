# Exercise 1: Structured JSON Output

## Objective
Create prompts that produce structured machine-readable output.

## Prompts Tested

### 1. Unstructured Prompt (Weak)
**Prompt:** "List three cities with their populations."

**Output Format:** Free text

**Example Response:** 
```
Paris has about 2.1 million people, Tokyo around 14 million, and New York roughly 8.3 million.
```

**Problems:**
- Hard to parse programmatically
- Inconsistent format
- Mixed units and formats

### 2. Structured Prompt (Improved)
**Prompt:** "Return the following in JSON format: [{"city": string, "population": number}]. List three cities with their populations."

**Output Format:** Valid JSON array

**Example Response:**
```json
[
  {"city": "Paris", "population": 2100000},
  {"city": "Tokyo", "population": 14000000},
  {"city": "New York", "population": 8300000}
]
```

**Benefits:**
- Machine readable
- Consistent structure
- Easy to validate and parse

## Multiple Input Testing

### Test Case 1: Countries and Capitals
**Prompt:** "Return countries and capitals in JSON format: [{"country": string, "capital": string}]"

**AI Response:**
```json
[
  {"country": "Germany", "capital": "Berlin"},
  {"country": "Italy", "capital": "Rome"},
  {"country": "Brazil", "capital": "Brasília"}
]
```
**Result:** ✅ Valid JSON structure maintained

### Test Case 2: Programming Languages
**Prompt:** "Return programming languages with year created in JSON: [{"language": string, "year": number}]"

**AI Response:**
```json
[
  {"language": "C", "year": 1972},
  {"language": "Java", "year": 1995},
  {"language": "Go", "year": 2009}
]
```
**Result:** ✅ Valid JSON structure maintained

### Test Case 3: Books and Authors
**Prompt:** "Return books with their authors and publication years in JSON format: [{"title": string, "author": string, "year": number}]"

**AI Response:**
```json
[
  {"title": "1984", "author": "George Orwell", "year": 1949},
  {"title": "To Kill a Mockingbird", "author": "Harper Lee", "year": 1960},
  {"title": "The Great Gatsby", "author": "F. Scott Fitzgerald", "year": 1925}
]
```
**Result:** ✅ Valid JSON structure maintained

## Analysis
The structured prompts work much better because:
1. They specify exact output format
2. They include data type information (string, number)
3. They provide clear schema structure
4. Results can be validated programmatically

The key improvement is being explicit about the expected JSON schema in the prompt itself.