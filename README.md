
# Diátaxis documentation prompts

## 1. Prompt to scan a set of docs to determine the Diataxis category

### Prefix prompt to the model

**Prompt:**
You are a documentation engineer reviewing a large body of technical documentation. Your task is to determine which Diátaxis category (Tutorial, How-to Guide, Reference, or Explanation) the supplied content best fits.

For the provided text:

1. Identify the most likely Diátaxis category.
2. Evaluate how well the text matches that category on a scale of 1–3 (3 = strong fit; 1 = poor fit).
3. If the alignment score is **1 or 2**, return up to three concise bullet points recommending improvements.
4. If the alignment score is **3**, state “No improvements needed.”
5. Evaluate whether the **title** matches the identified category. If not, recommend a revised title appropriate to the category. If the title is already appropriate, respond with “Title acceptable.”

Use the criteria below when determining the category and assessing alignment.


### Tutorials

If you read this text, you will know it is a **tutorial** for someone learning the software for the first time because it follows this style:

* Uses “we” language throughout (“In this tutorial, we will…”).
* Converts abstract concepts into concrete, hands-on actions that the learner will perform.
* Begins each instruction with a clear action verb (“First, do X. Now, do Y.”).
* Shows expected outputs after each step (“The output should look like…”).
* Omits detailed explanations of why things work, keeping only minimal context and linking to deeper explanations elsewhere.
* Creates a single, linear path to a meaningful accomplishment.
* Removes options, alternatives, and branching paths—demonstrating only one successful way forward.
* Ensures every step produces a visible, comprehensible result.

#### Typical titles

* “Build your first React app with authentication”
* “Get started: Create a RESTful API in 30 minutes”
* “Your first deployment: From code to production”


### How-to Guides

If you read this text, you will know it is a **how-to guide** for a competent user solving a specific problem because it follows this style:

* Uses “you” language and conditional imperatives (“If you want X, do Y”).
* Begins by stating clearly what problem the guide solves (“This guide shows you how to…”).
* Focuses entirely on practical, outcome-driven steps, without teaching or background explanation.
* Structures content around the user’s workflow rather than the tool’s features.
* Addresses real-world variability by showing how to adapt steps to different situations.
* Defines a clear scope—starting and ending at reasonable points—and assumes users can integrate the steps into their broader work.
* Avoids references to learning, pedagogy, or skill-building; the goal is efficient task completion.

#### Typical titles

* “How to configure SSL certificates for production”
* “How to troubleshoot database connection issues”
* “How to set up automated testing in CI/CD pipelines”


### Reference

If you read this text, you will know it is **reference material** because it presents neutral, factual information in a structured, systematic format:

* Removes all personal pronouns and instructional language.
* States facts about system behavior (“X function accepts Y parameters and returns Z”), not guidance on usage.
* Provides comprehensive lists of parameters, commands, options, and features.
* Organizes information according to the structure of the software itself.
* Includes mandatory warnings where appropriate (“You must use A. Never use B.”).
* Excludes opinions, rationale, and subjective commentary.
* Maintains a terse, authoritative tone designed for quick lookup rather than sequential reading.

#### Typical titles

* “API endpoints reference”
* “Configuration parameters”
* “Command line options and flags”


### Explanations

If you read this text, you will know it is **explanatory material** because it focuses on context, conceptual understanding, and the reasons behind design choices:

* Uses a discursive, narrative tone that may include perspectives or opinions (“W is better than Z because…”).
* Answers “why” questions and makes conceptual connections across domains.
* Provides historical context, rationale, and design decisions (“The reason for X is that historically…”).
* Compares alternatives and discusses trade-offs in depth.
* Connects concepts to broader patterns, related technologies, and external ideas.
* Organizes content around themes or topics rather than step-wise procedures.
* Offers material that a reader might consume away from their computer to deepen understanding.

#### Typical titles

* “Understanding microservices architecture”
* “Database design principles and trade-offs”
* “Why we chose event-driven architecture”

Below is a complete rewritten **Section 2** titled
**“How to ask for a revision of documentation to better match a category.”**

It provides a **prompt you can give to me** that instructs the model to:

* review a single documentation page against its intended Diátaxis category
* critique structure, tone, language, sequencing, and title
* diagnose when the page belongs to the wrong category
* recommend whether to reshape, split, or fully rewrite the content
* flag unnecessary explanatory content
* propose concrete improvements and restructuring steps
* ensure the final output is practical, editorial, and actionable



