# Markdown Editor

`yarn add @davidilie/markdown-editor`

## Info

This is an extended project on top of [https://github.com/nijat13/rich-markdown-editor](https://github.com/nijat13/rich-markdown-editor) which is extended on top of [https://github.com/outline/rich-markdown-editor](https://github.com/outline/rich-markdown-editor) and is in my opinion the perfect markdown editor for projects.

## What I changed

Most functionalities are the same, I just modified some margins and type errors so that it works well with my different projects.

## Usage

You can see the storybook [here](https://markdown-editor.davidapps.dev) or see a basic example below:

### Next.JS

```tsx
import dynamic from "next/dynamic";
import React, { useState, Suspense } from "react";

const Editor = dynamic(() => import("@davidilie/markdown-editor"), {
   ssr: false,
});

const Component: React.FC = () => {
   const [val, setVal] = useState("Hello World!");
   return (
      <Suspense fallback={<p>Loading...</p>}>
         <Editor
            defaultValue={val}
            onChange={(markdown) => setVal(markdown())}
         />
      </Suspense>
   );
};

export default Component;
```

### create-react-app

```tsx
import React, { useState } from "react";

import Editor from "@davidilie/markdown-editor";

const Component: React.FC = () => {
   const [val, setVal] = useState("Hello World!");
   return (
      <Editor defaultValue={val} onChange={(markdown) => setVal(markdown())} />
   );
};

export default Component;
```
