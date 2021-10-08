# How it works

## Lifecycle

The executable unit of EOCV-Sim are `OpenCvPipeline`s, created by the user. The lifecycle is automatically managed by the sim, calling:

* `init` before the first `processFrame`
* `processFrame` every time a new frame is dispatched from an [Input Source](../features/input-sources.md)
* `onViewportTapped` when the image displayed is clicked with the mouse \(or tapped if running the pipeline on a phone\)

```java
import org.opencv.core.Mat;
import org.openftc.easyopencv.OpenCvPipeline;

public class SamplePipeline extends OpenCvPipeline {

    @Override
    public void init(Mat input) {
        // Executed before the first call to processFrame
    }

    @Override
    public Mat processFrame(Mat input) {
        // Executed every time a new frame is dispatched
        
        return input; // Return the image that will be displayed in the viewport
                      // (In this case the input mat directly)
    }

    @Override
    public void onViewportTapped() {
        // Executed when the image display is clicked by the mouse or tapped
        // This method is executed from the UI thread, so be careful to not
        // perform any sort heavy processing here! Your app might hang otherwise
    }

}
```

 You can learn more about pipelines in [their respective section](../pipelines.md).

## Adding pipelines to EOCV-Sim

There are two ways for adding your own pipelines:

* [Workspaces](../workspaces/what-are-workspaces.md), which are the fastest and most flexible method of using the sim, since the pipelines are built on-the-fly and changes are applied immediately.
* [Building from source](../other/untitled.md), which allows the use of other JVM languages such as Kotlin, but it is slower since you have to recompile and wait for the sim to open every time you make changes in your pipelines.

Workspaces are the recommended method for development if you use Java. You can use any IDE or text editor for them. We officially support [Android Studio](../workspaces/android-studio.md) \(sort of\), [VS Code, and IntelliJ IDEA](../workspaces/vscode-and-intellij.md). 

## Executing a pipeline

Once you have added a pipeline using any of the methods mentioned before, executing any given pipeline is very simple. Your pipeline should appear in the "Pipelines" list, the first one located on the right section:

![In this case we will use the SamplePipeline shown before](../.gitbook/assets/image%20%281%29.png)

You can simply select the pipeline by clicking it with your mouse, and[ the life cycle explained before](how-it-works.md#lifecycle) will start in your code. Notice the gears icon the pipeline has, this means that the pipeline was added using the [workspaces ](../workspaces/what-are-workspaces.md)method. As opposed to the DefaultPipeline which has a hammer and a wrench icon, and means that it was added with the [Build from Source](../other/untitled.md) method \(though it's technically hard coded so that there is always a pipeline available to run when there's not any other\)

