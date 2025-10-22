# JS rules

- Use functional and declarative programming patterns; avoid classes.

## Rule: Prefer Uint8Array over Buffer

- Use **Uint8Array** as the primary binary data type across environments (Node.js and browsers).
- Treat Node.js Buffer as a subclass of Uint8Array; accept Buffer inputs but do not rely on Buffer-specific methods.
- **Do not** use Buffer-specific APIs (e.g., Buffer#slice, Buffer#readInt32BE, Buffer#write*).
- For slicing:
  - Use Uint8Array#slice() for a copy.
  - Use Uint8Array#subarray() (or Buffer#subarray()) for a zero-copy view.
- For structured reads/writes, use DataView (get*/set*, choose endianness).
- For text encoding/decoding, use TextEncoder/TextDecoder (UTF-8).
- For Base64/Hex:
  - Prefer utility functions or a cross-platform library (e.g., uint8array-extras).
  - Avoid Buffer.toString('base64' | 'hex') in shared code.
- If absolutely required to convert:
  - Uint8Array → Buffer: Buffer.from(uint8Array) or Buffer.from(uint8Array.buffer, byteOffset, byteLength).
- Linting enforcement:
  - Disallow global Buffer and imports from 'buffer'/'node:buffer' via ESLint.
  - In TypeScript, ban the Buffer type and suggest Uint8Array.

ref: [Goodbye, Node.js Buffer - by Sindre Sorhus](https://sindresorhus.com/blog/goodbye-nodejs-buffer)
