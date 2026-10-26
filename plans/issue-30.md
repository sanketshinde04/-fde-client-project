## Goal
Build the core LLM conversational pipeline with the TripNest brand persona, multi-turn memory, and requirement gathering for holiday inquiries.

## Steps
1. Set up the LLM provider client with retry mechanisms, timeout recovery, and token limits.
2. Craft the TripNest system prompt defining tone, WhatsApp-friendly brevity, and inquiry scope.
3. Implement session state and memory management to track travel details (destination, dates, party size, budget).
4. Implement fallback handling and human escalation triggers for out-of-scope requests.
5. Connect the LLM pipeline to the WhatsApp webhook message handler.
6. Add unit and integration tests verifying multi-turn conversational flows and error recovery.

## What could go wrong
- LLM API latency or rate limits degrading WhatsApp response times.
- Context window overflow or conversation state lost between turns.
- Assistant deviating from brand persona or hallucinating unsupported travel services.

## Done when
- [ ] LLM pipeline processes incoming WhatsApp messages with TripNest brand voice.
- [ ] Multi-turn memory accurately captures holiday criteria across messages.
- [ ] Rate limits, timeouts, and out-of-scope inquiries are handled gracefully.
- [ ] Test suite verifies successful conversation tracking and fallback paths.