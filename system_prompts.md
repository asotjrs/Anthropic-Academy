Q: What is a system prompt?
A: A string that defines how Claude should behave (tone, role, style).

Q: Why are system prompts important?
A: They make responses consistent, task-specific, and aligned with a role.

Q: What happens without a system prompt?
A: Claude gives generic answers.

Q: What happens with a system prompt?
A: Claude adapts behavior (e.g., tutor, assistant, expert).

Behavior Control

Q: Give an example use case of a system prompt.
A: A math tutor that guides step-by-step instead of giving answers.

Q: What should a good math tutor system prompt enforce?
A:

Give hints first
Guide step-by-step
Avoid direct answers

Q: What should it prevent?
A:

Immediate full solutions
Lazy/help-avoiding responses
API Usage

Q: How do you pass a system prompt in the API?
A: Using the system parameter in client.messages.create().

Q: Example structure?
A:

client.messages.create(
    model=model,
    messages=messages,
    max_tokens=1000,
    system=system_prompt
)
Design Patterns

Q: Why make system prompts a function parameter?
A: To make the chat function reusable and flexible.

Q: Example function signature?
A:

def chat(messages, system=None):

Q: Why not always pass system=None?
A: The API does not accept system=None.

Q: How do you handle that?
A: Conditionally add it:

if system:
    params["system"] = system
Advanced Understanding (important for exam)

Q: Why use **params when calling the API?
A: To dynamically include only valid arguments (like system when present).

Q: What problem does this solve?
A: Avoids passing invalid fields (e.g., system=None).

Q: What does **params do?
A: Unpacks a dictionary into keyword arguments.

Behavioral Insight

Q: How do system prompts influence model reasoning style?
A: They shift the model from answering → guiding (or any defined role).

Q: Do system prompts guarantee behavior?
A: No, but they strongly steer it.

Key Takeaway (high-value exam answer)

Q: One-sentence summary of system prompts?
A:
System prompts define the role and behavior of the model, enabling controlled, consistent, and task-specific responses.
