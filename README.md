# Philippines Higher Education Institutions API

A simple, fast, and structured JSON API built with Node.js and Express that provides a list of all State Universities and Colleges (SUCs), Local Universities and Colleges (LUCs), and Higher Education Institutions (HEIs) in the Philippines, sorted by regions.

**Author:** Rolly Paredes

## Overview
This API allows developers to easily retrieve a comprehensive list of schools in the Philippines. You can fetch all schools at once, filter them by specific regions, or filter them by their institutional category (e.g., SUCs or private HEIs).

## How it works
The data is parsed from a raw text file using `parse.js` to create a structured `data.json` file. The `index.js` Express server then reads this JSON file and serves it through various RESTful endpoints.

## Installation & Setup

1. **Install dependencies:**
   Ensure you have Node.js installed, then run:
   ```bash
   npm install
   ```

2. **Generate the JSON data:**
   If you have updated the `data.txt` file with new schools, run the parser script to generate the updated `data.json`:
   ```bash
   node parse.js
   ```

3. **Start the server:**
   ```bash
   npm start
   ```
   The API will now be running locally on `http://localhost:3000`.

## API Endpoints

### 1. Get All Schools
**Endpoint:** `GET /api/schools`
Returns the complete list of all schools, grouped by their respective regions.

### 2. Get Schools by Region
**Endpoint:** `GET /api/schools/region/:regionId`
Returns all schools within a specific region.
**Example:** `GET /api/schools/region/01`

### 3. Get All SUCs
**Endpoint:** `GET /api/schools/sucs`
Returns a list of all State Universities and Colleges (SUCs) across all regions.

### 4. Get All HEIs
**Endpoint:** `GET /api/schools/heis`
Returns a list of all Private Higher Education Institutions (HEIs) across all regions.

## Data Structure Example
```json
{
  "region": "01 - Ilocos Region",
  "schools": [
    {
      "name": "Pangasinan State University",
      "type": "SUC",
      "category": "SUC"
    },
    {
      "name": "AMA Computer College-Dagupan City",
      "type": "Private HEI",
      "category": "HEI"
    }
  ]
}
```

## Publishing Online
This API is ready to be deployed on platforms like **Render**, **Vercel**, or **Railway**. 
Simply upload this repository to GitHub, connect it to your preferred hosting provider, set the Build Command to `npm install`, and the Start Command to `npm start`.
