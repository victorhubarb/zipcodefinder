# Zip Code Finder 📮

![Status](https://img.shields.io/badge/status-completed-green?style=for-the-badge)
![Java](https://img.shields.io/badge/Java-API%20%2B%20JSON-orange?style=for-the-badge&logo=java)

A Java application that queries the ViaCEP API to look up Brazilian postal codes (CEPs) and saves the results as formatted JSON files.

---

## Overview

Built to practice HTTP API consumption and JSON handling in Java. The user types in a CEP, the app hits the ViaCEP REST API using `java.net.http.HttpClient`, deserializes the response into an `Endereco` record using GSON, prints the address to the console, and writes it to a `.json` file named after the CEP. Clean and focused — does one thing well.

---

## Architecture

```
src/
├── Main.java                # Entry point — user input and orchestration
├── ConsultaCep.java         # HTTP client — builds and sends the ViaCEP API request
├── Endereco.java            # Java record — models the address response from the API
└── GeradorDeArquivo.java    # File writer — saves the address as a formatted JSON file
```

### Key Concepts Applied

| Concept | How it shows up |
|---|---|
| **HTTP API Consumption** | `HttpClient` + `HttpRequest` from `java.net.http` — no external library needed for the request |
| **JSON Deserialization** | GSON maps the ViaCEP JSON response directly into the `Endereco` record |
| **Java Record** | `Endereco` is a record — immutable, concise DTO with `cep`, `logradouro`, `complemento`, `localidade`, `uf`, and `bairro` fields |
| **File I/O** | `GeradorDeArquivo` writes pretty-printed JSON using `GsonBuilder.setPrettyPrinting()` and `FileWriter` |
| **Exception Handling** | API errors and file write failures are caught and reported gracefully — app exits cleanly |
| **var keyword** | `var cep = leitura.nextLine()` — local type inference introduced in Java 10 |

---

## How to Run

**Prerequisites:** Java 18+ · IntelliJ IDEA or Eclipse · GSON library on the classpath

```bash
git clone https://github.com/victorhubarb/zipcodefinder.git
cd zipcodefinder
```

Open in your IDE, add GSON to the classpath, run `Main.java`, and enter any valid Brazilian CEP when prompted.

The app prints the full address to the console and saves it as `<CEP>.json` in the working directory — for example, searching `80530-230` generates `80530-230.json` with the formatted address data.

---

## Author

**Victor Hugo Barbosa**
[GitHub](https://github.com/victorhubarb) · [LinkedIn](https://www.linkedin.com/in/victorhbarbosa/)
