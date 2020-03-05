# Model #

This document describes the model for the i-on system.

# Concepts #

## `CalendarTerm` ##
- Represents a calendar period such as 2019/2020-Winter.
- A typical term is a semester, however other institutions may use different time spans.
- A term should have a human readable unique identifier (e.g. `s1920v`).
- Attributes
  - Unique human readable identifier.
  - Start date.
  - End date.
- Relations
  - ?  
- Questions:
  - Are start and end date really necessary?

## `Programme` ##
- Represents a graduation programme such as LEIC or MEIC.
- A programme has a curricular structure
  - The structure is composed by a set of _offers_.
  - Each _offer_ is composed by a `CurricularUnit`.
    - An offer may have restrictions, such as the `CurricularTerms` where that offer can be used.
- Attributes
  - Name.
  - Unique short name (i.e. acronym).
  - Term size
    - E.g. 6 terms for LEIC, 4 terms for MEIC.
- Relations
  - Zero or more `ProgrammeOffer`.

## `ProgrammeOffer` ##
- A `ProgrammeOffer` defines a `CurricularUnit` that can be _taken_, in the context of a `ProgrammeOffer`.
- A `ProgrammeOffer` may have a set of pre-conditions
  - E.g. The `CurricularTerm` set where the offer is available.
  - E.g. The `CurricularUnits` that are pre-requirements. 
- Attributes
  - Elective or optional.
- Relations
  - One `Programme`.
  - One `CurricularUnit`.

## `CurricularTerm` ##
- Represents the n-th term of a program structure.
  - A programme structure is divided into terms.
    - E.g. LEIC is divided into 6 terms, numbered from 1 to 6.
- Attributes.
  - Order (between 1 to N).

## `CurricularUnit` ##
- Represents, rather surprisingly, a curricular unit.
  - It has a coordinator.
  - It has an unique acronym (e.g. `LS`).
  - It has all the fields typically associated the _Ficha de Unidade Curricular_ (FUC).
    - E.g. Syllabus.
    - E.g. Learning outcomes.
    - E.g. Resources.
- Attributes
  - Unique name (e.g. `Software Laboratory`).
  - Unique acronym (e.g. `SL`).
- Relations
  - Zero or more `Class`.

## `Class` ##
- Alternative name: `CurricularUnitOffer`
- Represents the offering of a curricular unit on a `CalendarSemester`.
  - E.g. `LS/s1920v`.
- It should create a snapshot of most of the `CurricularUnit` attributes (e.g. Syllabus) so that we have an historical record of the `CurricularUnit` on a given calendar semester.
- Attributes
  - ?
- Relations
  - One `CurricularUnit`
  - Zero or more `Lecturer`
  - Zero or more `Task`
  - Zero or more `StudentGroup`

## `ClassSection` ##
- Sub-division of a `Class` with distinct lecturers, students and schedule.
- Relations
  - Zero or more `Lecturer`
  - Zero or more `StudentGroup``

## `StudentGroup`
- A set of students that will deliver something together. 
- Relations
  - Zero or more `Student`

## `Event`
- A typical calendar event (e.g. http://schema.org/Event)
- Can be associated to zero or more typed entities (e.g. `Class`)
- Can have a type (`intermediate-assessment`, `final-assessment`)
- Has "eventy" attributes

## `Task`
- Represents something that needs to be done (e.g. work assignment)
- Has a due date
- Is an `Event`? 

## `Person`
  - Just a person (or a dog, because this is the Internet)
