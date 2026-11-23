---
name: grill-requirement
description: Progressive requirement discovery Skill that refines intent into sufficient engineering clarity for OAEM depth selection.
---

# Grill Requirement Skill

## Purpose

Transform incomplete or vague engineering intent progressively into sufficient clarity to select the minimum necessary OAEM methodology depth.

## Core Behavior

- Iterative questioning loop:  
  QUESTION → ANSWER → UPDATE UNDERSTANDING → REMOVE IRRELEVANT QUESTIONS → DISCOVER NEW UNCERTAINTIES → DECIDE IF ANOTHER QUESTION CAN CHANGE THE ENGINEERING DECISION

- Maintain evolving state concepts:  
  - KNOWN  
  - UNKNOWN  
  - ASSUMPTIONS  
  - DECISIONS  
  - CONSTRAINTS  
  - RISKS  
  - NON_GOALS  
  - OPEN_QUESTIONS

## Human Interaction

- Primarily ask humans only about:  
  - intent  
  - preferences  
  - authority boundaries  
  - business/product decisions  
  - genuinely unavailable information

- Automatically discover what can be derived from the project source/configuration to reduce unnecessary questions.

## Stopping Condition

- Stop the questioning loop once sufficient clarity for the selected OAEM depth exists.

- Do NOT interrogate for the sake of interrogation.

## OAEM Method Compliance

- Preserve **VERTICAL BY DEFAULT** principle in information gathering.

- Ensure model- and harness-independence.

## Validation Scenarios

- Demonstrate dynamic question pruning.

- Validation that a single answer may change the next question.

- Confirm project facts are discovered before querying humans.

- Prove early stop when sufficient information is acquired.

- Test high-risk ambiguous cases prompt deeper questioning.

- Ensure trivial, clear requests do not trigger unnecessary questions.
