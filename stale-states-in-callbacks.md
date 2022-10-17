# how to avoid stale states in callbacks in react

i've been facing this issue since a couple of days

a callback that I've defined in my code cannot access the updated state, instead it seems to have the value of state variable that was present when the callback was first evaluated(is evaluated the correct term?)/used

to avoid this, we can create and use a mutable state variable using `useRef`

yes, so here is what i did -

```
let [myState, setMyState] = useState([])
let myStateRef = useRef(myState)

let myCallback = () => {
    console.log("stale value of myState is - ", myState)
    console.log("updated value of myState is - ", myStateRef.current) 
}

useEffect(() => {
    myStateRef.current = [...myState]
}, [myState])
```
