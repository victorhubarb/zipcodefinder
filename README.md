# Zip code finder <a name="readme-top"></a>
![Static Badge](https://img.shields.io/badge/status-completed-green?style=for-the-badge)

## Introduction
**Zip code finder** is a Java-based application designed to interact with the ViaCEP API. This project allows users to input a Brazilian postal code (CEP), retrieve the corresponding address details, and save the results to a `.JSON` file. The project demonstrates skills in API consumption, JSON handling, and user interaction through a menu-driven interface.

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [Features](#features)
- [Technologies](#technologies)
- [Contributors](#contributors)

## Installation

### Prerequisites
- Java JDK 18+ installed
- An IDE such as IntelliJ IDEA, Eclipse, or NetBeans installed

### Steps to run
1. Clone the repository:
   ```bash
   git clone https://github.com/victorhubarb/zipcodefinder.git
   cd zipcodefinder
   ```
2. Open the project in your preferred IDE:
- Import the project into your IDE (e.g., using “Open Project” in IntelliJ or “Import Project” in Eclipse).
- Ensure the project uses the correct Java SDK (JDK 18+).

3. Run the application:
- Locate the Main class in the project structure.
- Right-click on the Main class and select Run.

## Usage
The application prompts the user to input a postal code (CEP), fetches the address details from the ViaCEP API, and displays the results. Users can continue making queries or exit the application. The retrieved data is also stored in a .JSON file for further reference.

## Features
- **CEP Lookup**: Query the ViaCEP API to retrieve address details for a given postal code.
- **JSON File Generation**: Save the retrieved address information to a .JSON file.
- **Menu Navigation**:
  - Input a postal code.
  - Display the retrieved address.
  - Save the data to a .JSON file.
  - Exit the application.

## Technologies
- **Java**
- **JSON Handling Libraries** (e.g., Jackson or Gson)
- **HTTP Client Libraries** (e.g., HttpURLConnection, OkHttp, or similar)

## Contributors
- [Victor Barbosa](https://github.com/victorhubarb)
<p align="right">(<a href="#readme-top">back to top</a>)</p>
