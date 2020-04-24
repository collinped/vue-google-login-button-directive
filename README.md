# vue-google-login-button-directive

> :closed_lock_with_key: A simple [Vue](https://vuejs.org) directive to include [Google Sign-In Button](https://developers.google.com/identity/sign-in/web/sign-in) behavior in any component.

## Install

```bash
$ npm install --save vue-google-login-button-directive

$ yarn add vue-google-login-button-directive
```

## Usage

Import the directive and attach it to any component, let's give you an example:

> Important: `OnGoogleAuthSuccess` and `OnGoogleAuthFail` are mandatory methods you have to declare in your component where you are using the directive.

```html
<template>
  <button v-google-login-button="clientId" class="google-signin-button">
    Continue with Google
  </button>
</template>

<script>
  import GoogleLoginButton from 'vue-google-login-button-directive'
  export default {
    directives: {
      GoogleLoginButton
    },
    data: () => ({
      clientId: 'Your_Google_Client-Id'
    }),
    methods: {
      OnGoogleAuthSuccess(idToken) {
        // Receive the idToken and make your magic with the backend
      },
      OnGoogleAuthFail(error) {
        console.log(error)
      }
    }
  }
</script>

<style>
  .google-signin-button {
    color: white;
    background-color: red;
    height: 50px;
    font-size: 16px;
    border-radius: 10px;
    padding: 10px 20px 25px 20px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  }
</style>
```

> Looking for the [Facebook counterpart](https://github.com/collinped/vue-facebook-login-button-directive)?
