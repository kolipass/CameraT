# CameraT
##Customization
 * Custom shot sound
 
 You can takePicture() thith custom sound:  
 ```
        camera = mCameraPreview.getCamera();
        SimpleShutterSoundPlayer transaction = new SimpleShutterSoundPlayer(getActivity(), camera, R.raw.shutter);
        mCameraPreview.takePicture(false, true, transaction);
```
 * Custom surface
 
 You can set custom PreviewStrategy to CameraView:  ```mCameraView.setPreviewStrategy(new HoleStrategy(mCameraPreview)```
 
  ```
     class HoleStrategy extends SurfacePreviewStrategy {

        public HoleStrategy(CameraView cameraView) {
            super(cameraView);
        }

        protected SurfaceView makeSurfaceView(Context context) {
            return new HoleSurfaceView(context);
        }
    }
    ```
   [HoleSurfaceView](https://gist.github.com/kolipass/b6b6ba44de853adfaec3)
    
## Installing

Add it to your build.gradle with:
```gradle
repositories {
    maven { url "https://jitpack.io" }
}
```
and:

```gradle
dependencies {
    compile 'com.github.kolipass:camerat:1.0.1'
}
```
