Publish Android App Bundle to Google Play

`$ npm install -g deploy-aab-google-play`

`$ deploy-aab-google-play --help`

```bash
Usage: deploy-aab-google-play [options]

Publish Android App Bundle to Google Play

Options:
  -k, --keyFile <path>      set google api json key file
  -p, --packageName <name>  set package name (com.some.app)
  -a, --aabFile <path>      set path to .aab file
  -t, --track <track>       set track (production, beta, alpha...)
  -r, --releaseNote <note>  set release note (only for en-US)
  -e, --exit                exit on error with error code 1.
  -h, --help                output usage information
```

*Example:* 

`deploy-aab-google-play -k ./api-publish.json -p com.laCosaNostra.FiveHundredAndTwelve2 -a ./platforms/android/app/build/outputs/bundle/release/app.aab -t beta -r 'bug fixes'`

**Use in your own program**

```typescript
import { publish } from "deploy-aab-google-play";

publish({
  keyFile: "./api-publish.json",
  packageName: "com.laCosaNostra.FiveHundredAndTwelve2",
  aabFile: "./platforms/android/app/build/outputs/bundle/release/app.aab",
  track: "beta",
  releaseNote: "bug fixes"
})
  .then(() => {
    console.log("Success");
  })
  .catch(error => {
    console.error(error);
  });
```