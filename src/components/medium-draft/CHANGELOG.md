### 0.6.0-beta

- A revamped architecture develop custom editor in a better way using plugin-like system.
- Updated draft-convert's version (@mckelvey)

### 0.5.5

- A new prop `toolbarConfig` has been introduced. So instead of passing whole configuration into `blockButtons` and `inlineButtons`, you can just pass, `toolbarConfig` with value
```json
{block: ["header-three", "blockquote", ...], inline: ["BOLD", "ITALIC", "UNDERLINE", "hyperlink"]}
```
Note that the string values of the array must already be present in `BLOCK_BUTTON` and `INLINE_BUTTONS` in `medium-draft` (@roy-gbiv)

- Extra props can be passed to the `component` of each item in `sideButtons` inside the `prop` key. Earlier, only `title` and `component` were accepted. Now a 3rd key `prop` can also be passed whose keys can be accessed inside the `component` through `this.props` (@ jaspersorrio)
- Fixed paste handling when cursor is inside image block caption. Earlier, the `src` of image became `undefined`. Now, plaintext will be pasted if the cursor is inside Image block. Otherwise, Draft's pasting will take over.
- Now a string of text can also be passed to `createEditorState` as the first argument to create initial `editorState` pre-filled with the text.

### 0.5.3

- Added `medium-draft-importer` to convert html exported using `medium-draft-exporter` to draft's json format (@Yukaii)
- Fixed arrow navigation around image blocks
- Allow inline styles to be applied to heading blocks
- Remove hardcoded fonts from css files

### 0.5.2

- Now, the toolbar buttons also accept a react component instead of just a string as label.
  This can be used to customize the icon of the toolbar button. For ex - in the
  demo, blockquote and link buttons are svg components which previously were
  just string labels.
- Added a link info tooltip that shows up when cursor is inside a word with hyperlink.
- The tooltip has option to edit that link or unlink.
- Added medium's shortcut to add a link to text selection
    - <kbd>CTRL/CMD</kbd> + <kbd>K</kbd> -> Add link
- <kbd>CTRL/CMD</kbd> + <kbd>SHIFT</kbd> + <kbd>K</kbd> -> Remove link if cursor is inside a word with link.

### 0.5.1

- Optimized build process by minifying css and removing prop-types from the build files.
- Migrated to React 15.5 (@baldwmic) with external `prop-types` dependency.

### 0.5.0

- Moved away from the deprecated `Entity` usage of `draft-js` and updated to draft-js 0.10.1 (@valthon)
- Fix for unintentional page navigation when adding links (@J00nz)
- Fix where first click on side (+) button made it dissappear (@J00nz)
- Accept only image files through file selector (@anthonyjgrove)

### 0.4.1

- Added medium-draft-exporter to convert the draft-js JSON data to HTML.
- Moved away from string refs to recommended refs in React.

### 0.4.0

- Updated to use draft-js v0.9.1
- Namespaced all classes to start with `md-`
- Add relevant class to editor container based on whether editing is enabled or disabled
