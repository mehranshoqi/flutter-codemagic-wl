# White-labeling a Flutter Application with Codemagic

## What is White-labeling in Codemagic?

White-labeling is the process of customizing an application's branding and appearance to match different clients or brands. With Codemagic, you can easily create white-labeled versions of your Flutter application by leveraging variables and configurations.

## Step 1: Adding Variables in Codemagic and Setting the White-label Group

To customize your application for white-labeling, you need to add variables in the Codemagic dashboard. These variables will allow you to change the app icon, package name in Android, bundle identifier for iOS, and other configurations. In addition, you can set a white-label group to organize your white-labeled versions.

![Codemagic Variables](images/IMG_20231126_123914_102.jpg)

1. Open the Codemagic dashboard and navigate to your project.
2. Go to the "Environment" section and click on "Add Variable".
3. Add variables for the specific configurations you want to customize, such as `packageName`, `appName`, `bundleIdentifier`, or `firebaseConfigFile`.
4. Save the variables.
5. To set the white-label group, add a variable named `APP_NAME` and set its value to the desired app name.
6. Save the variable.

![Codemagic Variables](images/IMG_20231126_124053_280.jpg)

![Codemagic Variables](images/IMG_20231126_124206_206.jpg)

## Step 2: Create the codemagic.yaml File

To configure Codemagic for your Flutter project, you need to create a `codemagic.yaml` file in the root directory of your project. This file will contain the necessary configuration settings for building your app on Codemagic.

Follow these steps to create the `codemagic.yaml` file:

1. Open your project in a text editor.
2. Create a new file in the root directory of your project.
3. Name the file `codemagic.yaml`.
4. Add the necessary configuration settings for Android and iOS platforms.

- Specify the target group for your app.
- Choose the machine on which you want to build your Flutter app.
- Add any other required configuration settings.

Here's an example of how the `codemagic.yaml` file might look:

Android:
```yaml
name: Android client release
instance_type: mac_mini_m1
environment:
  flutter: 3.13.7
  groups:
    - sandbox
```

iOS:
```yaml
ios-client-release:
  name: iOS client release
  instance_type: mac_mini_m1
  environment:
    groups:
      - sandbox
    vars:
      XCODE_SCHEME: "Runner"
```
