<h1 align="center">OtpView</h1>

<img src="https://raw.githubusercontent.com/mukeshsolanki/android-otpview-pinview/master/screenshots/ss1.png" width="270" height="480" /> &nbsp;&nbsp;
<img src="https://raw.githubusercontent.com/mukeshsolanki/android-otpview-pinview/master/screenshots/ss2.png" width="270" height="480" /> &nbsp;&nbsp;
<img src="https://raw.githubusercontent.com/mukeshsolanki/android-otpview-pinview/master/screenshots/ss3.png" width="270" height="480" /> &nbsp;&nbsp;


## How to integrate into your app?
Integrating the project is simple a refined all you need to do is follow the below steps

Step 1. Add the JitPack repository to your build file. Add it in your root build.gradle at the end of repositories:

```java
allprojects {
  repositories {
    ...
    maven { url "https://jitpack.io" }
  }
}
```
Step 2. Add the dependency
```java
dependencies {
         implementation 'com.github.immujahidkhan:OTPView:0.0.1'
}
```

## How to use the library?
Okay seems like you integrated the library in your project but **how do you use it**? Well its really easy just add the following to your xml design to show the otpview

```xml
.....
 <com.immujahidkhan.OtpView
      android:id="@+id/otp_view"
      android:layout_width="wrap_content"
      android:layout_height="wrap_content"
      android:layout_marginTop="72dp"
      android:inputType="number"
      android:itemBackground="@color/colorPrimary"
      android:textColor="@android:color/white"
      app:itemCount="6"
      app:lineColor="@color/colorPrimary"
      app:viewType="line"
      />
.....
```
Add otpview style in the AppTheme
```xml
  <style name="AppTheme" parent="Theme.AppCompat.Light.NoActionBar">
    <!-- Customize your theme here. -->
    <item name="otpViewStyle">@style/OtpWidget.OtpView</item>
  </style>
```
To get a callback when the user enters the otp make use of `OnOtpCompletionListener` like wise

```java
 private OtpView otpView;
 otpView = findViewById(R.id.otp_view);
 otpView.setListener(new OnOtpCompletionListener() {
   @Override public void onOtpCompleted(String otp) {

     // do Stuff
     Log.d("onOtpCompleted=>", otp);
   }
 });
```

That's pretty much it and your all wrapped up.

## OtpView Attributes
| Attribute | Use |
| ----------| --- |
| app:itemCount | sets the length of the otp view |
| app:itemWidth | sets the with of each item inside the otp view |
| app:itemHeight | sets the height of each item inside the otp view |
| app:itemSpacing | sets the space between each item in otp view |
| app:lineWidth | sets the line border width |
| app:lineColor | sets the color to the line border |
| app:viewType | sets the view type of the otp view it can be either `rectangle` `line` or `none` |
| app:cursorVisible | sets the visibility of the cursor |
| app:cursorColor | sets the color of the cursor |
| app:cursorWidth | sets width of the cursor |
| app:itemBackground | sets the background color of each item in the otp view |
| app:hideLineWhenFilled | toggles the line border |
| app:rtlTextDirection | toggles RTL text direction |
| app:state_filled | toggles the option fill the field after data has been entered (Style of file can we set with a drawable assigned using itemBackground |

Apart from these you can use any property that applies to an `EditText`.
