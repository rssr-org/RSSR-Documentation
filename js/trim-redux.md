# Trim-Redux

Trim-redux is a library which make the redux easier to use.We don't have action, reducer, dispatch, combinReducer by using the 
trim-redux library and all we do is calling setStore command which implemented in trim-redux and do all redux thing behind the scence. 
To learn more about trim-redux follow the [official document](https://github.com/ebrahimiaval/trim-redux#readme)

# Usage

## Import trim-redux
    import {compose, createStore as createStoreProvider} from 'trim-redux';

## Redux states:
 each item in this list is a one state in redux store and value of this is default value

    export const defaultState = {
        localUser: {updated: false, token: null, detail: null},
        post: null,
        home: {isLoading: true},
        skeleton: {
            title: 'Occor when Error fetch skeleton!'
        }
    }

## create Redux Store

cearte store with defaultState
create store with combine server feched data and default store states


    export const createStore = (state = {...defaultState}) => createStoreProvider(state, composeEnhancer);

    export const clientCreateStore = function () {
        let states;

        if (isSet(window.RSSR_UPDATED_REDUX_STATES)) {
            states = {
                ...defaultState,
                ...window.RSSR_UPDATED_REDUX_STATES
            };
            delete window.RSSR_UPDATED_REDUX_STATES;
        }

        return createStore(states);
    }
