# 🎬 ScreenMatch – Working with Java Lists and Collections

> 🧭 This branch corresponds to the **Java: Working with Lists and Data Collections** course
> 
> from the [Alura](https://www.aluracursos.com/) [ONE](https://www.oracle.com/mx/education/oracle-next-education/) program.
> 
> It continues directly from the previous branch: `curso2-aplicando-poo`.

---

## 🧠 Project Overview

This version of **ScreenMatch** expands the original object-oriented project to include
**Java Collections Framework**, exploring **lists, ordering, interfaces, and maps**.

The goal is to understand how to organize, compare, and manipulate groups of objects efficiently —

using tools like `List`, `ArrayList`, `LinkedList`, `Collections`, and `HashMap`.

---

## 🧩 Key Topics Learned

In this stage, you applied the following key Java concepts:

* **Interfaces and abstraction** (`List`, `Comparable`, `Map`)
* **Collections Framework** (`ArrayList`, `LinkedList`, `Vector`, `Stack`)
* **Sorting and ordering** with `Comparable` and `Comparator`
* **Maps and HashMaps** for key-value data structures
* **Programming to interfaces** (using `List` instead of a concrete implementation)
* **Polymorphism in collections** (storing objects of subclasses in generic lists)

---

## 🧱 Project Structure

```
com.alura.screenmatch
│
├── modelos
│   ├── Titulo.java
│   ├── Pelicula.java
│   ├── Serie.java
│   └── Episodio.java
│
├── calculos
│   ├── Clasificable.java
│   ├── FiltroRecomendacion.java
│   └── CalculadoraDeTiempo.java
│
└── principal
    ├── Principal.java
    └── PrincipalConListas.java
```

### 🗂️ Highlights of this version

* **`Titulo`** now implements `Comparable<Titulo>`, allowing alphabetical ordering.
* **`Serie`** overrides `toString()` to print formatted details.
* **`PrincipalConListas`** demonstrates:

  * Use of `List<Titulo>` and `LinkedList`.
  * Sorting with `Collections.sort()` (natural order) and `Comparator.comparing()`.
  * Iterating polymorphically through a list of `Titulo` objects.
  * Filtering and classification through interfaces.
* **Introduction to `Map` and `HashMap`** for associating keys with values efficiently.

---

## ⚙️ Features Implemented

* Create and manage collections of movies, series, and episodes.
* Store titles in generic lists (`List<Titulo>`).
* Sort lists alphabetically or by release year.
* Apply recommendation filters using the `Clasificable` interface.
* Demonstrate the difference between `ArrayList` and `LinkedList`.
* Understand other list types like `Vector` and `Stack`.
* Learn how to use `Map` and `HashMap` to manage data pairs (key–value).

---

## 🧪 Example Usage

```java
List<Titulo> lista = new LinkedList<>();

Pelicula encanto = new Pelicula("Encanto", 2021);
encanto.evalua(9);

Pelicula avatar = new Pelicula("Avatar", 2023);
avatar.evalua(6);

Serie lost = new Serie("Lost", 2000);

lista.add(encanto);
lista.add(avatar);
lista.add(lost);

Collections.sort(lista);  // natural order (by name)
System.out.println("Sorted titles: " + lista);

lista.sort(Comparator.comparing(Titulo::getFechaDeLanzamiento));
System.out.println("Sorted by release date: " + lista);
```

### Using a HashMap

```java
Map<String, Integer> ratings = new HashMap<>();
ratings.put("Encanto", 9);
ratings.put("Avatar", 6);

System.out.println("Encanto rating: " + ratings.get("Encanto"));
```

---

## 🧾 Learning Objectives

Through this part of the course, you learned to:

* Use **lists and collections** to manage groups of objects.
* Apply **sorting mechanisms** for custom and natural orderings.
* Write **cleaner and more flexible code** by programming to interfaces.
* Use **maps** to store relationships between keys and values.
* Recognize when to use **ArrayList**, **LinkedList**, or other list types.
* Strengthen your understanding of **interfaces, polymorphism, and abstraction** in real-world scenarios.

---

## 🛠️ Technologies Used

* **Java 17+**
* **IntelliJ IDEA**
* **Java Collections Framework**
* **Comparable & Comparator**
* **Map and HashMap**

---

## 👩‍💻 Author

**Bruno Darío Fernández Ellerbach (Instructor: [Alura](https://www.aluracursos.com/) [ONE](https://www.oracle.com/mx/education/oracle-next-education/) Program)**

Adapted and practiced by *Jose Adrian Guillen Lamas* as part of the

**Java Object-Oriented Programming G9 – ONE** formation track.

---

## 📚 License

This project is for educational purposes as part of the Alura ONE learning program.
Feel free to clone, modify, and extend it for your own learning.

---

> ⭐ *“Collections are the backbone of Java programming — master them, and data flows naturally.”*

---

> 🔄 **Previous branch:** `curso2-aplicando-poo`
