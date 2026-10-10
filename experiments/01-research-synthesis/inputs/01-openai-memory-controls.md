# Source Packet 01 — OpenAI: Memory controls and freshness

## Sources

1. OpenAI Help Center, **“Memory in ChatGPT”**  
   https://help.openai.com/en/articles/8590148-memory-in-chatgpt  
   Checked for this experiment: October 10, 2026.

2. OpenAI, **“Dreaming: Better memory for a more helpful ChatGPT”**  
   https://openai.com/index/chatgpt-memory-dreaming/  
   Published June 4, 2026.

## Documented behavior

OpenAI describes ChatGPT Memory as a personalization system that can draw on multiple kinds of context. Depending on plan, region, platform, and workspace settings, those sources can include past chats, saved memories, custom instructions, Library files, and connected apps.

OpenAI says Memory does not retain every detail from every conversation. The system decides which available information is relevant to a response, and remembered information can change as the user’s context changes.

The current help documentation distinguishes a **memory summary** from the full set of information that Memory may use. The summary is described as a high-level view and may omit details or sources.

OpenAI also distinguishes **saved memories** from **chat history**. Saved memories are stored separately from chat history. Deleting the original chat does not automatically delete a saved memory that was created from it.

Information derived from chat history can change as ChatGPT updates what it considers useful to remember. Turning off Reference chat history schedules that derived information for deletion, while the original chats remain unless the user deletes them.

Users can tell ChatGPT that remembered information is incorrect or outdated. Where supported, they can also edit memory information directly.

“Don’t mention this again” changes future personalization behavior, but OpenAI says it does **not** delete the original source containing that information.

OpenAI’s June 2026 “Dreaming” announcement says the newer memory system was designed to address **staleness, correctness, and scalability** over long time horizons. The post gives the example of a future-trip memory eventually needing to reflect that the trip already happened rather than remaining permanently framed as upcoming.

OpenAI describes improved memory as continually updating a broader summary of relevant context, rather than behaving only as a static list of individual saved-memory items.

## What these sources establish

- Remembered information may come from more than one source.
- A visible memory summary is not necessarily a complete inventory of all usable context.
- A saved memory and the chat that produced it can have separate lifecycles.
- Information derived from chat history can be revised over time.
- OpenAI explicitly treats stale memory as a product problem.
- Suppressing future mentions of information is different from deleting the source.

## What these sources do NOT establish

These documents do not publish the full retrieval algorithm used for every response.

They do not show that ChatGPT always chooses the correct fact when old and new information conflict.

They do not establish that every account has identical memory behavior or controls.

The “Dreaming” article describes OpenAI’s system and product goals; it is not an independent benchmark proving that all stale-memory problems are solved.
