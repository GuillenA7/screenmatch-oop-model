# 🎬 ScreenMatch – Java Object-Oriented Programming Project

This project was developed as part of the **[Alura](https://www.aluracursos.com/) [ONE](https://www.oracle.com/mx/education/oracle-next-education/) – Java: Applying Object-Oriented Programming** course.  

It simulates a movie and series catalog application called **ScreenMatch**, designed to practice the core principles of **Object-Oriented Programming (OOP)** in Java.

> This repository contains the different stages of the ScreenMatch project, developed during the Java Object-Oriented Programming – ONE (Alura) training program.
> Each branch corresponds to a specific course within the program.

---

## 🧠 Project Overview

ScreenMatch is a console-based Java application where users can manage and rate movies and TV series.  

Throughout its development, the project explores key OOP pillars such as:

- **Encapsulation** – keeping data private and accessible through getters/setters.  
- **Inheritance** – sharing common properties and behaviors across classes.  
- **Polymorphism** – allowing objects to behave differently based on their type.  
- **Abstraction** – modeling real-world entities through meaningful classes.

---

## 🧩 Class Structure

```

com.aluracursos.screenmatch
│
├── modelos
│   ├── Titulo.java
│   ├── Pelicula.java
│   ├── Serie.java
│   └── Episodio.java
│
└── calculos
├── Clasificable.java
├── FiltroRecomendacion.java
└── CalculadoraDeTiempo.java

````

### 📄 Key Classes
- **`Titulo`** – Base class representing general media (title, release year, duration, rating, etc.).
- **`Pelicula`** – Extends `Titulo`; includes specific behavior for movies.
- **`Serie`** – Extends `Titulo`; includes attributes like seasons, episodes, and episodes per season.
- **`Episodio`** – Represents an episode that belongs to a series.
- **`Clasificable` (interface)** – Defines a contract for classes that can be rated.
- **`FiltroRecomendacion`** – Applies recommendation logic based on ratings.
- **`CalculadoraDeTiempo`** – Calculates total viewing time of selected titles.

---

## ⚙️ Features Implemented

- Add and manage movies, series, and episodes.
- Rate titles with stars based on average ratings.
- Use interfaces to unify rating behaviors (`Clasificable`).
- Apply inheritance to share attributes between `Pelicula`, `Serie`, and `Episodio`.
- Implement a recommendation filter that suggests popular or highly rated content.
- Demonstrate polymorphism through class hierarchies and interface implementation.

---

## 🧪 Example Usage

```java
Pelicula encanto = new Pelicula();
encanto.setNombre("Encanto");
encanto.setDuracionEnMinutos(120);
encanto.evaluar(9);
encanto.evaluar(8);

Serie casaDragon = new Serie();
casaDragon.setNombre("House of the Dragon");
casaDragon.setTemporadas(2);
casaDragon.setEpisodiosPorTemporada(10);
casaDragon.setDuracionEnMinutosPorEpisodio(50);

Episodio episodio = new Episodio();
episodio.setNombre("La Casa Targaryen");
episodio.setSerie(casaDragon);
episodio.setTotalVisualizaciones(300);

FiltroRecomendacion filtro = new FiltroRecomendacion();
filtro.filtra(encanto);
filtro.filtra(episodio);
````

---

## 🛠️ Technologies Used

* **Java 17+**
* **IntelliJ IDEA**
* Object-Oriented Programming (OOP) principles
* Standard Java SDK (no external dependencies)

---

## 🧾 Learning Objectives

Through this project, you will:

* Understand the **structure of classes and objects** in Java.
* Learn to design **hierarchies using inheritance**.
* Apply **interfaces** and **polymorphism** for extensibility.
* Practice **clean, modular, and reusable code**.

---

## 👩‍💻 Author

**Genesis (Instructor: Alura ONE Program)**

Adapted and practiced by *Jose Adrian Guillen Lamas* as part of the **Java Object-Oriented Programming G9 – ONE** training.

---

## 📚 License

This project is for educational purposes as part of the Alura ONE learning track.

Feel free to clone, modify, and extend it for your own practice.

---

⭐ *“Practice makes understanding. Code, break, fix, and learn — that’s the path to mastery.”*
