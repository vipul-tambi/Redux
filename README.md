state=> action-creators =>index.js=> iske andar dispatch function aayega
	
	reducers=>actionReducers=>isme reducer function aayega jisme state aur action honge
		=>index.js=> combinedReducers

	index.js=>export * as actionCreators from "./action-creators/index";

	store.js=>import { createStore, applyMiddleware } from "redux";
		  import reducers from "./reducers";
		  import thunk from "redux-thunk";
		  export const store = createStore(reducers, {}, applyMiddleware(thunk));
