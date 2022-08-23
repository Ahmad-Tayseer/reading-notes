# ***Read: Class 32 - Context API - Behaviors***

***

## ***Hooks and Context example***

***

## **With regard to the React Context API, what does a “provider” do?**

Our context provider is now responsible for both displaying the local state of the snackbars (we call them alerts), and for exposing an API for globally managing them.

***

## **With regard to the React Context API, how would we implement a “consumer” role?**

The other half of the puzzle is we now need a consumer for this provider. 

    import { useContext } from 'react'

    import { SnackBarContext } from 'components/snack-bar-provider'

    const useSnackBars = () => useContext(SnackBarContext)

    export default useSnackBars

***

## **Specifically with Context, how are we “wrapping” components to achieve our goals?**

It turns out that our custom hook from before is nothing more than a small wrapper around the useContext internal React hook, which consumes our new context. Our provider exposes the state mutator setAlerts directly, but we need something much higher level. We don’t want our components fumbling around with how to add an alert without destroying existing ones, and so on. Think of setAlerts as a private method, and we need to expose a public method that abstracts away the noise.

***

[README](README.md)
