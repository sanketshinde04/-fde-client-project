# Work Plan for Issue #23: Implement LLM Assistant Pipeline and Session Management

## Goal
Build the TripNest LLM conversation engine and session management to support multi-turn dialogues over WhatsApp.

## Steps
1. Define the TripNest system prompt with travel persona, tone of voice, and enquiry qualification guardrails.
2. Implement session storage keyed by user WhatsApp number with TTL to track multi-turn conversation history.
3. Build the core LLM orchestration pipeline to process incoming user messages and generate context-aware replies.
4. Add parameter extraction logic to capture key travel requirements (destination, dates, budget, party size).
5. Implement error handling, timeout fallbacks, and graceful degradation for LLM service disruptions.
6. Write unit and integration tests verifying session management, parameter extraction, and multi-turn flows.

## What could go wrong
- Rate limits or high latency from LLM provider could cause delayed WhatsApp responses.
- Session memory leaks or improper TTL configuration could result in stale conversation state.
- Prompt ambiguities could lead to hallucinations or out-of-scope travel recommendations.

## Done when
- Multi-turn WhatsApp conversations maintain context across sequential messages keyed by phone number.
- System prompt properly guides the assistant in qualifying customer travel enquiries.
- Session expiration and reset mechanisms operate reliably.
- Unit and integration tests for state transitions and error fallbacks pass.