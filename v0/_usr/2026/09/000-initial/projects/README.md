# 11portfolio rules
here are the guidelines, guardrails, and practices that i want to register and enforce specifically on my personal projects portfolio (11portfolio)

## Goals of the portfolio
this portfolio exists for multiple reasons:
- build tools and solutions that i need for myself
- build it in public to show other people how i work and how i think
- show how things work under the hood and behind the scenes
- organize it in a nice portfolio and get better professional leads and opportunities
- give other people access to the tools i build for myself
- create high value opportunitties in business
- monetise each project the way it makes most sense

## Portfolio structure
the brand is `rj11io` and its entry point is `rj11.io` and the project code is `11io`. every other project follows the format `11{code}` and points to a `{code}.rj11.io`. examples:
- `11ai` -> `ai.rj11.io`
- `11blog` -> `blog.rj11.io`
- `11cv` -> `cv.rj11.io`
- `11gg` -> `gg.rj11.io`
- ...

## Project registry
for now, this brain should live as a sibling of the projects it's managing, but should only focus on the registered projects and ignore the other siblings in order to not pollute context. ultimately the registered projects should have their paths in a .env file allowing to work in different computers just by updating the .env file (.env files should always be gitignored).

for now, the initial registered projects are:
- 11brain
- 11www
- 11blog
- 11ai
- 11gg
- 11pc
- 11fn
- 11crypto
- 11poker
