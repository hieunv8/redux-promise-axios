# redux-promise-axios

## Action Types
```javascript
export const GET_USERS_WITH_ID = "GET_USERS_WITH_ID";
export const PENDING = "_PENDING";
export const FULFILLED = "_FULFILLED";
export const REJECTED = "_REJECTED";
```

## Actions
```javascript
dispatch({
  type: GET_USERS_WITH_ID,
  url: "https://api.github.com/users/hieunv8",
});
```

## Reducers
```javascript
import * as Actions from "../actions";
import {fromJS} from "immutable";
export default function (state = fromJS({hieunv: null}), action) {
    switch (action.type) {
        case Actions.GET_USERS_WITH_ID + Actions.FULFILLED:
            return state.update("hieunv", (v) => fromJS(action.payload.data));
        default:
            return state;
    }
}
```