# Zip Code Finder

A small Java console program that looks up a Brazilian postal code (CEP) on the [ViaCEP](https://viacep.com.br) API, prints the address, and saves it as a JSON file named after the CEP.

I wrote it to practice calling an HTTP API and handling JSON in plain Java, without a framework around it.

## How it works

1. `Main` reads a CEP from the console.
2. `ConsultaCep` sends a GET request to `https://viacep.com.br/ws/<cep>/json` with `java.net.http.HttpClient`.
3. GSON turns the response into an `Endereco` record (cep, logradouro, complemento, localidade, uf, bairro).
4. `GeradorDeArquivo` writes it, pretty-printed, to `<cep>.json`.

Example of a saved file for `01001000`:

```json
{
  "cep": "01001-000",
  "logradouro": "Praça da Sé",
  "complemento": "lado ímpar",
  "localidade": "São Paulo",
  "uf": "SP",
  "bairro": "Sé"
}
```

The prompts and error messages are in Portuguese.

## Run it

Requires JDK 17 or newer (the record needs 16+) and the [GSON jar](https://mvnrepository.com/artifact/com.google.code.gson/gson). There is no build tool, so compile with the jar on the classpath:

```bash
git clone https://github.com/victorhubarb/zipcodefinder.git
cd zipcodefinder
javac -cp gson-2.10.1.jar -d out src/*.java
java -cp "out:gson-2.10.1.jar" Main     # on Windows use ; instead of :
```

Type an 8-digit CEP when prompted. The JSON file is written to the folder you ran it from.

## Known gaps

- A well-formed CEP that does not exist makes ViaCEP answer with `{"erro": true}`. The program does not check for that, so it saves an empty address to `null.json`.
- Input is not validated before the request is sent.
- There is no Maven or Gradle setup, so GSON has to be added by hand.
- No tests.

---

Victor Hugo Barbosa · [GitHub](https://github.com/victorhubarb) · [LinkedIn](https://www.linkedin.com/in/victorhbarbosa/)
