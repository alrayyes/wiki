---
id: 9e3bc9a2-cda1-4097-81ea-6e15736a5e9b
title: Impact of Multifaceted Abstraction on Key Quality Attributes
---

# Understandability

A class with the Multifaceted Abstraction smell has multiple aspects
realized into the abstraction, increasing the cognitive load on the
user. When a class has multiple responsibilities, it takes more time and
effort to understand each responsibility, how they releate to each other
in the abstraction, etc. This adversely affects its understandability.

# Changeability & extensibility

When a class has multiple responsibilities, it is difficult to determine
which members should be modified to support a change or enhancement.
Further, a modification to a member may impact unrelated
responsibilities within the same class; this in turn can have a ripple
effect accross the entire design. For this reason, the amount of time
and effort required to change or extend the class while still ensuring
that the reulting ripple effect has no adverse impact on the correctness
of the software is considerably greater. These factors negatively impact
changeability and extensibility.

# Reusability

Ideally, a well-formed abstraction that supports a single responsibility
has the potential to be reused as a unit in a different context. When an
abstraction has multiple responsibilities, the entire abstraction must
be used even if only one of the responsibilities needs to be reused. In
such a case, the presence of unnecessary responsibilities may become a
costly overhead that must be addressed. Thus, the abstraction's
reusability is compromised. Further, in an abstraction with multiple
responsibilities, sometimes the responsibilities may be intertwined. In
such a case, even if only a single responsibility needs to be reused,
the overall behavior of the abstraction may be unpredicatable, again
affecting its reusability.

# Testability

Often, when a class has multiple responsibilities, these
responsibilities may be tightly coupled to each other, making it
difficult to test each responsibility separately. This can negatively
impact the testability of the class.

# Reliability

The effects of modification to a class with intertwined responsibilities
may be unpredictable and lead to runtime problems. For instance,
consider the case in which each responsibility operates on a seperate
set of variables. When these variables are put together in a single
abstraction, it is easy to mistakenly access the wrong variable,
resulting in a runtime problem.
