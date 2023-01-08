Structure of react redux

state=> action-creators =>index.js=> iske andar dispatch function aayega
	
	reducers=>actionReducers=>isme reducer function aayega jisme state aur action honge
		=>index.js=> combinedReducers

	index.js=>export * as actionCreators from "./action-creators/index";

	store.js=>import { createStore, applyMiddleware } from "redux";
		  import reducers from "./reducers";
		  import thunk from "redux-thunk";
		  export const store = createStore(reducers, {}, applyMiddleware(thunk));

App.js
import "./App.css";
import { useSelector, useDispatch } from "react-redux";
import { bindActionCreators } from "redux";
import { actionCreators } from "./state";

function App() {
  const account = useSelector((state) => state.account);
  const dispatch = useDispatch();
  const { depositMoney, withdrawMoney } = bindActionCreators(
    actionCreators,
    dispatch
  );

  return (
    <div className="App">
      <h1>0</h1>
      <button onClick={() => depositMoney(1000)}>Deposit</button>
      <button onClick={() => withdrawMoney(1000)}>Withdraw</button>
    </div>
  );
}

export default App;
