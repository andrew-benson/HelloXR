# HelloXR
A template for a starter meta quest project

This tutorial describes the essential steps to:

1.  Set up a Unity project that can build and run on a Meta Quest headset.
2.  Develop a basic "hello world" Unity project comprising a single scene with a cube GameObject rendered on the headset.
3.  Configure Camera settings.
4.  Build, run, and test a project on a Meta Quest headset.

This tutorial is the primary reference for starting Meta Quest development quickly.

![Hello World app running on a Meta Quest 2](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/337073903_1256787218585121_2461188438672474420_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=n0nAX1CC41MAX8eQ_Mx&_nc_ht=scontent-man2-1.xx&oh=00_AfCp9WRg7h2qwczHG3Sk5xWepRSZ1Iw6aGoAJ_C76bzU-w&oe=65687F84)

*Hello World app running on a Meta Quest 2*

Prerequisites
-------------

Before reading further, ensure you have followed all steps in the [Set Up Development Environment](https://developer.oculus.com/documentation/unity/book-unity-gsg/) and [Meta Quest Developer Hub](https://developer.oculus.com/documentation/unity/ts-odh/#set-up) guides. By following these guides, your development environment will be ready for your first project in Unity and your Meta Quest headset will be accessible in the Meta Quest Developer Hub.

### Glossary

-   Oculus Integration SDK - An all-in-one source for core features, components, scripts, and plugins to ease the app development process. It comes as a Unity package that contains multiple SDKs.
-   OVRPlugin - A plugin that allows Unity to communicate with the VR Runtime of Meta Quest.
-   Oculus XR Plugin - An extension of the Unity VR subsystem that communicates with OVRPlugin.

Note: This tutorial uses Unity Editor version 2021.3.20f1 and Integration SDK v54.1. Screenshots might differ if you are using other versions, but functionality is similar.

Step 1. Connect headset over USB
--------------------------------

You must set the headset into developer mode and connect it to your computer with a USB cable.

1.  Put on your Meta Quest headset and sign into the account you want to use for development.
2.  On the headset, go to Settings > System > Developer, and turn on the USB Connection Dialog option.
3.  Connect the headset to your computer using a USB-C cable.
4.  When prompted to allow access to data, select Allow.

    ![Allow connection to headset](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/337552984_1256787235251786_4918098165374670071_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=3k5EPua1AKYAX9WsRvo&_nc_ht=scontent-man2-1.xx&oh=00_AfDFQpd-xc_K0Sz2NkIo8gojKeLdoDPE05NdST5u2PcgeA&oe=656868B0)

Step 2. Create new project
--------------------------

Leave your headset aside for now and follow this process:

1.  Open Unity Hub.
2.  On the Projects tab, select New project. If you have installed multiple Unity versions, select the version you want for this project.
3.  Select the 3D Core template.
4.  Under Projects Settings, enter *HelloWorld* as the Project name, choose the location to store it, and select Create project.

    ![Create Unity project](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/336989426_1256787231918453_8919915243042044201_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=h-cbwCfhXo4AX_YNKMl&_nc_ht=scontent-man2-1.xx&oh=00_AfBmPmAFYVAtv9AWGKeHwmL6Audn1copw1bReOgN10YWpQ&oe=65688B2A)

Step 3. Create a Cube GameObject to display to user
---------------------------------------------------

Although not essential, this step will help you confirm that a basic primitive renders on your Meta Quest headset without any issues.

1.  In Unity Editor, go to GameObject > 3D Object > Cube.

    ![Add Cube GameObject](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/337049348_1256787241918452_8614717389220434650_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=BzPWtgFuh-8AX8fGLD3&_nc_ht=scontent-man2-1.xx&oh=00_AfBaKQX3_bQYHP7qJ0m2HphTpbavD8luVAu8oQT-a3h4hQ&oe=65686ED1)

2.  Update the cube's Position to *[0, 0, 2]* and Scale to *[0.2, 0.2, 0.2]*.

    ![Update Cube GameObject](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/347390964_1285760859021090_1833843577097848014_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=i9GBSEMli4QAX8oG3n1&_nc_ht=scontent-man2-1.xx&oh=00_AfDYnoSfSHiW-184aJt9xHq7xxQHYUPMLXQoQhkD05HnXQ&oe=65686B87)

3.  Save your project.

You should now have a cube GameObject in your SampleScene.

Step 4. Import Integration SDK from Oculus Developer Center
-----------------------------------------------------------

Later, you will learn how to import only the SDKs you need so that you reduce the size of your app, but for now, import all of it.

1.  Go to the [Oculus Developer Center](https://developer.oculus.com/downloads/package/unity-integration) page and select Download.
2.  In Unity Editor, go to Assets > Import Package > Custom Package.

    ![Import Package](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/337159428_1256787228585120_5948389350272488091_n.png?_nc_cat=100&ccb=1-7&_nc_sid=e280be&_nc_ohc=tqODDDh63yIAX_g-NFt&_nc_ht=scontent-man2-1.xx&oh=00_AfBMli0HWOCYM_0dVIpu-Qnz4ebsjNYkycCIWMCfzqm89Q&oe=6568957E)

3.  Locate the downloaded `OculusIntegration.unitypackage` file and select Import.
4.  On the Import Unity Package window, leave all the files and folders selected, and select Import.
5.  When prompted to restart Unity, select Restart.

    ![Restart](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/358534334_1316029392660903_4083241143445642796_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=WRlTQh187zwAX-TGlwK&_nc_ht=scontent-man2-1.xx&oh=00_AfD3M2s-ekwW3uIDE2apt26K6YiDF_gTmLswXEtYBkdbYA&oe=65687DC8)

6.  When prompted to clean up old Interaction SDK assets, select Show Assets (Recommended), and then select Clean Up (Recommended).

    ![Interaction SDK cleanup](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/337689280_1256787211918455_3832955982573359297_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=FwvPDEl95QIAX-4WLvr&_nc_ht=scontent-man2-1.xx&oh=00_AfCKBB6eoIo8u0lTppe_-Irk1blyuFgyNGv8f4105loHjg&oe=656865D7)

7.  Confirm by selecting Clean Up Package.

    ![Interaction SDK cleanup confirmation](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/337720159_1256787251918451_8283007666622396180_n.png?_nc_cat=107&ccb=1-7&_nc_sid=e280be&_nc_ohc=go2d-5-fMUoAX-BMILs&_nc_ht=scontent-man2-1.xx&oh=00_AfCdmxIubUFjnclJuMYeGiRiUIxbJdipzGuI80_oADYuAw&oe=656881B0)

8.  When prompted to update Spatializer plugins, select Upgrade.

    ![Update Spatializer](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/336921130_1256787238585119_3576972929607334412_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=_klhuwBKPRkAX9UBE4k&_nc_oc=AQnXIh7GmcB5CrkxGlcXmHPgc1fX_y2XJc8-9-0cTvuj6ETypLThzIuM4BetRBpirxk&_nc_ht=scontent-man2-1.xx&oh=00_AfDoYKZn5X8BnlRKU6Syq5LcxNwOQuDeE5QM1hv1IEH09A&oe=65687103)

9.  When prompted to restart Unity, select Restart.

Important: If you did not see the prompt in numbered list item 5, after restarting Unity Editor, make sure that your OVR Utilities Plugin is set to the one bundled to your Unity Editor. To do so, go to Oculus > Tools > OVR Utilities Plugin > Manual Update OVRPlugin. If they match, you should see this message:

![Unity Utilities Plugin](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/358362977_1316029389327570_4890525707853873682_n.png?_nc_cat=106&ccb=1-7&_nc_sid=e280be&_nc_ohc=GTiNb0UGTGkAX9yQJfb&_nc_ht=scontent-man2-1.xx&oh=00_AfAydFKfNYD7xayr0yUl5zTMY7WW6CNUZpearzPv2vk4Ow&oe=65689CF9)

Step 5. Set up Build Settings and install XR Plugin
---------------------------------------------------

The target platform for Meta Quest headsets is Android and the final output is an .apk file.

1.  In Unity Editor, go to File > Build Settings.
2.  In the Platform list, select Android, and select Switch Platform.

    ![Switch Platform](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/336775687_1256787221918454_8373327264288615834_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=BVovxtPmVGEAX8VTVAf&_nc_ht=scontent-man2-1.xx&oh=00_AfDTdiIOef1ZbH69gUf2lhCIrXmer9CCnmpcD8AsCeGHuQ&oe=65689C8B)

3.  While still in the Build Settings window, focus on the Run Device list and select your Meta Quest headset. If you don't see the headset in the list, ensure you have connected it properly and select Refresh.

    ![Run Device settings](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/337278031_1256787215251788_8318506729512379227_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=esbNzWzq1PYAX_HHw02&_nc_ht=scontent-man2-1.xx&oh=00_AfBBC-y1xZ-4JiiIQuxDP6ncNuT-o8CczooVjTsj9xqkLw&oe=656895A0)

4.  Select Player Settings... in the bottom left of the same window.
5.  Navigate to the Player section in the left panel and select it.

    ![Player settings](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/337553012_1256787258585117_861545128127288919_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=KPurbShKA7YAX8bTqjz&_nc_ht=scontent-man2-1.xx&oh=00_AfCUyDwOSDCOrqDVdVQM9x_1gIbjNEqDArbSluE71u17qQ&oe=6568877C)

6.  Expand the Other Settings section.
    1.  Ensure the Color Space is *Linear*. This is a requirement for developing in OpenXR.

        ![Color space](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/337176759_1256787261918450_2428503429349541749_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=HWKHhN3MDJ4AX_KdrKE&_nc_ht=scontent-man2-1.xx&oh=00_AfCMLmR_h7OlSzb5saX1OLpxM6M-t3jK5jikspR0EmIEOw&oe=65689357)

    2.  Scroll down to the Identification section and update Minimum API Level to *Android 10 (API Level 29)*.
    3.  Scroll down until you see the Configuration section.
    4.  Change the Scripting Backend to *IL2CPP* and make sure only *ARM64* is selected for Target Architectures.

        ![Player settings 2](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/337159028_1256787225251787_2809522318433604748_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=tQnpLuOpRfEAX9lO8YO&_nc_ht=scontent-man2-1.xx&oh=00_AfDYTXExEGioYKNL8wkPVfkP4yQpIx-uh__HJW7IU6wHbw&oe=656882C9)

7.  While still in the Project Settings window, select XR Plugin Management and select Install XR Plugin Management.

    ![XR Plugin Management](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/337238371_1256787248585118_5929761425150240219_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=xTeQIBeGyA8AX9irvHN&_nc_ht=scontent-man2-1.xx&oh=00_AfD8fB8Z9m6BF2EJKryDVMn6UohJSwxrRACNZVnqg9IuBQ&oe=65688D8C)

8.  When installation finishes, go to the Android icon tab and check Oculus in the Plug-in Providers. This installs the Oculus XR Plugin, which is required for VR development.

    ![XR Plugin Management installed](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/336865250_1256787245251785_1492678249093749629_n.png?_nc_cat=101&ccb=1-7&_nc_sid=e280be&_nc_ohc=mEuLORH-rqIAX_LzJb4&_nc_ht=scontent-man2-1.xx&oh=00_AfAUdmLEuuiE5hw5ej4NJ9CFVU-iIe0CgqImiOSD8c3l7w&oe=65686CEA)

Step 6. Add OVRCameraRig to scene
---------------------------------

Oculus Integration SDK contains the OVRCameraRig prefab which is a replacement to Unity's main camera. This means you can safely delete Unity's main camera from the Hierarchy tab.

The primary benefit of using OVRCameraRig is that it offers the OVRManager component (`OVRManager.cs` script). OVRManager provides the main interface to the VR hardware.

Follow this process:

1.  Ensure you have followed all the steps in the [Hello VR on Meta Quest Headset tutorial](https://developer.oculus.com/documentation/unity/unity-tutorial-hello-vr/) to set up your project.
2.  Under Hierarchy tab, right-click Main Camera, and select Delete.
3.  In the Project tab, expand the Assets > Oculus > VR > Prefab folder, and drag and drop the OVRCameraRig prefab into your scene. Alternatively, drag and drop it in the Hierarchy tab.

    ![Add OVRCameraRig](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/338386994_1258890925041417_2028402720336207885_n.png?_nc_cat=110&ccb=1-7&_nc_sid=e280be&_nc_ohc=EPnSLoBSsrwAX9CXaUL&_nc_ht=scontent-man2-1.xx&oh=00_AfCrrNLacukIkSvA7mvYNzKxi4Ee0R1OQfxXdApyKF3svQ&oe=6568951A)

4.  Ensure your project's hierarchy looks like this:

    ![OVRCameraRig Hierarchy](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/338340697_1258890941708082_7465170306964606316_n.png?_nc_cat=109&ccb=1-7&_nc_sid=e280be&_nc_ohc=nAlU6g6T3XIAX8b8Cnc&_nc_ht=scontent-man2-1.xx&oh=00_AfDg4T_MUgP-iv41Z7IJrMYYILV2-qsSRGRwPhWQIeHd7A&oe=65686693)

5.  Select OVRCameraRig in the Hierarchy tab.
6.  With the OVRCameraRig selected in the Inspector, under the OVR Manager component, select Open Settings.

    ![OVRCameraRig Settings](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/338332517_1258890918374751_8362469564406059991_n.png?_nc_cat=111&ccb=1-7&_nc_sid=e280be&_nc_ohc=yrvOZV948MgAX_U1b7O&_nc_ht=scontent-man2-1.xx&oh=00_AfBAPeTDZRhd-orpB-2S_waEMoO9B6eDvDdUIPjABY7xQw&oe=65688FDB)

7.  Ensure your headset is selected under Target Devices.

    ![OVRCameraRig Devices](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/338370466_1258890935041416_9135301470530917061_n.png?_nc_cat=105&ccb=1-7&_nc_sid=e280be&_nc_ohc=g1kF-mI8pAgAX-KE7G9&_nc_ht=scontent-man2-1.xx&oh=00_AfDqeX7ziOqthWZNnMuPMzoaShYhb1l7pZ5VpIMPTBLc3w&oe=656873D6)

Step 7. Build and run project on headset
----------------------------------------

1.  Go to File > Build Settings and, under Scenes, select Add Open Scenes. This should list your open scene.

    ![Add Open Scenes](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/337028761_1256787268585116_3032500462521193866_n.png?_nc_cat=102&ccb=1-7&_nc_sid=e280be&_nc_ohc=3xoMNbZSysIAX8Z9EbB&_nc_ht=scontent-man2-1.xx&oh=00_AfDRU54VPMbvB-DM3aj2tKJyk_EWNrkTyKfMoKpIJLzN2w&oe=6568784E)

2.  Select Build And Run and choose a name for your .apk file, for example, `HelloWorld.apk`.
3.  Put on your Meta Quest to experience your *Hello World* app.

Important: At this stage, you might see a few configuration warnings that prevent you from building the project. If this happens, fix these issues in Step 8, by using the Project Setup Tool in Step 8. Even if your project builds and runs successfully, the settings in the Project Setup Tool will help you optimize it.

Step 8. Troubleshoot and Optimize Project with Project Setup Tool
-----------------------------------------------------------------

1.  In Unity Editor, go to File > Build Settings and then select Player Settings....
2.  In the Project Settings window that opens, select Oculus. This opens the Project Setup Tool.
3.  In the checklist under the Android icon tab of the Project Setup Tool, select Fix All if you haven't built your project successfully.

    ![Project Setup Tool Fix All](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/337149685_1256787271918449_1741311882967024483_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=1VxFKRlq9rIAX9SA5ql&_nc_oc=AQkuCwok6GhyShLx389oEQNo2vzQOqNf_okmJrbzoIAqq1gQPC4iXm7Xn2Izb7Hmc1E&_nc_ht=scontent-man2-1.xx&oh=00_AfDv9SLFjB6eC7TgtIn1RjBlqWhuoSJrvpPIxP7iNPh0iw&oe=65688F17) This helps you fix all of your configuration errors.

4.  If you still see Recommended Items in the list, select Apply All.

    ![Project Setup Tool Apply All](https://scontent-man2-1.xx.fbcdn.net/v/t39.2365-6/337368782_1256787278585115_6919467309358258585_n.png?_nc_cat=108&ccb=1-7&_nc_sid=e280be&_nc_ohc=TPdMEaYSyTAAX80sijq&_nc_ht=scontent-man2-1.xx&oh=00_AfA7rI_74mr7kMC-kHEjebKHQ3jGODLmAqZhXo4Fc5Rp-g&oe=656897A2) This helps you optimize your project.

5.  Go back to the Build Settings window, select Build And Run, and put on your headset.

Note: For faster iteration times, you can use Meta Quest Link which helps you test your Unity projects without building your project. For details, read [Use Meta Quest Link for App Development](https://developer.oculus.com/documentation/unity/unity-link).

Additional troubleshooting steps
--------------------------------

-   Error message `Execution failed for task ':launcher:packageRelease'. A failure occurred while executing com.android.build.gradle.internal.tasks.Workers$ActionFacade...`

    You might have conflicts with a prior Android Studio installation on your computer. To resolve this, try deleting or renaming the `debug.keystore` and `debug.keystore.lock` files in your `\Users\<username>\.android` folder. Restart Unity, and build your project again.

-   For additional troubleshooting, read the [Troubleshooting](https://developer.oculus.com/documentation/unity/unity-enable-device/#troubleshooting) guide.