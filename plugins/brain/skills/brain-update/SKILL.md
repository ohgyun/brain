# Brain Update: Log-based Rules/Values Update

Analyze logs to discover repeated patterns and elevate them to Project rules and Role values.

## Execution Steps

1. **Determine Log Scope**
   - Check last modification date of rules.md and values.md
   - Default: analyze only logs after last modification
   - User choice: "Since last change" (default) vs "Re-analyze all"

2. **Log Analysis and Pattern Identification**
   - Read logs from `~/.brain/logs/{project}/`
   - Extract from "What We Discovered This Session" section:
     - Repeated principles
     - New insights
     - Candidates for values/rules
   - Analyze repetition frequency (prioritize 2+ occurrences)

3. **Detect Similar Items**
   - Read existing rules/values files
   - Compare new candidates with existing items
   - When similar items found, offer merge options:
     - Keep both items
     - Add/extend to existing item
     - Ignore new candidate
     - Modify existing item

4. **Present and Select Elevation Candidates**
   - Summarize analysis (include repetition count, source logs)
   - User selects items to elevate

5. **Update Files**
   - Reflect selected items in rules.md, values.md
   - Do not add comments/metadata

## Important Principles

- **User confirmation required**: Never auto-modify files
- **Conservative merge**: Detect only obvious duplicates; user decides on similarities
- **Prioritize repetition**: Present patterns repeated 2+ times first
