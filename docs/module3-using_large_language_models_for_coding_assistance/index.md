# Module 3 - Using Large Language Models (LLMs) for Coding Assistance

!!! warning "Work in progress"
    This page is currently under development.

This module introduces the participants to the use of LLMs as coding assistants, focusing on integrating AI tools into daily programming workflows to boost productivity, improve code, and accelerate learning. **Note that this is not a Module to learn about basic usage of LLMs, or other of its capabilities regarding data analysis, image and video generation, or scientific writing.**

Participants start with prompting and chat assistants such as GitHub Copilot, learn about the potential pitfalls, and use LLM chats to self-learn. In the second half, we move from assistants that answer questions to agentic AI: tools that can read a codebase, run commands, and make changes on their own. We cover how agents use tools, what the Model Context Protocol (MCP) is, and when multi-agent systems make sense. The module ends with two weeks of working on the participants' own projects.

## Learning outcomes

By the end of this module, participants will be able to:

- explain what LLMs are, roughly how they work, and where they help or fail in programming,
- tell the difference between AI-assisted and AI-generated code,
- write clear prompts that give the model the right context, constraints, and examples,
- use chat assistants and GitHub Copilot in VS Code to write, explain, debug, refactor, and test code,
- check AI-generated code critically (tests, reading the diff, verifying packages and APIs),
- handle research code and data responsibly when using AI tools (privacy, licensing, credentials),
- explain what an AI agent is and how it differs from a chat assistant,
- explain what MCP is and how it connects LLMs to tools and data,
- describe when a multi-agent setup is useful and when it is not,
- apply these tools to their own project while staying in control of the result.

## Weekly plan

- **Week 1:** Introduction and presentation, start of prompting and chat assistants
- **Weeks 2, 3, and 4:** Prompting and chat assistants (e.g. GitHub Copilot)
- **Weeks 5 and 6:** Agentic AI, MCP, and multi-agent systems
- **Weeks 7 and 8:** Continue working on participants' projects

## Sections

1. **Introduction and presentation** (45min - 1h) - Week 1
    - Quick welcoming to the module
    - What are LLMs and how they work
    - Examples of code assistants
    - Benefits and limitations of using AI in programming
    - AI-assisted vs. AI-generated code
2. **Prompting and chat assistants (e.g. GitHub Copilot)** - Weeks 1, 2, 3, and 4
    - Prompt engineering basics: context, constraints, examples, and iterating on answers
    - Using chat assistants for programming: explaining, debugging, and refactoring code
    - Using LLM chats to self-learn new libraries and concepts
    - GitHub Copilot in VS Code: inline suggestions, chat, and editing across files
    - Giving the assistant the right context (open files, selections, project instructions)
    - Generating tests and documentation with AI
    - Reviewing and verifying AI-generated code
    - Common pitfalls: hallucinated functions and packages, outdated APIs, overconfidence
    - Responsible use: data privacy, credentials, licensing, and institutional guidelines
3. **Agentic AI, MCP, and multi-agent systems** - Weeks 5 and 6
    - From chat assistants to agents: what changes when the AI can act
    - How agents work: tools, the agent loop, and working inside a repository
    - Agent modes in coding tools (e.g. Copilot agent mode, command-line coding agents)
    - Staying in control: permissions, reviewing changes, and not letting the agent commit for you
    - Model Context Protocol (MCP): what it is, MCP servers and clients
    - Connecting agents to tools and data through MCP (e.g. GitHub, file system, documentation)
    - Multi-agent systems: splitting work between agents, and when it is worth it
    - Risks: security, prompt injection, cost, and reproducibility
4. **Continue working on projects** - Weeks 7 and 8
    - Applying chat assistants and agents to the participants' own projects
    - Discussing questions and challenges with experts and peers

## Participants' projects

In weeks 7 and 8, participants work on their own projects uninterrupted,
in a room with experts and peers, where they can collaboratively address questions and challenges.
The goal is to try the tools from this module on real code and to share what worked and what did not.
