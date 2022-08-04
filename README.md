# <img align="left" src="ic_launcher.png" height="60" width="60" /> <p align=left>Telegram +<img align="center" src="icon_foreground.png" height="60" width="60" ></p>

## About 
>Based on 8.8.6

INDIAN origin based 🇮🇳
- Reincarnation of Telegram, Telegram X, Nekogram, Nicegram 

## What's New:

- [x] Fingerprint as Default Security lock.
- [ ] Accent Color 🎨
- [ ] Enable Reaction
- [ ] Two icon for Profile Editing (keep both or use only one user dependent)
- [ ] Change of Icon (duotone)
- [ ] Redesign Media Player 
- [ ] Swipe Control in media player 
- [x] N Many More ...😍🥳

## Preview
>Duotone Icon with Color Palette (Default [blue]())
<img src="Screenshot 1.png" height="850" width="400" />

## Features:

- [x] Profile Pic full display toggle ( Source Telegram X)
- [x] Show either Phone Number or Unique ID or none (Source )
- [x] Tablet Mode (Source )
- [x] Clear Media data (Source Telegram X)
- [x] Go to Source Chat (Source Telegram X)
- [x] Pin Saved Messages (Source Telegram)
- [x] Scrolling Pin Messages (Source Telegram X)
- [x] Customize Double tap (Source )

```
Note: Hi everyone the above points is what 
  I want to be integrated in the app,
     But Since I'm not a developer 
    I can't implement this feature.
```

### Biometric FingerPrint Authentication (Java Based Code)

- activity_main.xml
```
android:id="@+id/main_layout"
android:visibility="gone"
```

- built.gradle
```
dependencies{
    implementation 'androidx.biometric:biometric:1.0.1'
}
```

- MainActivity.java
```
public class MainActivity extends AppCompatActivity {
    

   BiometricPrompt biometricPrompt; // Use androidx.biometric
   BiometricPrompt.PromptInfo promptInfo;
   ConstraintLayout mMainLayout;


   @Override
   protected void onCreate(Bundle savedInstanceState) {
       super.onCreate(savedInstanceState);
       setContentView(R.layout.activity_main);
       mMainLayout = findViewById(R.id.main_layout);


       BiometricManager biometricManager=BiometricManager.from(this);
       switch(biometric Manager.canAuthenticate())
       {
            case BiometricManager.BIOMETRIC_ERROR_NO_HARDWARE:
                Toast.makeText(getApplicationContext(), "Device Doesn't have fingerprint", Toast.LENGTH_SHORT).show();
                break;

            case BiometricManager.BIOMETRIC_ERROR_HW_UNAVAILABLE:
                Toast.makeText(getApplicationContext(), "Not Working", Toast.LENGTH_SHORT).show();

            case BiometricManager.BIOMETRIC ERROR_NONE_ENROLLED:
                Toast.makeText(getApplicationContext(), "No FingerPrint Assigned", Toast.LENGTH_SHORT).show();
       }

       
      Executor executor = ContextCompat.getMainExecutor(this);

      biometricPrompt = new BiometricPrompt(MainActivity.this, executor, new BiometricPrompt.AuthenticationCallback() {
            @Override
            public void onAuthenticationError(int errorCode, @NonNull CharSequence errString) {
                super.onAuthenticationError(errorCode, errString);
            }

            @Override
            public void onAuthenticationSucceeded(@NonNull BiometricPrompt.AuthenticationResult result) {
                super.onAuthenticationSucceeded(result);
                Toast.makeText(getApplicationContext()), "Login Successfully", Toast.LENGTH_SHORT.short();
                mMainLayout.setVisibility(view.VISIBLE);
            }

            @Override
            public void onAuthenticationFailed() {
                super.onAuthenticationFailed();
            }
        });

        promptInfo = new BiometricPrompt.PromptInfo.Builder()
                       .setTitle("Test Built")
                       .setDescription("Use FingerPrint to Login")
                       .setDeviceCredentialAllowed(true).built();

        biometricPrompt.authenticate(promptInfo);

   }  
}
```

How many of you guys really want the features to be implemented [Poll](). If you want to join the chat to discuss, suggest new ideas [Click Here]() 

Participate in the Poll which version of Telegam you used the most [Poll]()
