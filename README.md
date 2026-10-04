# ide

## Firebase Admin SDKs

This project can use the Firebase Admin SDKs for Node.js, Java, Python, and Go. The SDKs provide privileged access to Firebase services from trusted server environments.

### Credentials

Use [Application Default Credentials (ADC)](https://firebase.google.com/docs/admin/setup#initialize_the_sdk_in_non-google_environments) to authenticate. On Google Cloud, the SDKs use the credentials of the runtime service account. For local development, authenticate with `gcloud auth application-default login`, or set `GOOGLE_APPLICATION_CREDENTIALS` to the path of a service-account JSON file:

```sh
export GOOGLE_APPLICATION_CREDENTIALS="/path/to/service-account.json"
```

Do not commit service-account files or other credentials to the repository.

### Node.js

Install the package:

```sh
npm install firebase-admin
```

Initialize the default app with ADC:

```js
const { initializeApp } = require("firebase-admin/app");

const app = initializeApp();
```

### Java

Add the `com.google.firebase:firebase-admin` dependency using the current version from the [Firebase Admin Java setup guide](https://firebase.google.com/docs/admin/setup#java).

Initialize the default app with ADC:

```java
import com.google.auth.oauth2.GoogleCredentials;
import com.google.firebase.FirebaseApp;
import com.google.firebase.FirebaseOptions;

FirebaseOptions options = FirebaseOptions.builder()
    .setCredentials(GoogleCredentials.getApplicationDefault())
    .build();
FirebaseApp app = FirebaseApp.initializeApp(options);
```

### Python

Install the package:

```sh
pip install firebase-admin
```

Initialize the default app with ADC:

```python
import firebase_admin

app = firebase_admin.initialize_app()
```

### Go

Install the package:

```sh
go get firebase.google.com/go/v4
```

Initialize the default app with ADC:

```go
ctx := context.Background()
app, err := firebase.NewApp(ctx, nil)
if err != nil {
    return err
}
```

Import `context` and `firebase.google.com/go/v4` in the Go file containing this code.

For product-specific APIs and additional configuration, see the [Firebase Admin SDK documentation](https://firebase.google.com/docs/admin/setup).
