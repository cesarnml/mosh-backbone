# Backbone.js Cheatsheet

- [Backbone.js Cheatsheet](#backbonejs-cheatsheet)
  - [Lessons](#lessons)
  - [Notes](#notes)
    - [Models](#models)

## Lessons

- [x] ~~_Lesson 01_~~ [2025-03-22]
- [x] ~~_Lesson 02_~~ [2025-03-22]
- [x] ~~_Lesson 03_~~ [2025-03-22]
- [x] ~~_Lesson 04_~~ [2025-03-22]
- [x] ~~_Lesson 05_~~ [2025-03-22]
- [x] ~~_Lesson 06_~~ [2025-03-22]
- [x] ~~_Lesson 07_~~ [2025-03-22]
- [x] ~~_Lesson 08_~~ [2025-03-24]
- [x] ~~_Lesson 09_~~ [2025-03-24]
- [x] ~~_Lesson 10_~~ [2025-03-24]
- [x] ~~_Lesson 11_~~ [2025-03-24]
- [ ] Lesson 12
- [ ] Lesson 13
- [ ] Lesson 14
- [ ] Lesson 15
- [ ] Lesson 16
- [ ] Lesson 17
- [ ] Lesson 18
- [ ] Lesson 19
- [ ] Lesson 20
- [ ] Lesson 21
- [ ] Lesson 22
- [ ] Lesson 23
- [ ] Lesson 24
- [ ] Lesson 25
- [ ] Lesson 26
- [ ] Lesson 27
- [ ] Lesson 28
- [ ] Lesson 29
- [ ] Lesson 30
- [ ] Lesson 31
- [ ] Lesson 32
- [ ] Lesson 33
- [ ] Lesson 34
- [ ] Lesson 35
- [ ] Lesson 36
- [ ] Lesson 37
- [ ] Lesson 38
- [ ] Lesson 39
- [ ] Lesson 40
- [ ] Lesson 41
- [ ] Lesson 42
- [ ] Lesson 43
- [ ] Lesson 44
- [ ] Lesson 45

## Notes

- `Backbone` is a lightweight library for structuring JS code. It operates under the `MVC` design framework.
- `MVC` promotes `separation of concerns` to create easily extendible and loosely couple application while keeping code maintainable code
- Backbone Components:
  - 1. Events: Ability for an object to pub/sub events
  - 2. Models: Application state
  - 3. Collections: A set of Models
  - 4. Views: Render models and listen for DOM/model events
  - 5. Routers: To create SPAs

### Models

- `Models`:
  - Containers for application data
  - JS objects with changing tracking mechanism and pub/sub and ajax request to server
    - `person.save({ success: () => {}})`
  - When a model is created `new Model()` Backbone automatically calls `model.initialize()` method
  - Backbone Models are hash maps.
    - Must use `.set` when setting Model attributes
    - Read with `.get`
    - Delete with `.unset`
    - Delete all with `.clear`
    - Get a JSON with `.toJSON`
    - Check for attribute existence with `.has`
    - When instantiating the model can use `.defaults` object to set default value for attributes
    - `.validate()` method called whenever attributes are set on a model ... must return undefined or string if not valid; method is passed `model.attrs` as a parameter

```js
var Song = Backbone.Model.extend({
  validate: function (attrs) {
    if (!attrs.title) {
      return "Title is required";
    }
  },
});
```

- `Inheritance` from a Parent model can be done via the `var Child = Parent.extend()` method on the Parent class
