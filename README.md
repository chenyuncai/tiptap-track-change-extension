# TrackChangeExtension

A Track Change extension for Tiptap.


## Installation

just copy the ts file to your project. it depends on the @tiptap/pm package to use ProseMirror api.

## Usage

```javascript


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

editor.commands.acceptChange()


```

## style

```css
insertion {
  color: green;
}
deletion {
  color: red;
}
```

###### Enjoy it...