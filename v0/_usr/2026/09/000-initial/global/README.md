# Global rules
here are the main fundamental guidelines, guardrails, and practices that i want to enforce on the global brain framework

## _usr
let's use the keyword `_usr` when refering to the human operator. when you find any folder named `_usr` assume it's reserved for the human operator to draft temporary files inside and ignore it's contents in order to not pollute your context unless specifically referred to it to read instructions.

we want to include this rule in our AGENTS.md reference for the brain framework.

## Priority rules
- lower the value, higher the priority
- 0 highest priority
- 999 extremely low priority

priority will be the main indicator of the order of the tasks to execute, it's value can be initially set as a rough estimate and can change depending on further analysis, the value can be justified through many lenses such as criticality, urgency, difficulty, but the main determining factors should be efficiency, impact, and compounding effect. concrete and real example:
- i want to propagate my blog boilerplate across a few different surfaces with high priority
- but i also want to improve my blog markdown components to support charts and other data visualisations with lower priority
you should be able to understand that it's much more efficient to do the improvements before the propagation, rather than propagate the blog and then propagate the improvements. you should alert the `_usr` when you find such cases, and prioritize things accordingly when planning by yourself.

## Folder structure
These have been the optimal and clean folder structures i found to work best, but they are open for improvements, however you should default to these when the situation applies.

### Project folder structure
we want to avoid cluttering the project root (or clutter any layer), in general we want to reserve the project root only for items that must live on that level. things like the top level README.md, AGENTS.md, or CHANGELOG.md, top level package.json with npm publishing configs or equivalent, AI agent configs like `.claude` or `.agents`. also global technical configs like docker files, `.vscode`, `.github`, `.husky`, `.git`, `.env`, `.gitignore`, etc.

the next level below we are gonna have a version layer `~/{version}/**`, this is where we are gonna scope everything about this specific version of the project, starting with v0:

```
{project}/
├── v0/
│   ├── docs/
│   ├── www/
│   ├── AGENTS.md
│   ├── README.md
│   └── ...
├── v1/
│   ├── docs/
│   ├── www/
│   ├── AGENTS.md
│   ├── README.md
│   └── ...
├── v2/
│   ├── docs/
│   ├── www/
│   ├── AGENTS.md
│   ├── README.md
│   └── ...
├── AGENTS.md
├── README.md
└── ...
```

as you can see from this structure each version has their own README.md, AGENTS.md, docs, and web app (www). other common modules under the version layer are `plugins` for ai skills and plugins, `scripts` for utility scripts, or other domain specific directories.

### Web app (www) folder structure
under the version layer will often exist a `www` folder, we reserve this keyword for the web application layer of that version of the project. we will mainly work with next.js typescript applications using app router. on the application root we want to maintain the same principle of avoinding clutter, so we reserve it for items that must exist there like the app package.json, README.md, AGENTS.md, config files, public folder, and framework / third party library specific items like shadcn components, tailwind configs, third party providers, etc. 

```
www/
├── app/
│   ├── components/ <- our global components
│   ├── scripts/ <- our global scripts
│   └── ...
├── AGENTS.md
├── README.md
├── package.json
├── lib/ <- shadcn utility scripts
├── components/
│   └── ui <- shad cn components
├── package.json
└── ...
```

inside the next.js app router `app/` folder is where we want to scope our work using the React Modules principles inside the app router. meaning if our application has multiple modules, each module has it's own scoped components and scripts etc (`app/{module}/components`), while keeping global app components in the `app/components`. example:

```
app/
├── components/ <- our global components
│   ├── header.tsx
│   ├── footer.tsx
│   └── ...
├── scripts/ <- our global scripts
│   └── ...
├── moduleA/
│   ├── components/  <- moduleA components
│   ├── scripts/  <- moduleA scripts
│   └── ...
├── moduleB/
│   ├── components/  <- moduleB components
│   ├── scripts/  <- moduleB scripts
│   └── ...
└── ...
```

we want to keep the scopes thight as much as possible without having things leak out of a module or version unnecessarily, always assume the intention is to scope down as much as possible unless explicitly told otherwise.

going beyond the module, when creating technical files of any kind tsx components, ts scripts, md docs, we want to atomize and make things as unitary as possible to make it easier to tweak observe test and maintain.
a whole page should never be written on a single tsx file, it should be broken down into as many subcomponents as possible, same as big functions scripts and hooks. prefer using kebab-case for filenames when applicable.

when working inside the next.js app router is common for me to run into layout conflicts, for this i like to use the `(module)` namespace, usually starting to work on a `app/(main)/layout.tsx` level where i can easily scope out of `(main)` to a the root layout if needed, giving me a lot more flexibility when needed even in more nested levels. example:

```
app/
├── layout.tsx <- root layout
├── (main)/
│   ├── layout.tsx <- main layout
│   └── ...
└── ...
```

using this initial structure keeps the root layout clean with just the necessary load, leaving the main layout to be the first custom point. one important note to structure the web app to be as much server side rendered as possible, with special attention when implementing providers in the lowest layout possible and client components the best way possible.

### Archive folder strcture
when creating a folder structure with the purpose of archiving at any point, default to a `~/{year}/{month}/**` format with sequential child folder inside each month if no better solution is found or instructed. example: `~/2026/09/000-initial-planning`.
