# Redux Notes

## Store
*The "soul" of Redux. The single source of truth for the application. The store holds the application state and has access to the following methods:*

* getState - returns the current state

    store.getState();

* dispatch - dispatches an action. The only way to update the application state.

    store.dispatch(action);

* subscribe - subscribes a change listener to the state. When the reducer update the state, it calls all subscribed listener methods.
They can access the state using the `.getState` method.

* unsubscribe
This is the method returend when you all the `store.subscribe(listener)`. Useful if you no longer want to call your listener method when the state changes.

    // To subscribe
    const unsubscribe = store.subscribe(() => {
        console.log('Application state updated.');
    });

    // To unsubscribe
    unsubscribe(); 

## Action 
*Plain JavaScript objects. They usually have a payload and always have a type.*

**Example**

    const action = {
        type: 'ADD',
        payload: { value: 5 },
    };

## Reducers
*Reducers are the pure functions we were talking about above. They know what to do with an action and its information (payload).*



# Calculator Demo

*Workflow Order*

* Set default state
* Build utility methods - "How are we going to grab our values."
* Build action creators - "Give us an object, put it in the payload."
* Build hook operators - "Our event listeners for the actions creator. When the event listener fires, it will `dispatch` to the store."

* Subscription Updating
Every time the state changes, this listener will update the `#grand-total` value

    store.subscribe(() => {
        setTotal(store.getState());
    });

Note: `setTotal` is a const variable we established in 
`store.getState();` returns the current state.

    
