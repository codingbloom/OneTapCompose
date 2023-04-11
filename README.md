<h1 align="center">Google One Tap SignIn</h1></br>

<p align="center">
Google One Tap SignIn Library in Jetpack Compose.
</p><br>

### Gradle Dependencies:

Step-1: Add the below dependency in your app level module's `build.gradle` file:
```gradle
dependencies {
    implementation 'com.github.stevdza-san:OneTapCompose:1.0.0'
}
```
Step-2: Add repository in your `settings.gradle` file:
```
dependencyResolutionManagement {
    repositories {
        ...
        maven { url 'https://jitpack.io' }
    }
}
```
## How to Use this library:

Connect your android Project to Firebase and collect your 'CLIENT_ID' from there.</br></br>
And then, just call `OneTapSignInWithGoogle()` function.</br>
You will also pass `OneTapSignInState`, because that state is used later to trigger One-Tap dialog.</br></br>
Demo Project with 'GoogleOneTapSignIn' library:

```kotlin
    val oneTapState = rememberSignInState()
    GoogleOneTapSignIn(
        state = oneTapState,
        clientId = "PUT_YOUR_CLIENT_ID_HERE",
        onTokenIdReceived = { tokenId ->
            Log.d("TAG", tokenId)
        },
        onDialogDismissed = { message ->
            Log.d("TAG", message)
        }
    )
```

To trigger OneTap dialog, just call `open()` function.

```kotlin
    Button(onClick = { oneTapState.open() }) {
        Text(text = "Sign in")
    }
```

# Credits
```xml
All Credits goes to my teacher 'Stevdza-san (Stefan Jovanović)'.
```
