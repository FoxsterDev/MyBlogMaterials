# Insight about GameActivity

If you are creating an Android application using native code or have any Unity plugins with Android activities that target Android platforms, 
it is recommended to consider using the "[GameActivity](https://developer.android.com/games/agdk/game-activity) " provided by the Android Game Development Kit (AGDK). 
If you already have existing plugins and are experiencing high ANR (Application Not Responding) rates, 
it is worth considering migrating from "NativeActivity" to "[GameActivity](https://developer.android.com/games/agdk/game-activity) ". 
This could help resolve some of the threading issues related to NativeActivity and potentially reduce your ANR rates.


**Why switch to GameActivity from NativeActivity?**
[Google officially recomends it](https://developer.android.com/games/agdk/game-activity)
>Note: We strongly recommend using GameActivity for new games and other C/C++ intensive applications. If you have an existing NativeActivity application, we recommend migrating to GameActivity.

**Other key points**:
- **Better Threading Support**: GameActivity provides better threading support for lifecycle, input, and touchscreen keyboard events, resulting in improved performance and a smoother user experience.
- **Easier Updates**: With GameActivity, developers can update the GameActivity package independently of the engine updates, making it easier to stay up-to-date with the latest features and bug fixes.
- **Customizable**: GameActivity allows developers to tweak the Unity<>Android bridge with their own customizations, giving them more flexibility to tailor their app to their specific needs.


**What is about Unity**

[Unity finally introduced GameActivity in Unity 2023.1]((https://forum.unity.com/threads/introducing-gameactivity-for-android-in-2023-1.1409418/))


**Android issue tracker linked issues:**

[[ANR] Starting from Android 11 - android.os.MessageQueue.nativePollOnce
](https://issuetracker.google.com/issues/230950647?pli=1)

[Slow GLSurfaceView.Renderer.onSurfaceCreated() can freeze the Activity forever and cause ANR
](https://issuetracker.google.com/issues/269158607?pli=1)

**Date** 28.04.2023,
**Unity** versions <2023