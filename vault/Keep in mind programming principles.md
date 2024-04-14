
- DRY - don’t repeat yourself
- KISS - keep it simple stupid, keep it short and simple
- YAGNI - you aren’t gonna need it, “Always implement things when you actually need them, never when you just foresee that you need them”

SOLID
-   [Single Responsibility Principle](https://www.digitalocean.com/community/conceptual_articles/s-o-l-i-d-the-first-five-principles-of-object-oriented-design#single-responsibility-principle) - A class should have one and only one reason to change (i.e. code modified), meaning that a class should have only one job.
-   [Openness for extension and closedness for modification](https://www.digitalocean.com/community/conceptual_articles/s-o-l-i-d-the-first-five-principles-of-object-oriented-design#open-closed-principle) - class should be extendable without modifying the class itself
-   [Common Closure Principle](https://ericbackhage.net/clean-code/the-common-closure-principle/#:~:text=The%20Common%20Closure%20Principle%20(CCP,have%20multiple%20reasons%20to%20change.) - The classes in a component should be closed together against the same kind of changes
-   [Independence in Clean Architecture](https://blog.cleancoder.com/uncle-bob/2012/08/13/the-clean-architecture.html) - independent of frameworks (i.e. unlimited by feature laden packages), testable in isolation, independent of UI (i.e. UI can be changed easily), independent of database (i.e. business rules not bound to database), independent of external agency (i.e. business rules dont know anything at all about the outside world).
