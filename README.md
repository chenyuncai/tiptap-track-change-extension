# TrackChangeExtension

A Track Change Extension for Tiptap. Like the revision in Microsoft Office Word.

## Demo

[Visit Demo](https://track-change.onrender.com/)

The demo is deployed on [render.com](https://www.render.com). You maybe need a VPN if you are in china

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
    dataOpUserId: '', // set the op userId
    dataOpUserNickname: '', // set the op user nickname
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
editor.commands.updateOpUserOption('id', 'nickname')

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

###### Enjoy it...

### publish
npm run build

npm publish --registry=https://registry.npmjs.org