# Screenshots

## stream-start.png
Shows the initial state of the streaming markdown parser with the STREAM button visible before any markdown content has been streamed in.

## rendered-output.png
Shows the fully rendered markdown output with:
- Code blocks styled with dark background (e.g., bash commands)
- Inline code styled with light gray background (e.g., `vscode`, `milvus`, `schema`)
- Proper formatting for headings, bold text, italics, and numbered lists
- All content streamed in and properly parsed

## Implementation Details

The streaming markdown parser handles:
1. **Optimistic Parsing**: Code styling is applied immediately when delimiters are detected
2. **Token Splitting**: Correctly processes backticks that may be split across multiple tokens
3. **State Management**: Tracks whether parser is inside inline code or code blocks
4. **DOM Preservation**: Adds elements incrementally without replacing the entire DOM, allowing text selection
5. **Visual Differentiation**: 
   - Code blocks: Dark background (#1e1e1e) with light text (#d4d4d4)
   - Inline code: Light gray background (#f0f0f0) with padding
