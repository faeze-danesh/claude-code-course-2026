# /trace

## Description
This skill traces how a tool call flows through the devlens system.

It explains step by step how a request moves from the user to Claude and then to the tools in the codebase.

---

## When to use
Use this skill when the user asks:
- how a tool works
- where a function is defined
- how a request flows in the system

---

## Steps

1. Identify the tool name (e.g. read_file, write_file)
2. Find the tool definition in tools.js
3. Trace how index.js receives the request
4. Follow the agent loop in api.js
5. Show how Claude decides to call the tool
6. Show final output returned to user

---

## Output format

Tool:
<tool name>

Definition:
<file + function>

Flow:
1.
2.
3.
4.

Result:
<final output explanation>

---

## Example

Input:
/trace read_file

Output:

Tool: read_file

Definition:
Defined in tools.js → readFileTool()

Flow:
1. User sends request in UI
2. index.js receives /chat request
3. api.js sends messages to Claude
4. Claude requests read_file tool
5. tools.js executes file read
6. Response returned to Claude
7. Claude returns final answer

Result:
The file content is read and shown to user.