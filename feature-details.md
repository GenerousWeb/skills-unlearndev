## Extract features from the features md file into its own feature spec md file

```plaintext
Extract the feature [feature] from features.md into its own markdown document, feature-[FEATURE_NAME].md.
Instructions:
- Preserve the original intent of the feature
- Pull in any relevant requirements, constraints, assumptions, dependencies, edge cases, and related notes from elsewhere in features.md or spec.md
- Exclude unrelated features or implementation details that do not directly support this feature
- Rewrite the extracted feature into a clean, structured spec that is easier to plan in detail
Output format:
# [Feature Name]
## Summary
A short plain-English summary of the feature and its purpose.
## Goals
Clear outcomes this feature should achieve.
## Requirements
Functional requirements only for this feature.
Do not start designing the solution yet
Do not propose any low level technical decisions
```

## Remove any section in the generated spec if not required

## Add technical details to the feature file

```plaintext
Add a technical section and include:
- [Technical item 1]
- [Technical item 2]

-- test the feature
How might you build this based on this feature document only? Give me the technical decisions you'd make in a simple list.

-- question how the technical design is implemented
How are you going to implement [feature/mechanism]?
```

## Choose the out of scope things added to your feature
```plaintext
-- scope creep check
What helpful additions might you sprinkle in if building this that we don’t want?

-- specific section with features to be excluded
Add these to the constraints section and/or update applicable sections of the feature plan:
- *[Feature you don't want]
- *[Package you don't want to include]
- *Etc.
```

## Breaking the features so that it can be reviewed
```plaintext
Add a new section, “Implementation Steps” and break up this feature into smaller, ordered implementation steps.
These steps should be large enough to add a significant and usable feature, but small enough that we can comfortably review it.
```

## Preview how AI will build 
```plaintext
Generate a Claude Code prompt for Implementation Step [step number],
taking into account the context from this feature file, our features.md file and spec.md file.
```

## Follow TDD to build test first before the feature is built. Review the use cases covered in the test plan

```plaintext
- Add a simple bulleted list of tests under a Tests heading for each implementation step.
- Generate a Claude Code prompt to write tests for Implementation Step [step number], using [testing framework].

```
