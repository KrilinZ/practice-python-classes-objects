<!-- hide -->
<div align="center">

# Practice Python Classes and Objects

[![Certified by 4Geeks Academy](https://img.shields.io/badge/4Geeks%20Academy-Certified%20Tutorial-2563eb?style=for-the-badge)](https://4geeks.com)
[![Auto-graded with LearnPack](https://img.shields.io/badge/LearnPack-Auto--graded-2563eb?style=for-the-badge)](https://github.com/learnpack/learnpack)
[![Open in GitHub Codespaces](https://img.shields.io/badge/Open%20in-Codespaces-fb5a1f?style=for-the-badge&logo=github)](https://codespaces.new/4GeeksAcademy/practice-python-classes-objects)

🇪🇸 [Leer esta página en español](https://github.com/4GeeksAcademy/practice-python-classes-objects/blob/HEAD/README.es.md)

</div>
<!-- endhide -->

Practice Python Classes and Objects is a LearnPack tutorial with 12 steps: one welcome guide plus 11 auto-graded exercises that go from defining your first class to polymorphism. Every exercise ships an `app.py` template and a `pytest` file, 39 tests in total. Grading is incremental, so you work through the steps in order. It runs in GitHub Codespaces or on your own machine, in English and Spanish.

<!-- hide -->
## 📋 About this tutorial

- **Difficulty:** easy
- **Estimated duration:** 12 hours
- **Steps:** 12 folders inside `exercises/` (1 intro + 11 coding exercises)
- **Automatic tests:** 39 `pytest` test functions spread over 11 `test.py` files
- **Technologies:** Python, object-oriented programming, classes, objects
- **Grading:** incremental
- **Languages:** English and Spanish (every exercise has `README.md` and `README.es.md`)
- **Runtime:** Python 3.10 dev container, `pytest` 6.2.5, LearnPack 5.0.13
<!-- endhide -->

## 🎯 What will you learn?

This tutorial covers the four pillars of object-oriented programming in Python, one concept per step, with no framework and no external dependency beyond `pytest`:

- Declaring a class and instantiating objects from it
- Initializing state with `__init__` and storing instance attributes
- Adding behavior through instance methods that use `self`
- Encapsulating state behind `_name` / `_age` conventions plus getters and setters
- Validating input and raising `ValueError` to keep objects consistent
- Implementing the dunder methods `__str__`, `__repr__` and `__eq__`
- Telling class attributes apart from instance attributes, and `@classmethod` from `@staticmethod`
- Modelling has-a relationships with composition
- Managing a collection of objects inside a container class
- Reusing behavior with inheritance and `super()`
- Applying polymorphism through a shared method contract

## 👀 What will you build?

There is no single final project here. You write 11 small, independent programs, each one solved in its own `app.py` and checked by its own test file:

1. **Create your first class** — declare `Person` and instantiate `student`. Two tests: the class exists and `student` is an instance of it.
2. **Constructor and initial state** — add `__init__(name, age)`, store `self.name` and `self.age`, and create `student` with `"John"` and `21`.
3. **Instance methods** — write `greet()`, which returns `"Hi, my name is John"`, and `have_birthday()`, which increases `age` by one.
4. **Basic encapsulation** — keep state in `_name` and `_age`, expose `get_name()` and `get_age()`, and write `set_age(new_age)` that returns `True` when it updates and `False` when the value is negative.
5. **Data validation** — reject an empty `name` or a negative `age` by raising `ValueError`, both in the constructor and in `set_age()`.
6. **Special methods** — return `"Person: John (21 years old)"` from `__str__`, `"Person(name='John', age=21)"` from `__repr__`, and compare two people by name and age in `__eq__`.
7. **Class attributes and methods** — keep a shared `population` counter, expose it with a `@classmethod`, and add a `@staticmethod` `is_adult(age)`.
8. **Composition** — build an `Address` class, put an instance of it inside `Person`, and return `"Miami, USA"` from `full_address()`.
9. **Object collections** — write a `Classroom` class that adds, finds, removes and counts `Person` objects held in a list.
10. **Inheritance and reuse** — extend `Person` into `Student` with a `cohort` attribute and override `describe()` while reusing the parent constructor with `super()`.
11. **Polymorphism and abstraction** — give `Animal` a `speak()` that raises `NotImplementedError`, implement it in `Dog` and `Cat`, and call both through the same `make_it_speak(animal)` function.

## 🎓 What do you need before starting?

You should already be comfortable with basic Python: variables, data types, conditionals, loops, lists and functions. The very first exercise assumes you know how to define a function and call it, and several exercises rely on f-strings to build return values.

You do **not** need previous experience with object-oriented programming, decorators or `pytest`. Everything about classes is introduced from zero, and the tests run for you.

If you are not there yet, warm up with [Learn Python Interactively (beginner)](https://4geeks.com/en/interactive-exercise/python-beginner-exercises) and [Learn Python Functions Interactively](https://4geeks.com/en/interactive-exercise/python-function-exercises).

## ✅ How does the automatic grading work?

Each coding exercise has a `test.py` file that imports your module and runs real assertions against it. Nothing is checked by pattern-matching your source code, so any implementation that behaves correctly passes.

1. Write your solution in `app.py`. The file starts almost empty, with a single comment line.

2. Press **Run** in the LearnPack interface to execute your file and see its output.

3. Press **Test**. LearnPack runs `pytest` on that exercise only and reports each assertion by name.

4. The test file imports the objects it needs straight from your module, with a line such as `from app import Person, student`. If any of those names is missing, the import fails and every test in the file fails at once, not just one.

5. When the whole file is green, click **Next** to move to the following exercise.

If you want to start over, each exercise has an untouched copy of its `app.py` stored in `.learn/resets/`, and a `solution.hide.py` you can compare against once you are done.

## 💡 What mistakes should you avoid?

These are the traps that trip people up even when the code looks right. Most come straight from what the assertions actually check; a couple come from the success criteria written into the exercise itself:

- **Printing instead of returning.** `greet()`, `describe()`, `full_address()` and `speak()` are all checked with equality assertions such as `assert student.greet() == "Hi, my name is John"`. A `print()` returns `None` and fails.
- **Returning truthy values instead of real booleans.** `set_age()` in exercise 4 and `is_adult()` in exercise 7 are asserted with `is True` and `is False`. Returning `1`, `0`, a non-empty string or `None` fails the identity check even though it would pass an `if`.
- **Getting the exact text wrong.** The strings are compared character by character: `"Person: John (21 years old)"` and `"Person(name='John', age=21)"`, with single quotes around the name inside `__repr__`. An extra space or a different word breaks it.
- **Incrementing the counter on the instance.** In exercise 7, writing `self.population += 1` creates a brand-new instance attribute and leaves the class attribute at zero. Use `Person.population += 1` so `get_population()` sees it.
- **Making `Animal` abstract with `abc`.** Exercise 11 asserts that `Animal().speak()` raises `NotImplementedError`, which means the base class has to be instantiable. Declaring it with `ABC` and `@abstractmethod` makes `Animal()` raise `TypeError` instead, and the test fails.
- **Forgetting the global objects.** Nearly every exercise expects a module-level instance with an exact name: `student`, `student_clone`, `bootcamp`, `dog`, `cat`. Defining the class alone is never enough.
- **Ignoring the instance the exercise asks for.** Exercise 10 states `Student("John", 21, "42")`, with the cohort as the string `"42"`, and the only assertion compares `student.describe()` against `"Name: John, Age: 21, Cohort: 42"`. Build that text with the exact labels and commas.
- **Declaring the student list at class level.** Exercise 9 puts "keeps its collection in an internal list initialized in `__init__`" among its success criteria, so write `self.students = []` there. A list defined in the class body is shared by every `Classroom` you create, and `bootcamp` ends up holding students you added somewhere else.
- **Leaving `input()` at the top level.** The test file imports `app`, so any code outside a function or class runs during the test and blocking calls will hang it.

## ❓ Frequently asked questions

### What is the difference between a class and an object in Python?

A class is the blueprint that describes what a type of object looks like and what it can do; an object, or instance, is one concrete thing built from that blueprint. In this tutorial `Person` is the class and `student = Person("John", 21)` is an object. One class, as many objects as you need, each one with its own state.

### Do I need to install anything to start?

No, if you open the repository in GitHub Codespaces. The dev container ships Python 3.10, Node 20, `pytest`, LearnPack and the LearnPack VS Code extension already configured. Installing locally is also supported and takes three commands.

### Do I have to complete the exercises in order?

Yes, and it is worth it. Grading is set to `incremental` and the content is cumulative: exercise 5 validates the constructor you wrote in exercise 2, exercise 10 inherits from the `Person` class you have been refining since exercise 1. Skipping ahead means re-reading concepts you already skipped.

### How do I know my answer is correct?

By running the tests. There are 39 test functions across the 11 coding exercises, from 2 in the first one up to 5 in the encapsulation and validation exercises. Each one is a real behavior check, so passing them means your object actually behaves as expected, not that it looks like the solution.

### What do I do if I break my `app.py`?

Every coding exercise keeps a pristine copy of its starter file in `.learn/resets/<exercise-name>/app.py`. Copy it back over your file and you are at square one, with no need to re-clone the repository.

### Is this tutorial free, and who owns the code I write?

Access costs nothing: the repository is public, so you can open it in Codespaces or clone it without paying. It ships no `LICENSE` file, so the tutorial content is not released under an open-source license and its rights stay with the authors. The solutions you type into `app.py` are yours.

<!-- hide -->
## 📝 Related tutorials

If you want to go deeper into object-oriented programming or into Python in general:

- [Learn Object Oriented Programming with Python](https://4geeks.com/en/interactive-exercise/object-oriented-programing-with-python)
- [Object Oriented Programing In Javascript](https://4geeks.com/en/interactive-exercise/object-oriented-programing-in-javascript)
- [Learn Python Loops and Lists Interactively](https://4geeks.com/en/interactive-exercise/python-loops-lists-exercises)
- [Master Python by Practice](https://4geeks.com/en/interactive-exercise/master-python-exercises)
- [Classes chapter in the official Python documentation](https://docs.python.org/3/tutorial/classes.html)

## 🚀 How to start

The fastest path is GitHub Codespaces, no local setup required:

1. Open the repository in a codespace:

    [![Open in GitHub Codespaces](https://img.shields.io/badge/Open%20in-Codespaces-fb5a1f?style=for-the-badge&logo=github)](https://codespaces.new/4GeeksAcademy/practice-python-classes-objects)

2. Wait for the container to finish building. It installs Python 3.10, `pytest`, LearnPack and the `@learnpack/python` plugin on its own.

3. Start the tutorial from the integrated terminal:

    ```bash
    learnpack start
    ```

4. Open the forwarded port in the browser tab that VS Code offers, and begin with `00-Welcome`.

## 💻 Local installation

If you prefer to work on your own machine, you need Python 3 and Node.js installed:

1. Clone the repository and enter the folder:

    ```bash
    git clone https://github.com/4GeeksAcademy/practice-python-classes-objects.git
    cd practice-python-classes-objects
    ```

2. Install the Python dependencies used by the tests:

    ```bash
    pip3 install pytest==6.2.5 pytest-testdox mock
    ```

3. Install LearnPack and its Python plugin:

    ```bash
    npm i @learnpack/learnpack@5.0.13 -g
    learnpack plugins:install @learnpack/python@1.0.6
    ```

4. Launch the tutorial:

    ```bash
    learnpack start
    ```

## 📚 How the exercises are organized

Everything lives inside `exercises/`, one folder per step, numbered so LearnPack can order them. The 11 coding folders share the same four files:

- **`README.md` and `README.es.md`** — the statement in English and Spanish, with the goal, the key concept, numbered instructions and the success criteria.
- **`app.py`** — your working file, delivered with a single placeholder comment.
- **`test.py`** — the `pytest` file that grades the exercise. It is worth reading: it is the exact contract your code has to satisfy.
- **`solution.hide.py`** — one valid solution, hidden by LearnPack while you work.

`00-Welcome` is the exception: it only has the two READMEs, because it explains the workflow and has nothing to solve. Outside `exercises/`, the interesting paths are `learn.json` (tutorial configuration) and `.learn/resets/` (untouched copies of every `app.py`).

## 🤝 Contributors

This tutorial is built and maintained by [4Geeks Academy](https://4geeks.com) and runs on [LearnPack](https://github.com/learnpack/learnpack), the engine behind its interactive tutorials.

Found a typo, an unclear statement or a test that does not behave as documented? Open an issue or a pull request in the [repository](https://github.com/4GeeksAcademy/practice-python-classes-objects).
<!-- endhide -->
