---
context:
  - "[[Software Engineering]]"
  - "[[Data Oriented Design]]"
  - "[[Computer Science]]"
---

# Lessons From Mike Acton

Lessons learned from Mike Acton

---

See [Mike Acton - Data Oriented Design and C++](https://www.youtube.com/watch?v=rX0ItVEVjHc)
See [Mike Acton -  Solving the Right Problems for Engine Programmers](https://www.youtube.com/watch?v=4B00hV3wmMY)

Extremely practical!

**Practice**: You should practice your craft every day.

**Version Serialized Data**: Always version your serialized data by default.

**Model First**: Model the target first however you can before actually building it.

**Multiple By Default**: Most systems will do the same thing multiple times, so design around that.

**Sample Systems**: Create systems that sample your other systems, in order to know what to optimize.

## Quotes

_The purpose of all programs, and all parts of those programs, is to transform data from one form to another._

- The Programmer's job is NOT to write code; The Programmer's job is to solve data transformation problems.

_If you don't understand the data you don't understand the problem._

_Understand the problem by understanding the data._

_Different problems require different solutions._

_If you have different data, you have a different problem._

_If you don't understand the cost of solving the problem, you don't understand the problem._

_If you don't understand the hardware, you can't reason about the cost of solving the problem._

_Everything is a data problem. Including usability, mainteance, debug-ability, etc. Everything._

_Solving problems you probably don't have creates more problems you definitely do._

_Rule of thumb: Where there is one, there are many. Try looking on the time axis._

_Software does not run in a magic fairy aether powered by the fevered dreams of CS PhDs._

- Software is real engineering that runs on real hardware to solve a real problem.

_Reason must prevail._

## Lies & Truths

WRONG: Software is a platform.
TRUTH: Hardware is the platform.

WRONG: Code designed around model of the world.
TRUTH: Design around the data, not an idealized world.

WRONG: Code is more important than data.
TRUTH: Solve how to transform data first, not code design.

