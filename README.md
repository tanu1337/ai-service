# ai-service

## Install

```sh
npx jsr add @tanu1337/ai-service
# or
pnpm dlx jsr add @tanu1337/ai-service
# or
yarn dlx jsr add @tanu1337/ai-service
# or
deno add jsr:@tanu1337/ai-service
```

## Usage example

```javascript
import { initChat } from "@tanu1337/ai-service";

// Initialize, optional models are gpt-4o-mini, claude-3-haiku, llama, mixtral, o3-mini
const chat = await initChat("o3-mini");

// Fetch the full reply in one go
let message = await chat.fetchFull("Hello");
console.log(message);

// Redo
chat.redo();
message = await chat.fetchFull("Hello");
console.log(message);

// Fetch the streamed reply
const stream = chat.fetchStream("Hello");
for await (let data of stream) {
  console.log(data);
}
```
