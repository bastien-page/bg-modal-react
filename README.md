# Modal React component

## Installation

You can install this component with npm or yarn :

    npm i bg-modal-react

or

    yarn add bg-modal-react

## Use in React project

Import the Modal component

    import Modal from "bg-modal-react";

## Example

### App.js

```js
function App() {
  // Add UseState to manage Open and Close modal
  const [openModal, setOpenModal] = useState(false);

  // Create your custom style
  const customModal = {
    backgroundContainer: "rgba(146, 146, 146, 0.6)",
    backgroundColor: "#8ea719",
    topPosition: "50%",
    leftPosition: "50%",
    boxShadow: "5px 5px 15px 5px rgba(0, 0, 0, 0.43)",
    color: "white",
    fontSize: "20px",
  };

  return (
    <div
      //If you want use KeyboardEvent
      onKeyUp={(e) =>
        (e.code === "Escape" || e.code === "Enter") && setOpenModal(false)
      }
    >
      <button onClick={() => setOpenModal(true)}>Ouvrir la modal</button>

      {/* Create condition to show Modal  */}
      {openModal && (
        <Modal style={customModal} setOpenModal={setOpenModal}>
          {/* Modal must 2 props : style and hook useState
          Your message must be in children */}
          Inscription
        </Modal>
      )}
    </div>
  );
}

export default App;
```
