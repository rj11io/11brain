# 11brain framework
Here are all the guidelines that i want to register for the first version / iteration of our brain framework. We will start with a design i came up with that can fulfill my immediate work, and continuously improve on the framework over time

## Immediate goals
- create a simple framework to manage my personal projects
- simple but flexible folder structure
- knowledge base for the peronal projects portfolio
- register and follow the global and project guidelines
- ability to plan many of tasks across multiple projects, group and prioritize them, track and execute the work
- execute only 1 tick at a time
- ability to remember what has been done in the short and long term
- ability to track back changes made and understand what led to that change and what it impacted in the present (possible bugs or breaking)
- an initialization prompt i can use on a new thread and pick up the necessary context to understand what has been done and continue the work
- robust against interruptions (mainly from token usage limits or internet failures)
- self-improving: we want to design a way to keep track of the pros and cons of the current version of the framework and evolve it in the future / when it makes sense
- sleep-mode: when we are a bit limited with token usage, but want to have a continuous work flow, researching the best way to have the agent "sleep" after doing a task, sleep value should be a var that can be a ms value or a multiplier. defaulting to "2x" meaning the agent should sleep for twice the amount of time the previous task took. obviously during sleep the agent should not generate tokens or cause any action that can cause usage.

i want to be able to plan work ahead, and not get blocked by execution. meaning having a well defined plan of work, with the execution slightly lagging behind. also flexible enough to plan work in other projects without blocking or interrupting the execution on current projects. this goal in particular is hard to define, but comes from the disadvantages of acting as a single human operator with constant interruptions. an example is, i would like to have preplanned work being done while i plan this very document for future work, without creating conflicts or interruptions.

to achieve this in this first version we are assuming that the "brain" folder lives as a sibling of the projects it is managing. we can follow the folder structure definitions from `../global`. build a knowledge base from the seed information in `../projects`.

have a short (`ram`) and long (`rom`) term memory system. in `rom` we want to register goals and long term tasks, track and prioritize them in the most efficient and compounding way, and understand what's in progress and what is completed. in `ram` we want to register the micro actions of the current task, giving us the ability to recover from interruptions, when tasks are completed these logs should be archived to `rom` to make it easier to back track. let's design asimple flexible robust folder structure for our memory system.

one thing to note about the memory system, the project knowledge base, and AGENTS.md reference: we want to keep track of the things we work on projects (features, improvements, bugfixing, refactors, etc), and NOT about the results, products, or outputs of the projects themselves.

we also need a simple register we can add to an `AGENTS.md` to reference our brain in a way that makes sense for AI agents to work, and avoid the default `memory.md` or other default memory systems in favor of using our brain framework.

this version of the brain should work best with a single machine, on a single thread, executing 1 tick at a time. with being easy to start a new thread. these immediate goals are the highest priority at the moment.

## Short term goals
after achieving our immediate goals, we can focus on the next steps, which is mainly about publishing / productizing the brain framework. evolve the brain framework to fit multiple projects, single project, multiple modules inside a project, a mix and match of all these options nested. the purpose of this project is to become more than a personal tool, it's also a proof of work, a portfolio piece, and a tool that other people can use for themselves. there are no hard specifications yet, but we should account for this. low priority.

## Long term goals
after achieving our short term goals, it's time to focus on the long term goals, which are about evolving the brain framework, and having the ability to have multiple machines with multiple threads working on multiple projects in parallel and at the same time. no extra specifications for now but keep this in mind. low priority.
