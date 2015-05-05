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
 * Normal usage
 
Add it to your root build.gradle with:
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

 * Local usage
 
If you want to use you own local fork:
You need run ```    gradle install ```and check the local Maven repo folder ```.m2/repository/CameraT/library```

Add it to your root build.gradle with:
```gradle
repositories {
        mavenLocal()
}
```
and:

```gradle
dependencies {
    compile 'CameraT:library:unspecified'
} 
```
[![Release](https://img.shields.io/github/tag/kolipass/CameraT.svg?label=maven)](https://jitpack.io/#kolipass/CameraT)
