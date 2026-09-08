# Zip Code Finder 📮

![Status](https://img.shields.io/badge/status-completed-green?style=for-the-badge)
![Java](https://img.shields.io/badge/Java-API%20%2B%20JSON-orange?style=for-the-badge&logo=java)

A Java application that queries the ViaCEP API to look up Brazilian postal codes (CEPs) and saves the results as formatted JSON files.

---

## Overview

Short and focused — that's the best way to describe this one. You type a CEP, the app hits the ViaCEP REST API, deserializes the response into an `Endereco` record using GSON, prints the address to the console, and writes it to a `.json` file named after the CEP. That's it. One thing, done well. Built to practice HTTP consumption and JSON handling in Java without any unnecessary complexity around it.

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
| **HTTP API Consumption** | `HttpClient` + `HttpRequest` from `java.net.http` |
| **JSON Deserialization** | GSON maps the ViaCEP JSON response into the `Endereco` record |
| **Java Record** | `Endereco` is a record — immutable, concise DTO |
| **File I/O** | `GeradorDeArquivo` writes pretty-printed JSON using `GsonBuilder.setPrettyPrinting()` |
| **Exception Handling** | API errors and file write failures are caught and reported gracefully |
| **var keyword** | `var cep = leitura.nextLine()` — local type inference from Java 10 |

---

## How to Run

**Prerequisites:** Java 18+ · IntelliJ IDEA or Eclipse · GSON on classpath

```bash
git clone https://github.com/victorhubarb/zipcodefinder.git
cd zipcodefinder
```

Open in your IDE, add GSON to the classpath, run `Main.java`, and enter any valid Brazilian CEP. The app prints the address and saves it as `<CEP>.json`.

---

## Author

**Victor Hugo Barbosa**
[GitHub](https://github.com/victorhubarb) · [LinkedIn](https://www.linkedin.com/in/victorhbarbosa/)
