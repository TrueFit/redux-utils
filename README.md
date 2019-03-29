# truefit-redux-utils

This library is a set of redux util functions. These are patterns that we have used across projects and found to be helpful.

## Install

```bash
npm install truefit-redux-utils
```

or

```bash
yarn add truefit-redux-utils
```

## Reducers

### State Reducer
An HOF that allows you to express your reducer as a series of states.

| Parameter    | Type      | Description                                                                             |
| ------------ | --------- | --------------------------------------------------------------------------------------- |
| initialState | any       | the initial value of the reducer                                                        |
| states       | js object | this object has the states (action types) as the keys, and the transforms as the values |

```javascript
import {stateReducer} from 'truefit-redux-utils';
import {ADD_ITEM, REMOVE_ITEM} from '../actions';

export default stateReducer([], {
  [ADD_ITEM]: (state, payload) => [...state, payload],
  [REMOVE_ITEM]: (state, payload) => state.splice(state.indexOf(payload), 1),
});
```
