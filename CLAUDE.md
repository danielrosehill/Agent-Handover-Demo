# CLAUDE.md - Agent Handover Demo

## Project Overview

This repository implements a document-based pattern for handling task handover between AI agents working across different environments, platforms, or models. It provides a structured approach to maintaining context and task continuity when agents need to transfer work, particularly useful in multi-agent workflows.

## Purpose

The Agent Handover Demo addresses the challenge of coordinating AI agents across different environments (VMs, networks, cloud instances) where traditional shared memory systems may be impractical or unavailable. Instead of complex infrastructure, this pattern uses simple markdown documents as handover briefs to preserve context between agents.

## Core Components

### 1. Handover Generator Agent
A specialized agent responsible for creating comprehensive handover briefs when a task needs to be transferred. It documents:
- Completed work with verification steps
- Current system state and configurations
- Next steps with priorities and dependencies
- Important context and potential issues

### 2. Handover Receiver Agent
Processes incoming handover briefs and initializes target agents with the necessary context. It handles:
- Parsing and validating handover documentation
- Verifying environment state matches documentation
- Briefing the target agent with complete context
- Error handling for incomplete or unclear briefs

## Architecture

The pattern follows a clear flow:
1. Primary agent works until reaching a handover point
2. Handover Generator creates a structured markdown brief
3. Brief is transferred to target environment (SCP, Git, network share)
4. Handover Receiver processes the brief and initializes the target agent
5. Target agent continues work with full context

## Use Cases

- **Cross-VM Development**: Transferring work between development and production environments
- **Model Specialization**: Chaining different AI models for their specific strengths (coding → documentation → testing)
- **Network Boundary Crossing**: Moving tasks between internal networks and cloud environments
- **Multi-Environment Workflows**: Complex projects spanning multiple systems or platforms

## Key Advantages

- Works across any AI systems that can process markdown
- Model-agnostic (GPT, Claude, Llama, etc.)
- No complex networking or infrastructure required
- Human-readable and editable
- Version controllable with git
- Lightweight and simple to implement

## Repository Structure

- `system-prompts/`: System prompts for handover generator and receiver agents
- `templates/`: Standard template for handover briefs
- `example-handover.md`: Sample handover brief demonstrating the pattern

## Working with This Repository

When working on this project:
- The system prompts define the behavior of specialized handover agents
- The template provides a standardized structure for handover documentation
- The example demonstrates a realistic handover scenario

This is a pattern demonstration repository meant to be adapted and integrated into multi-agent workflows. The handover mechanism is designed to be simple, reliable, and maintainable while enabling sophisticated agent coordination.

## Author

**Daniel Rosehill**
Website: [danielrosehill.com](https://danielrosehill.com)
Email: github@danielrosehill.com

## License

MIT License - see LICENSE file for details
