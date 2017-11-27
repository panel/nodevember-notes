# Fantastic Components and How to Find (Build) Them
[slides](https://github.com/jogjayr/nodevember-components-talk)

## What is a component library?
- Set of standardized, reusable UI Components
- Consistent look and feel
- Often used in conjunction with a FE framework
- Generally has the ability to be themed or customized


## What is a component?
- package of markup and styles
- programmatic interface to set values

## Reasons to Build Your Own
- Custom functionality not found elsewhere
- Existing component library not maintained or of high enough quality

## If you build a component library ...
1. Component Distribution
1. Using Components
1. Language
1. Documentation
1. Development Process

### Component Distribution

#### Dependency Management
Distribute Components as npm packages. Each component is published as its own module and published individually.

##### Artifactory
- you can decorate artifacts with the jenkins run that created it.

##### Pros
1. not much differetn from 3rd party libraries
1. possible for different teams/projects to use different versions
1. easy to test and build each component separately

##### Cons
1. You must manage dependencies
1. Need to maintain backwards compatibility and/or backport fixes to older versions

#### Monorepo
- All projects are in one repo
- External libs are handled by package managers

##### Pros
1. No versioning -- everyon on latest
1. East to promote component from project to lib
1. Component discovery easier
1. Compatibility issues are discovered sooner

##### Cons
1. More complicated build Process
1. Harder to open source components

### Component Usage
**Use webpack to import exactly what you need**

### Language
Recommends using type-checking

### Documentation

#### Styleguides
- Every component has a demo dir - a self contained project showing off
- Demos are deployed as part of Styleguide
- Check out 3rd party styleguid generators

### Process

#### Dedicated Team

##### Pros
1. Component API more uniform
1. Docs and samples are better maintained

##### Cons
1. Smaller orgs can't dedicate that many engineers
1. Less business context

#### Collective Ownership

##### Pros
1. Better business context

##### Cons
1. Everyone needs to understand API philosophy
1. Meeds rigorous code reviews
1. Communicating new components is more challenging
