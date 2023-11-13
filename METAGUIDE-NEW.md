#Note
This guide uses the Meta XR All-in-One SDK package, versus using Oculus Integration SDK (Deprecated)

Prerequisites
-------------

Before reading further, ensure you have followed all steps in the [Set Up Development Environment](https://developer.oculus.com/documentation/unity/book-unity-gsg/) and [Meta Quest Developer Hub](https://developer.oculus.com/documentation/unity/ts-odh/#set-up) guides. By following these guides, your development environment will be ready for your first project in Unity and your Meta Quest headset will be accessible in the Meta Quest Developer Hub.

### Glossary

-   [Meta XR All-in-One SDK](https://developer.oculus.com/downloads/package/meta-xr-sdk-all-in-one-upm/) - An all-in-one source for core features, components, scripts, and plugins to ease the app development process.
-   OVRPlugin - A plugin that allows Unity to communicate with the VR Runtime of Meta Quest.
-   Oculus XR Plugin - An extension of the Unity VR subsystem that communicates with OVRPlugin.

Note: The tutorial uses Unity Editor version 2021.3.20f1 and [Meta XR All-in-One SDK](https://developer.oculus.com/downloads/package/meta-xr-sdk-all-in-one-upm/) v59. Screenshots might differ if you are using other versions, but functionality is similar.

Step 1. Connect headset over USB
--------------------------------

You must set the headset into developer mode and connect it to your computer with a USB cable.

1.  Put on your Meta Quest headset and sign into the account you want to use for development.
2.  On the headset, go to Settings > System > Developer, and turn on the USB Connection Dialog option.
3.  Connect the headset to your computer using a USB-C cable.
4.  When prompted to allow access to data, select Allow.

    ![Allow connection to headset](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/337552984_1256787235251786_4918098165374670071_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=8q7xBKfREAIAX8s_mY5&_nc_ht=scontent-man2-1.xx&oh=00_AfDuc7ivtxUjuBgoXg3epUfyZ9JmDRXRQ22468TREqkP6Q&oe=656C9570)

Step 2. Create new project
--------------------------

Leave your headset aside for now and follow this process:

1.  Open Unity Hub.
2.  On the Projects tab, select New project. If you have installed multiple Unity versions, select the version you want for this project.
3.  Select the 3D Core template.
4.  Under Projects Settings, enter *HelloWorld* as the Project name, choose the location to store it, and select Create project.

    ![Create Unity project](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/336989426_1256787231918453_8919915243042044201_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=Dgi9ZyPk60oAX_2ansq&_nc_ht=scontent-man2-1.xx&oh=00_AfCjNvn-S89fNz6EiQsQULBVAW_eKpAuPCOf18AYh0I35A&oe=656C7FAA)

Step 3. Create a Cube GameObject to display to user
---------------------------------------------------

Although not essential, this step will help you confirm that a basic primitive renders on your Meta Quest headset without any issues.

1.  In Unity Editor, go to GameObject > 3D Object > Cube.

    ![Add Cube GameObject](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/337049348_1256787241918452_8614717389220434650_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=1He5Im0Sw9sAX8G-avI&_nc_ht=scontent-man2-1.xx&oh=00_AfC20NB90c-l4pPLOHLCsHnOkdilOFx7cXs3vIDVXSB4Hw&oe=656C9B91)

2.  Update the cube's Position to *[0, 0, 2]* and Scale to *[0.2, 0.2, 0.2]*.

    ![Update Cube GameObject](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/347390964_1285760859021090_1833843577097848014_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=owC3MxCJxq0AX_AUQhM&_nc_ht=scontent-man2-1.xx&oh=00_AfCO_GIgTzehRNV6SCS1K2l9et_s4VCxm00gOMAgC1O_Mw&oe=656C9847)

3.  Save your project.

You should now have a cube GameObject in your SampleScene.

Step 4. Import Meta XR All-in-One SDK from the Unity Asset Store
----------------------------------------------------------------

Later, you will learn how to import only the SDKs you need so that you reduce the size of your app, but for now, import all of it.

1.  Navigate to Window > Package Manager to open the Unity Package Manager pane.

2.  Go to the [Unity Asset Store](https://developer.oculus.com/documentation/unity/unity-tutorial-hello-vr/ASSETSTOREALL) page and log in if needed.

3.  Select Add to My Assets button.

4.  Select Open in Unity to start the integration process with the Package Manager in Unity. If asked, allow Asset Store Links to be opened by Unity.

5.  Wait for the Unity Package Manager window to open.

6.  On the "Meta XR All-in-One SDK" pane, click Install.

7.  When prompted to restart Unity, click Restart Editor.

    ![Restart](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/399977511_1383307772599731_7639894417932318845_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=YnY_kgxTn5IAX8Ki2ml&_nc_ht=scontent-man2-1.xx&oh=00_AfDMrYyLosjfrjG-R5XIdTuNa1n-y3UImbs-DbdjrSyQuQ&oe=656C9848)

Step 5. Set up Build Settings
-----------------------------

The target platform for Meta Quest headsets is Android and the final output is an .apk file.

1.  In Unity Editor, go to File > Build Settings.
2.  In the Platform list, select Android, and select Switch Platform.

    ![Switch Platform](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/336775687_1256787221918454_8373327264288615834_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=amvoYHiXfEgAX87jCvv&_nc_ht=scontent-man2-1.xx&oh=00_AfCb8sWWfeqRCwryP5DTUmBMjo3sM3Kgu4ACxEL-OBa7Qg&oe=656C910B)

3.  While still in the Build Settings window, focus on the Run Device list and select your Meta Quest headset. If you don't see the headset in the list, ensure you have connected it properly and select Refresh.

    ![Run Device settings](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/337278031_1256787215251788_8318506729512379227_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=IiEttpwuHG8AX_xt7Fc&_nc_ht=scontent-man2-1.xx&oh=00_AfD3MAFBN3WAlA66bJY4Xcro2P7hMtJzd9ahAzruv9wGtg&oe=656C8A20)

Step 6. Run Unity Project Setup Tool
------------------------------------

1.  Navigate to Oculus > Tools > Project Setup Tool. The Unity Project Setup Tool has rules for creating a new application with Meta Quest in Unity.

2.  In the checklist under the Android icon tab of the Project Setup Tool, select Fix All.

    ![Project Setup Tool Fix All](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/337149685_1256787271918449_1741311882967024483_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=Bv-gxdJjtb8AX_z7GqC&_nc_oc=AQlGBn73SFLEgCexJ0ODC-N_SwDuP3MryltGee3dg_nZJMi6CXidNJ9kyze8LgZ2DDI&_nc_ht=scontent-man2-1.xx&oh=00_AfB7dsvXUxj5m2c_oAHC5AHuteRyCMNjBoBypSWf33FCAQ&oe=656C8397) This applies the required settings for creating Meta Quest XR apps, including setting the minimum API version, using ARM64, and installing the Oculus XR Plug-in and XR Plug-in Management package.

3.  If you still see Recommended Items in the list, select Apply All.

    ![Project Setup Tool Apply All](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/337368782_1256787278585115_6919467309358258585_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=HBhq4tQ6WR4AX9ySpzo&_nc_ht=scontent-man2-1.xx&oh=00_AfB9o4J2THHeFQBBeaLXoJ5c0Xtn1A6tz-IxMWapiQhlbg&oe=656C8C22) This optimizes project settings for Meta Quest Unity apps, including texture and graphics settings.

Step 7. Add OVRCameraRig to scene
---------------------------------

[Meta XR Core SDK](https://developer.oculus.com/downloads/package/meta-xr-core-sdk/) contains the OVRCameraRig prefab which is a replacement to Unity's main camera. This means you can safely delete Unity's main camera from the Hierarchy tab.

The primary benefit of using OVRCameraRig is that it offers the OVRManager component (`OVRManager.cs` script). OVRManager provides the main interface to the VR hardware.

Follow this process:

1.  Under Hierarchy tab, right-click Main Camera, and select Delete.
2.  In the Project tab, search for Camera Rig, and drag the OVRCameraRig prefab into your scene. Alternatively, drag it in the Hierarchy tab.

    ![Add OVRCameraRig](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/399698901_1383307755933066_998362524927828782_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=s_i4MRS6EOkAX-1HLKx&_nc_ht=scontent-man2-1.xx&oh=00_AfAcqqa8xTtAdxSk7g3BIkt5imOr1Qnus1QxjQ2GQRcljw&oe=656CAE94)

3.  Ensure your project's hierarchy looks like this:

    ![OVRCameraRig Hierarchy](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/338340697_1258890941708082_7465170306964606316_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=PBWlWR_6LTcAX9AXxED&_nc_ht=scontent-man2-1.xx&oh=00_AfDm66BDQENB9sNygOKQ2pRpMEOEryd2vnvvlaOLlED13w&oe=656C9353)

4.  Select OVRCameraRig in the Hierarchy tab.
5.  With the OVRCameraRig selected in the Inspector, under the OVR Manager component, ensure your headset is selected under Target Devices.

    ![OVRCameraRig Devices](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/399594247_1383307759266399_7307038258008667196_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=vkdCuGV6IUwAX86wVnP&_nc_ht=scontent-man2-1.xx&oh=00_AfC1PykvBWh2cNBNz-D8LU0X4eJrmB4kOw_Jo_B0UQXKOQ&oe=656C7E61)

Step 8. Build and run project on headset
----------------------------------------

1.  Go to File > Build Settings and, under Scenes, select Add Open Scenes. This should list your open scene.

    ![Add Open Scenes](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/337028761_1256787268585116_3032500462521193866_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=9hdFhc_9nRUAX-NLha7&_nc_ht=scontent-man2-1.xx&oh=00_AfBHxS6VY13SI044RCE6WfuaUb86awCTScgj9mM06COMHw&oe=656CA50E)

2.  Select Build And Run and choose a name for your .apk file, for example, `HelloWorld.apk`.
3.  Put on your Meta Quest to experience your *Hello World* app.

Note: For faster iteration times, you can use Meta Quest Link which helps you test your Unity projects without building your project. For details, read [Use Meta Quest Link for App Development](https://developer.oculus.com/documentation/unity/unity-link).

Additional troubleshooting steps
--------------------------------

-   Error message `Execution failed for task ':launcher:packageRelease'. A failure occurred while executing com.android.build.gradle.internal.tasks.Workers$ActionFacade...`

    You might have conflicts with a prior Android Studio installation on your computer. To resolve this, try deleting or renaming the `debug.keystore` and `debug.keystore.lock` files in your `\Users\<username>\.android` folder. Restart Unity, and build your project again.

-   For additional troubleshooting, read the [Troubleshooting](https://developer.oculus.com/documentation/unity/unity-enable-device/#troubleshooting) guide.