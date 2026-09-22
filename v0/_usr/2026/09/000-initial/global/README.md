# Global rules
here are the main fundamental guidelines, guardrails, and practices that i want to enforce on the global brain framework

## _usr
let's use the keyword `_usr` when refering to the human operator. when you find any folder named `_usr` assume it's reserved for the human operator to draft temporary files inside and ignore it's contents in order to not pollute your context unless specifically referred to it to read instructions.

we want to include this rule in our AGENTS.md reference for the brain framework

## Priority rules
- lower the value, higher the priority
- 0 highest priority
- 999 extremely low priority

priority will be the main indicator of the order of the tasks to execute, it's value can be initially set as a rough estimate and can change depending on further analysis, the value can be justified through many lenses such as criticality, urgency, difficulty, but the main determining factors should be efficiency, impact, and compounding effect. concrete and real example:
- i want to propagate my blog boilerplate across a few different surfaces with high priority
- but i also want to improve my blog markdown components to support charts and other data visualisations with lower priority
you should be able to understand that it's much more efficient to do the improvements before the propagation, rather than propagate the blog and then propagate the improvements. you should alert the `_usr` when you find such cases, and prioritize things accordingly when planning by yourself
