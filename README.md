# Chess Board (React Drag & Drop)

| In this React project, I explore the drag-and-drop capabilities of <a href="http://react-dnd.github.io/react-dnd">React DnD</a> while using Flexbox to build a simplified chess board containing a single set of pieces. |
|:-|

### Identify components and consider props.

| Components | Description | Props |
|:-|:-|:-|
| **`Knight`** | A single knight piece. | Probably needs no props. There's no need for it to be aware of its own position since it'll be placed into `Square` as a child. |
| **`Square`** | A single square on the board. | Probably just **`color`** (alternating in white and black), as it is the only value needed for rendering. It's not necessary to give position via props.
| **`Board`** | The entire 8x8 board with 64 total squares. | `Board` only consists of `Square` components, therefore instead of passing `Square` components to `Board` as children, `Board` would probably just own them. This means `Board` would then need `Knight`'s **current position**, a two-item array with a column (**`x`**) and row (**`y`**) position. |

#### Where will the current state live?

If it can be helped, not `Board`. It's a good idea to have as little state in components as possible. Since `Board` will already have some layout logic, it's best to not burden it with managing state. However, for this simple demo, it's rather trivial at this point. Let's assume state exists *somewhere* and think about it later. Meanwhile, let's make sure the components render correctly when they receive said state via props.

The goal is to make `Knight` draggable. This requires maintaining `knightPosition` in some kind of state storage and having some way to update it.

React is not opinionated about the state management or the data flow (e.g. Flux, Redux, Rx).

---

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.<br>
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

[chessboard.webm](https://user-images.githubusercontent.com/94825943/205294379-faaae590-7611-43f8-a233-580263ca5fb2.webm)
