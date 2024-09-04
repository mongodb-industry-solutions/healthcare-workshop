# Healthcare Workshop

## Overview

This repository contains a collection of Jupyter Notebooks designed to demonstrate data generation, validation, and MongoDB-based operations for a healthcare system. The main goal is to generate patient and appointment data while handling complex MongoDB schema transformations and relationships.

## Prerequisites

Ensure that you have the following installed:

- **Python 3.x**
- **Conda** package manager (or `miniconda`, `anaconda`)
- **MongoDB Atlas** account or local MongoDB setup.

### MongoDB Credentials

The connection to MongoDB requires a URI string that is provided via an environment variable. You should set your MongoDB connection string in your environment:

```bash
export MONGO_URI='your-mongo-uri'


Alternatively, for ease of use in Jupyter Notebooks, you can set the variable directly within the notebooks.

## Conda Environment Setup

1. **Create a new conda environment**:

conda create –name healthcare_env python=3.11

2. **Activate the environment**:

conda activate healthcare_env

3. **Install required packages**:

pip install pymongo Faker jupyter

4. **Launch Jupyter Notebook**:

## Notebooks Overview

### S1 - Data Generation (Patients)

**File: `S1 - data-generation-patients.ipynb`**

This notebook generates random patient data using the `Faker` library and inserts it into MongoDB. It demonstrates how to generate fields such as patient name, address, contact details, and emergency contact. The main MongoDB collection for storing this data is `patients`.

- **Features**:
- Use of `Faker` to generate realistic patient data.
- Randomized timestamps for record creation and updates.

### S2 - Insert Validation Error

**File: `S2 - insert-validate-error.ipynb`**

This notebook demonstrates MongoDB insert validation, showcasing how to manage and handle validation errors when attempting to insert data that doesn’t meet the required schema or constraints. An example is provided where incorrect province data leads to an error.

- **Features**:
- Error handling for incorrect schema values.
- Validation of address data.

### S3 - Change Schema

**File: `S3 - change-schema.ipynb`**

This notebook illustrates how to change an existing schema in MongoDB. Specifically, it migrates the `address` field to a new `addresses` array format, allowing patients to have multiple addresses.

- **Features**:
- Schema transformation: from a single `address` to multiple `addresses`.
- Use of MongoDB `updateMany()` function to modify existing records.

### S4 - Generate Appointments

**File: `S4 - generate-appointments.ipynb`**

This notebook generates appointments for patients in the system. It demonstrates creating various appointment types (e.g., consultation, follow-up) and includes additional details such as doctor information, services provided, and location using MongoDB’s document model capabilities.

- **Features**:
- Use of embeddings and arrays for complex data structures.
- Appointment validation and overlap checks.
- Generation of random appointment details like doctor info, services, and location.