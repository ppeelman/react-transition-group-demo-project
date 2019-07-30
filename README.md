## react-transition-group

Documentation: https://reactcommunity.org/react-transition-group/

`npm install react-transition-group --save`

### Transition component

There are 4 main states a Transition can be in:

- **'entering'**
- **'entered'**
- **'exiting'**
- **'exited'**

3 mandatory props:

- **in**: Show the component; triggers the enter or exit states (boolean, default: false)
- **timeout**: The duration of the transition, in milliseconds. Required unless addEndListener is provided.
- **children**: A function child can be used instead of a React element. This function is called with the current transition status ('entering', 'entered', 'exiting', 'exited'), which can be used to apply context specific props to a component.

Optional props:

- **mountOnEnter**: By default the child component is mounted immediately along with the parent Transition component. If you want to "lazy mount" the component on the first in={true} you can set mountOnEnter. After the first enter transition the component will stay mounted, even on "exited", unless you also specify unmountOnExit. (boolean prop)
- **unmountOnExit**: By default the child component stays mounted after it reaches the 'exited' state. Set unmountOnExit if you'd prefer to unmount the component after it finishes exiting. (boolean prop)
- 6 different events to listen to:

  - **onEnter**
  - **onEntering**
  - **onEntered**
  - **onExit**
  - **onExiting**
  - **onExited**

=> useful to create 'staggered' animations: where one animation starts when another ends

### CSSTransition component

CSSTransition applies a pair of class names during the appear, enter, and exit states of the transition. The first class is applied and then a second _-active class in order to activate the CSS transition. After the transition, matching _-done class names are applied to persist the transition state.

The prop **classNames** contains the classname which is then used to append _-enter, _-enter-active etc.

To still use your own CSS classnames, just set an object instead:

```js
classNames={{
        enter: "",
        enterActive: "ModalOpen",
        exit: "",
        exitActive: "ModalClosed"
      }}
```

### TransitionGroup component

The <TransitionGroup> component manages a set of transition components (<Transition> and <CSSTransition>) in a list. Like with the transition components, <TransitionGroup> is a state machine for managing the mounting and unmounting of components over time.

Consider the example below. As items are removed or added to the TodoList the in prop is toggled automatically by the <TransitionGroup>.

Note that <TransitionGroup> does not define any animation behavior! Exactly how a list item animates is up to the individual transition component. This means you can mix and match animations across different list items.

## Alternative animation packages

- **react-motion**: https://github.com/chenglou/react-motion
  uses real-world physics to animate things, the developer only specifies start and end state, not timing

- **React Move**: https://react-move.js.org/#/
  based on d3.js

- **react-router-transition**: http://maisano.github.io/react-router-transition/
