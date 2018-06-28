# Tests and TDD

<hr>
<p>Stephan Müller | <a href="mailto:smueller@suse.com">smueller@suse.com</a></p>
<p>Ceph Dashboard F2F 2018</p>

---

### What this talk tries to cover

* Why, what and when use tests
* Difference between unit and full integration tests
* Concept of TDD
* Ceph dashboard

---

# Why, what and when use test

--

### Why unit testing

* Avoid regression (f.e. merge conflicts)
* Bulletproof refactoring (Trust in tests)
* Saves time on the long run
* Documenting what the code does
* Avoid legacy code

--

### Why E2E tests

* Avoid system regression
* Make sure systems communicate as expected
* Test the whole system in a working environment

--
### What to cover -> Behavior

* Scenarios
* Inputs and outputs

--

### When to write tests

* On time, f.e. test against a bug
* Lay out requirements (Tests first)
* Before the code is in
* Best: before writing (TDD)

--

### How do we write good unit tests

* Test behavior
* Only mock externals (API and 3rd Party)
* Stub out results that are not needed
* Don't just look after code coverage
* Refactor tests before submitting
* Write them so you can trust them

---

# Full integration VS unit tests

--
### Full integration tests (end-to-end tests)

* Test if backend and frontend communicate as expected
* Each tests touches a lot of files
* Finds bugs in backend and frontend
* Needs a hole environment
* Not as easy to write as unit tests

--
### E2E vs unit tests

Topic | E2E | unit 
--- | --- | ---
Speed | slow | fast
Tests needed | few | many
Error finding | fishy | easy
Test consistent | no | yes
Test system integration | yes | no

---

# TDD - Test driven development

--
### Concept

Iterates in short cycles over three phases, in short:

<img src="images/tdd_flow.gif" style="background:none; border:none; box-shadow:none;">

--
### Phase 1 - Write a failing test

1. Extend or create a test until it fails.
2. Stop as soon as it fails.

Benefit -> The test can fail

--
### Phase 2 - Make the test pass

1. Extend or create production code that makes the test pass.
  * Use the simplest solution
2. Stop as soon as the test passes.

* Benefit -> fast progress

--
### Phase 3 - Refactor

Refactor tests and productive code

Benefits:
* Clean and fast code
* Only the last changes have to be refactored

---
# Ceph Dashboard

--
### Current State

* Currently we have 395 Tests in 112 test suites
  * 3.5 Tests per suite
* We need a lot more tests per suite

--
### Outlook

* Complexity will evolve
* More requirements
* Change existing code on daily bases

-> Adding unit tests and usage of TDD will help here
