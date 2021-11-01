# Conditional Rendering

One way we can do conditional rendering is to use React elements as variables.

First, we can use state to give us a true or false value dependant on whether or not the user is logged in.

```
function LoginControl (props) {

  const [isLoggedIn, setLogIn] = useState(false)

  function handleLoginClick () {
    setLogIn(true);
  }

  function handleLogoutClick () {
    setLogIn(false);
  }

  let button;

```

We can use `if...else` to conditionally render these React elements.

```if (isLoggedIn) {
    button = <LogoutButton onClick={ handleLogoutClick } />;
  } else {
    button = <LoginButton onClick={ handleLoginClick } />
  }
```

And then we render on the page the button dependant on what `isLoggedIn` currently is.

 ```return (
    <div>
      <Greeting isLoggedIn={ isLoggedIn } />
      { button }
      </div>
 )
}
```

If we want to prevent a component from rendering at all, we can wrap things in a guard clause that checks state to see if we should or should not return `null`.


## Ternary Rendering

We can also use a ternary if we want to toggle between two different displays.

```return (
    <div>
      {loggedIn ? <h1>Hello</h1> : <h1>Please login</h1>}
      { button }
      </div>
 )
}
```
## Logic Rendering

If we want to use something or nothing, we can use the inherent functionality of `&&` to determine this. Because `&&` returns false if `loggedIn` is false, it displays nothing on the page.

```return (
    <div>
      {loggedIn && <h1>Hello</h1>}
      { button }
      </div>
 )
}
```

## Further Ternary Rendering

We can also use ternaries inline to further reduce our lines of code. Our ternary here is checking `props.logStatus` to see if it should display "Log Out" or "Log in".

```function LogTog(props) {
    return (
        <div>
        <button onClick ={() => {props.toggleLog(!props.logStatus)}> {
            props.logStatus ? "Log Out" : "Log In"
        }</button>
    )
}
```