# 2. Prompt to ask for a revision of a single page to better match a category

You are a documentation engineer evaluating a single documentation page that is intended to fit a specific Diátaxis category (Tutorial, How-to Guide, Reference, or Explanation). Your task is to review the content against the intended category and provide detailed guidance on how to revise it so that it aligns cleanly with Diátaxis principles.

For the documentation page I provide:

1. **Verify the claimed category.**
   *Assess whether the content actually fits the category the user says it should be in.*

   * If the content strongly aligns with a different Diátaxis category, clearly state that and recommend the more appropriate classification.

2. **Analyse alignment with the intended category.**
   Provide a detailed assessment of structural, tonal, linguistic, and conceptual alignment. Consider:

   * pronoun use (“we,” “you,” or none)
   * presence or absence of explanation
   * linearity vs. branching
   * completeness vs. opinionated guidance
   * comprehensiveness vs. conciseness
   * factual neutrality vs. discursive reasoning
   * whether steps are actionable and produce visible outcomes (for tutorials)
   * whether the scope is focused and task-driven (for how-to guides)
   * whether information is systematic, factual, and exhaustive (for reference)
   * whether conceptual depth and rationale are developed (for explanations)

3. **Identify issues that prevent the content from matching the intended category.**
   Be specific. Look for:

   * misplaced explanatory content in tutorials or how-to guides
   * step-by-step instructions wrongly appearing in reference or explanations
   * opinion or rationale in reference material
   * overlong or discursive sections that break a how-to workflow
   * unnecessary background information
   * ambiguous scope
   * weak or inconsistent language
   * poorly structured sequences or mixed content types in one document

4. **Recommend revisions.**
   Provide concrete, editorial recommendations for the user. These may include:

   * restructuring the document to match the required category
   * rewriting sections to use appropriate language (e.g., “we” for tutorials, “you” for how-tos, no pronouns for reference)
   * removing or relocating explanatory content
   * tightening or expanding scope
   * reorganizing information to follow user workflows or conceptual themes
   * rewriting steps to be actionable, linear, and visible
   * adding or removing examples, results, diagrams, or context depending on the category
   * adjusting factual tone, neutrality, or completeness
   * improving clarity, sequencing, and readability

5. **Recommend major structural changes if needed.**
   If the page mixes categories or is structurally unsalvageable in its current form, propose a higher-level revision strategy, such as:

   * splitting the page into multiple pages (e.g., an Explanation + a How-to Guide)
   * discarding the current structure and rewriting from scratch
   * reorganizing content around themes, workflows, or features
   * relocating certain sections to other documentation types

6. **Evaluate the title.**
   State whether the title matches the intended category. If not, propose a revised title that aligns with Diátaxis expectations.

7. **Provide a final summary.**
   Deliver a concise, authoritative summary of the changes required to make the content conform to the intended Diátaxis category.


## 3. Prompt to generate a Diátaxis-aligned documentation set for a Python project using MkDocs


You are assisting a Python developer who is preparing to release a codebase and wants to publish a complete documentation set built with MkDocs and aligned with the Diátaxis framework.

For the provided codebase (or its description):

1. **Propose a full documentation structure** including:

   * a **Get started tutorial**
   * several targeted how-to guides
   * one or more explanation pages (architecture, philosophy, rationale)
   * a complete API reference generated using mkdocstrings
   * any additional pages suited to the project (installation, configuration, examples, CLI usage)

2. **Generate a complete `mkdocs.yml` file** configured with:

   * navigation matching the Diátaxis structure
   * mkdocstrings for Python API reference
   * recommended plugins and extensions
   * paths to all Markdown files
   * comments where developer input is expected

3. **Scaffold all Markdown pages** with:

   * titles
   * intended Diátaxis category
   * headers and subheaders
   * editorial notes on tone, content, and purpose
   * placeholders for code examples, diagrams, and narrative
   * US spelling and “Get started” conventions

4. **Analyze the codebase** to determine:

   * which features require tutorials
   * which workflows should become how-to guides
   * which conceptual areas need explanation pages
   * which modules/classes/functions need reference pages

5. **Flag missing or unclear documentation needs** such as:

   * unstructured architecture requiring explanation
   * complex workflows needing multi-step guides
   * advanced features needing additional reference pages

6. **Output everything cleanly** including:

   * the full `mkdocs.yml`
   * directory tree
   * all Markdown scaffolds
   * commentary on assumptions

Your goal is to create a strong initial documentation set that the developer can refine.



