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
