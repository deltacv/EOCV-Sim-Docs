# Building from Source

Especially for the users that wish to use _EOCV-Sim_ with Kotlin, which is a feature not currently supported with workspaces, you can instead opt to download the sim's source code and build it after adding your own pipelines

1. Make sure to have IntelliJ IDEA installed. Any IDE with Java Gradle support should work, but it is extremely recommended to use IntelliJ.
2. Clone EOCV-Sim's repository using Git, either from the command line;

```
git clone https://github.com/deltacv/EOCV-Sim
```

or using IntelliJ;

<figure><img src="../.gitbook/assets/image (6).png" alt="" width="545"><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (7).png" alt="" width="563"><figcaption><p>Click on "clone" after entering the URL</p></figcaption></figure>

3. After importing EOCV-Sim into IntelliJ, you can start adding your own pipelines into the "TeamCode module". Kotlin is already configured in the project, so you don't need to do any additional setup;

<figure><img src="../.gitbook/assets/image (8).png" alt="" width="395"><figcaption></figcaption></figure>

4. Run EOCV-Sim using IntelliJ with the "Run Simulator" run configuration. **You will need to close and run the simulator every time you make changes to your pipelines, you won't be able to see any changes otherwise.**

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>
