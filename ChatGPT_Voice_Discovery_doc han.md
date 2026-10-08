# ChatGPT Voice Discovery — Working Prototype

Implementation handoff for codebase / coding agent

## 1. Product intent

Build a focused Voice discovery enhancement inside a familiar ChatGPT mobile interaction model. This is not a redesign and not a separate Voice app.

**Reference prototype:** https://chatgptvoiceusage.lovable.app

The M3 PRD is the source of truth for product scope and behavior. The Lovable prototype is the visual and interaction reference.

**Lovable prototype URL:** https://chatgptvoiceusage.lovable.app

## 2. Critical requirement: real conversation

- The prototype must be genuinely interactive, not a scripted or prepopulated simulation.
- When a reviewer initiates Voice, the system must wait for the reviewer to actually speak.
- The reviewer's actual speech must be transcribed and displayed as the user message.
- The AI response must be generated dynamically from the actual user input and conversation history.
- The AI response should be spoken aloud.
- The reviewer must be able to continue the conversation naturally for multiple turns.
- Do not hard-code sample user messages, scripted assistant responses, or a fixed 3–4 turn conversation.
- The AI should respond to what the reviewer actually says. Do not force every response to end with a question.

## 3. Reviewer experience

### ChatGPT home — familiar

Use a familiar ChatGPT-style mobile layout: top bar, empty state, standard composer. On desktop, center the experience in a phone-width column.

### Voice discovery layer

Show the heading **"What are you trying to figure out?"** and three situation cards:

- **Presentation in 30 minutes?** — Practice your presentation through a natural conversation.
- **Interview coming up?** — Practice your answers through a natural conversation.
- **Stuck between two options?** — Talk it through and make your decision.

Hint: **"Speak naturally. Use the language that feels comfortable."**

### Voice conversation — inside the chat thread

Selecting a situation reveals the primary CTA **"Tap to Talk"** and secondary option **"Or type instead"**.

The selected situation becomes the conversation context/title. The screen may show a short opening invitation, but this is **NOT** a simulated conversation turn.

- Presentation: **"Tell me what you’re presenting and what you want to practice."**
- Interview: **"Tell me about the role you’re interviewing for."**
- Decision: **"Tell me what you’re trying to decide between."**

After that opening invitation, the conversation begins with the reviewer's real speech. Messages appear as normal ChatGPT-style bubbles. A single voice control communicates the current state: **Ready to talk / Listening / Processing / Speaking**, with an End action.

### Feedback

- After End: **"Did Voice help?"** — Yes / Somewhat / No
- Then: **"Would you use Voice for something similar again?"** — Definitely / Probably / Probably not

## 4. Context and conversation behavior

The selected situation should provide context to the AI, but should not constrain the reviewer to a scripted flow.

- **Presentation:** help the reviewer think through presentation content, structure, delivery, questions, or concerns based on what they say.
- **Interview:** respond to the actual role, experience, question, concern, or answer the reviewer provides.
- **Decision:** help the reviewer explore the options, criteria, trade-offs, and uncertainty they actually describe.
- Maintain conversation history across turns so responses are contextual.
- Keep responses concise enough for a natural voice back-and-forth, while still being thoughtful and useful.

## 5. Multilingual behavior

Support natural English, Hindi, Hinglish, and mixed-language interaction where the underlying speech and language services support it. Do not add a language-selection screen. The reviewer should be able to speak in the language mix that feels natural.

## 6. Functional architecture

The implementation should use a minimal architecture suitable for a portfolio prototype:

**Browser microphone → speech-to-text → Transcript + conversation history + selected situation → secure backend/server function → LLM for a contextual response → text-to-speech → Spoken response → reviewer; conversation continues**

Technology choices are open to the coding agent. Do not make the implementation dependent on Lovable-specific services unless there is a clear reason. API keys/secrets must remain server-side.

## 7. State to support

- Selected situation
- Current conversation
- Conversation messages
- Voice active/inactive
- Voice state: Ready / Listening / Processing / Speaking
- Feedback response

## 8. Explicitly out of scope

- Replacing typing with Voice
- Redesigning ChatGPT
- A separate Voice app or dashboard
- User profiles or persona databases
- Language databases or language-selection UI
- Analytics dashboards
- Authentication, payments, or production infrastructure unless technically required for the prototype
- Production-grade Voice infrastructure
- A scripted/demo conversation

## 9. Acceptance criteria

- The reviewer immediately recognizes the experience as ChatGPT-like.
- The three contextual discovery situations are visible.
- The primary discovery CTA is exactly: **Tap to Talk.**
- The reviewer can initiate Voice using their microphone.
- No fake or prepopulated conversation turns appear.
- The reviewer's actual speech becomes the user message.
- The AI responds dynamically to the actual content.
- The AI response is spoken aloud.
- The reviewer can continue for multiple turns.
- Conversation context is preserved across turns.
- The reviewer can end the conversation and provide the two-step feedback.
- Typing remains available through **'Or type instead'**.

## 10. Source of truth

Use the M3 PRD for product requirements, scope, selected opportunity, JTBD, solution logic, metrics, and non-goals. Use the Lovable prototype URL for visual/interaction reference. Do not treat intermediate wireframes as a pixel-perfect UI specification; preserve the product intent and familiar ChatGPT interaction model.
