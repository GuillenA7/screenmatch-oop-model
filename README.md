# 🎬 ScreenMatch – Java API Consumption & File Persistence

> 🧭 This branch corresponds to the **Java: Consuming APIs, Writing Files, and Handling Errors** course
> from the [Alura](https://www.aluracursos.com/) [ONE](https://www.oracle.com/mx/education/oracle-next-education/) program.
> It continues directly from the previous branch: `curso3-colecciones`.

---

## 🧠 Project Overview

In this stage of the **ScreenMatch** project, the application evolves from working with in-memory data to interacting with **external APIs** and **persisting data in files**.

The main goals are to:

* Learn how to **consume APIs** using Java’s `HttpClient`.
* Parse and manipulate **JSON** responses with **Gson**.
* Handle **errors and exceptions** gracefully.
* Save and read data from **local files** using the `java.io` package.

This version introduces real-world concepts such as data persistence, serialization, and robust exception handling.

---

## ⚙️ Features Implemented

* 🔗 **API Consumption** using Java’s built-in `HttpClient`.
* 🔍 **JSON parsing** with the **Gson** library.
* 🧾 **Object transformation** between `TituloOmdb` (DTO) and domain model `Titulo`.
* 💾 **File writing and reading** using `FileWriter` and `Scanner`.
* 🚨 **Custom exception handling** with `ErrorEnConversionDeDuracionException`.
* 🌀 **Loop-based input** to perform multiple API searches.
* 🧱 **JSON persistence** of user-searched titles (`titulos.json`).
* 🧩 **Code organization** and separation of concerns following OOP best practices.

---

## 🧱 Project Structure

```
com.alura.screenmatch
│
├── calculos
│   ├── Clasificable.java
│   ├── FiltroRecomendacion.java
│   └── CalculadoraDeTiempo.java
│
├── excepcion
│   └── ErrorEnConversionDeDuracionException.java
│
├── modelos
│   ├── Titulo.java
│   ├── Pelicula.java
│   ├── Serie.java
│   ├── Episodio.java
│   └── TituloOmdb.java
│
└── principal
    ├── Principal.java
    ├── PrincipalConListas.java
    └── PrincipalConBusqueda.java
```

---

## 🧪 Example: Consuming an API and Saving Results

```java
Scanner lectura = new Scanner(System.in);
List<Titulo> titulos = new ArrayList<>();
Gson gson = new GsonBuilder()
    .setFieldNamingPolicy(FieldNamingPolicy.UPPER_CAMEL_CASE)
    .setPrettyPrinting()
    .create();

while (true) {
    System.out.println("Enter a movie name (or type 'salir' to exit): ");
    var busqueda = lectura.nextLine();

    if (busqueda.equalsIgnoreCase("salir")) break;

    String direccion = "https://www.omdbapi.com/?t=" +
            busqueda.replace(" ", "+") +
            "&apikey=YOUR_API_KEY";

    try {
        HttpClient client = HttpClient.newHttpClient();
        HttpRequest request = HttpRequest.newBuilder().uri(URI.create(direccion)).build();
        HttpResponse<String> response = client.send(request, HttpResponse.BodyHandlers.ofString());

        TituloOmdb miTituloOmdb = gson.fromJson(response.body(), TituloOmdb.class);
        Titulo miTitulo = new Titulo(miTituloOmdb);

        titulos.add(miTitulo);
    } catch (Exception e) {
        System.out.println("Error: " + e.getMessage());
    }
}

try (FileWriter escritura = new FileWriter("titulos.json")) {
    escritura.write(gson.toJson(titulos));
}
```

---

## 🧩 Key Learnings

* How to **consume REST APIs** and handle HTTP responses.
* How to **convert JSON ↔ Java objects** using Gson.
* How to **persist and read data** with the `java.io` package.
* How to design code with **low coupling and high cohesion**.
* How to **handle exceptions** effectively, including custom runtime exceptions.
* How to **serialize and store lists of objects** in readable JSON format.

---

## 🛠️ Technologies Used

* **Java 17+**
* **HttpClient API (java.net.http)**
* **Gson (Google JSON library)**
* **java.io package (FileWriter, File, Scanner)**
* **IntelliJ IDEA**

---

## 👩‍💻 Author

**Bruno Darío Fernández Ellerbach (Instructor: Alura ONE Program)**

Adapted and practiced by *Jose Adrian Guillen Lamas*

as part of the **Java Object-Oriented Programming G9 – ONE** formation track.

---

## 📚 License

This project is for educational purposes as part of the **Alura ONE** program.

Feel free to clone, adapt, and extend it for learning and experimentation.

---

⭐ *“From consuming data to persisting it — this stage connects Java to the real world.”*

---

> 🔄 **Previous branch:** `curso3-colecciones`
