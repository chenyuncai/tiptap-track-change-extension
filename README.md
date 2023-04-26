# TrackChangeExtension

A Track Change Extension for Tiptap. Like the revision in Microsoft Office Word.

## Installation

just copy the ts file to your project or install from npm. it depends on the @tiptap/pm package to use ProseMirror api.

## Usage in Vue3

```javascript

import TrackChangeExtension from 'index.ts'
or
import TrackChangeExtension from 'track-change-extension'

const myTrackChangeEnabled = ref(false)

extensions: [
  ...OtherTiptapExtensions,
  TrackChangeExtension.configure({
    enabled: true,
    onStatusChange (status: boolean) {
      myTrackChangeEnabled = status
    }
  }),
]

// commands

// accept one change near by the cursor or an active selection range
editor.commands.acceptChange()
editor.commands.acceptAllChange()
editor.commands.rejectChange()
editor.commands.rejectAllChange()

```

## style

```css
insertion {
  color: green;
  text-decoration: underline;
}
deletion {
  color: red;
  text-decoration: line-through;
}
```

### next to do:

1. save author, date info
1. export the static util about the operation command when someone need to export a accepted/rejected document without a real operation
1. deploy a online demo on vercel

###### Enjoy it...

### publish
npm run build

npm publish --registry=https://registry.npmjs.org