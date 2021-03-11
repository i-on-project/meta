# About
A registry of vocabulary shared among all projects.

# Abstract
These concepts are not tied to any specific context.

* `Offer`: to provide a service
	- to present an option of satisfying a requirement
	- [Spec](https://schema.org/Offer)
	- e.g. selling tickets for an event

* `Event`: an occurrence
	- [Spec](https://schema.org/Event)
	- e.g. a meeting

* `Section`: a subdivision of a body
	- **alias of** `Subdivision`
	- e.g. the navy is a subdivision of the national armed forces

# Academic
* `Course`: 
	- **alias of** `Curricular Unit`
	- [Spec](https://schema.org/Course)
	- e.g. Software Laboratory

* `Class`: an instance of `Course` in a given `Academic Term`
	- **alias of** `Course Offer`
	- **alias of** `Course Instance`
	- [Spec](https://schema.org/CourseInstance)
	- e.g. Software Laboratory aka SL, v1920

* `Class Section`: a subdivision of a `Class`
	- e.g. Software Laboratory 2, v1920

* `Programme`: an academic plan of `Courses`
	- **alias of** `Program`
	- **alias of** `Educational Occupational Program`
	- [Spec](https://schema.org/EducationalOccupationalProgram)
	- e.g. Computer Science and Computer Engineering, aka CSCE

* `Programme Offer`: a `Course` in the context of a `Programme`
	- e.g. in the LEEIRT `Programme` Internet Networks is an elective `Course` which will provide 6 Credits upon completion
	- e.g. in the CSCE `Programme` Internet Networks is an optional `Course` which will provide 6 Credits upon completion
	
# Time
* `Duration`: defines the amount of intervening time in a time interval
	- [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601#Durations)
	- [Spec](https://schema.org/Duration)

* `Academic Year`: `Duration` of a year from a starting date, during which instances of academic `Events` will be active
	- doesn't necessarily align with the calendar year
	- [Spec](https://en.wikipedia.org/wiki/Academic_year)
	- e.g. 1920 is the `Academic Year` spanning 12 months from a starting date in September

* `Academic Term`: a portion of an `Academic Year`, the time during which an educational institution holds academic `Events`
	- `Semester` (a term of an `Academic Year` divided in 2)
	- `Trimester` (a term of an `Academic Year` divided in 3)
	- `Quarter` (a term of an `Academic Year` divided in 4)
	- [Spec](https://en.wikipedia.org/wiki/Academic_term)
	- e.g. the summer `Semester` of the 1920 `Academic Year`
	
* `Calendar Term`: the nth `Academic Term` of a `Programme` for any starting date
	- e.g. the `Course` SL is available during the 4th `Calendar Term` of the CSCE `Programme`
	- e.g. the CSCE `Programme` spans 3 `Academic Years` (semestral), a total of 6 `Calendar Terms`
	
* `Schedule`: weekly distribution of a regularly occurring `Event`
	- indicates the days of week during which the `Event` takes place, each with its own start time and `Duration`
	- has its own `Duration` (it expires)
	- [Spec](https://schema.org/Schedule)
	- e.g. a workshop opened during Mondays (1pm-2pm) and Tuesdays (3pm-4pm), active from January to April
