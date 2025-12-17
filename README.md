Repo for reproducing an issue with react-native-background-downloader on react-native 0.76

This repo was created by running:

```bash
npx @react-native-community/cli@15 init RNBGDownloaderIssueRepro --version 0.76
cd RNBGDownloaderIssueRepro
npm install @kesha-antonov/react-native-background-downloader
```

Then `npm run android` to see the issue.
```bash
error Failed to install the app. Command failed with exit code 1: ./gradlew app:installDebug -PreactNativeDevServerPort=8081
e: file:///Users/me/dev/repro-repos/RNBGDownloaderIssueRepro/node_modules/@kesha-antonov/react-native-background-downloader/android/src/main/java/com/eko/RNBackgroundDownloaderModuleImpl.kt:598:9 'if' must have both main and 'else' branches if used as an expression
e: file:///Users/me/dev/repro-repos/RNBGDownloaderIssueRepro/node_modules/@kesha-antonov/react-native-background-downloader/android/src/main/java/com/eko/RNBackgroundDownloaderModuleImpl.kt:607:11 'if' must have both main and 'else' branches if used as an expression FAILURE: Build failed with an exception. * What went wrong:
Execution failed for task ':kesha-antonov_react-native-background-downloader:compileDebugKotlin'.
> A failure occurred while executing org.jetbrains.kotlin.compilerRunner.GradleCompilerRunnerWithWorkers$GradleKotlinCompilerWorkAction > Compilation error. See log for more details * Try:
> Run with --stacktrace option to get the stack trace.
> Run with --info or --debug option to get more log output.
> Run with --scan to get full insights.
> Get more help at https://help.gradle.org. BUILD FAILED in 5s.
info Run CLI with --verbose flag for more details.
```

Fixed with the patch file `patches/@kesha-antonov+react-native-background-downloader+4.3.2.patch`
