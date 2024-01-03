# Reduce

Kotlin Multiplatform Library

### Publish to MavenCentral

1) Registering a Sonatype account as described here: 
   https://dev.to/kotlin/how-to-build-and-publish-a-kotlin-multiplatform-library-going-public-4a8k
2) Add developer id, name, email and the project url to
   `/convention-plugins/src/main/kotlin/convention.publication.gradle.kts`
3) Add the secrets to `local.properties`:

```
signing.keyId=...
signing.password=...
signing.secretKeyRingFile=...
ossrhUsername=...
ossrhPassword=...
```

4) Run `./gradlew :dodo:publishAllPublicationsToSonatypeRepository`

### Build platform artifacts

#### Android aar

- Run `./gradlew :reduce:assembleRelease`
- Output: `/reduce/build/outputs/aar/reduce-release.aar`

#### JVM jar

- Run `./gradlew :reduce:jvmJar`
- Output: `/reduce/build/libs/reduce-jvm-1.0.jar`

#### iOS Framework

- Run `./gradlew :reduce:linkReleaseFrameworkIosArm64`
- Output: `/reduce/build/bin/iosArm64/releaseFramework/reduce.framework`

#### JS file

- Run `./gradlew :reduce:jsBrowserProductionWebpack`
- Output: `/reduce/build/dist/js/productionExecutable/reduce.js`

#### macOS Framework

- Run `./gradlew :reduce:linkReleaseFrameworkMacosArm64`
- Output: `/reduce/build/bin/macosArm64/releaseFramework/reduce.framework`

#### Linux static library

- Run `./gradlew :reduce:linkReleaseStaticLinuxX64`
- Output: `/reduce/build/bin/linuxX64/releaseStatic/libreduce.a`

#### Windows static library

- Run `./gradlew :reduce:linkReleaseStaticMingwX64`
- Output: `/reduce/build/bin/mingwX64/releaseStatic/libreduce.a`
