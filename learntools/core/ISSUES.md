Issues
------
- Globals binding statefulness (see comment in `globals_binder.py`)

Feature requests / Nice-to-haves
-----
- add some tests to learntools.core
- rework `bind_exercises`. Add overarching "Exercise" objects for containing Problems. See comments in `utils.py`.
- Helpers for exploiting a canonically correct implementation of a function for `FunctionProblem`s.
- add "abstract attribute" enforcement (see comment at top of problem.py)
- more factory syntax conveniences for problem creation
- convenient syntax for per-variable custom checking?
- Some kernel support for automagically running standard setup code in learn notebooks
- Some convenience for initializing an exercise module with standard boilerplate (imports at top, `bind_exercises` stuff at the bottom)
- Make ProblemViews (and Problems?) aware of their canonical `bind_exercises` name for more helpful messages. (See Hint "coda" for example)
- revive/complete scripts for autogenerating (/autotesting) exercise notebook skeleton 
- some helper for checking variable types in Problem.check() implementations
- generalization of above: assert wrappers (similar to the ones that come with unittest) with reasonable default failure messages.
- some helper for testing notebooks to exec a problem's CodeSolution source and verify that checking passes?
- in RichText, replace angle brackets with html entities (this is a frequent problem when passing in strings that include the result of calling `type()` on something, which gives you something like `"<class 'str'>"`
- would be nice to extract the 'check whether empty function body has been touched as proxy for attemptedness' logic out of `FunctionProblem`. See embeddings course ex2 `RecommendFunction` for an example where this would be useful (a sort of function problem not amenable to basic test cases, need custom check fn).
    - similarly for extracting out logic for checking whether variable has its default value from static equality checking problems. 
        - could take out the stuff around _expected, and check_whether_attempted in `EqualityCheckProblem` and turn it into some kind of mixin
    - like, maybe some declarative way to specify attemptedness-checking logic as like, "all these variables have non-default values", "any of these variables have non-default values", "this function is non-empty", etc.
    - and/or some easy way to raise unattempted inside a custom checking fn? (I think, as the code is currently structured, the check function is somehow past the point of no return for declaring unattempted)
