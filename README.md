# <img src="https://github.com/Coolboyrajat/Flaticons/blob/main/svg/Star%202.svg" height="40" width="40" /><img align="center" src="TeleGram ++.svg" height="60" width="200" />

## About 
>Based on 8.9.2

Love from 🇮🇳
- Reincarnation of Telegram, Telegram X, Nekogram, Nicegram 

## What's New:

- [ ] Design from Scratch by [@Radioactive](https://github.com/Coolboyrajat)
- [ ] Action Bar Toggler
- [x] Fingerprint as Default Security lock.
- [ ] Accent Color 🎨
- [ ] Number of icon for Profile Editing `[1,2 or 5 user dependent (min 1 required)]`
- [ ] New Icon (duotone)(Animated)
- [ ] Redesign Media Player 
- [ ] Swipe Control in media player 
- [ ] Some Settings will Pop up in the middle & Some from bottom.
- [ ] Select Saved Message, QR code or Download button in Action tab-bar Screen for better productivity. 
- [ ] Delete Media data inside `Group/Channel` media tab nad if `owner/admin` remove source chat.
- [ ] Calender in Siderbar to remember Date (User based)
- [x] N Many More Some things ...😍🥳

```
Note: Hi everyone the above points is what 
  I want to be integrated in the app,
     But Since I'm not a developer 
    I can't implement this feature.
```

## Demo Preview: <img src="https://github.com/Coolboyrajat/Flaticons/blob/main/svg/Star%202.svg" height="40" width="40" />[PROTOTYPE](https://www.figma.com/proto/4OuObhrp6NOdEuZ1c1UGBy/Telegram?node-id=645%3A74&scaling=min-zoom&page-id=0%3A1&starting-point-node-id=645%3A74)
>Duotone Icon with Color Palette

<img src="Screenshot.png" height="850" width="400" />

Get ready for more ... Do you like duotone icon in the demo preview [Poll]()

I'm also thinking about a little change in icon for `'PREMIUM USER'`. Do guys what to give any [Suggestion / Discuss]()


## Features:

- [x] Profile Pic as background toggle (Source Nikogram, Telegram X)
- [x] Show either Phone Number or Unique ID or none (Source Nikogram)
- [x] More than 5+ Accounts (Source Telegram X)
- [x] Tablet Mode (Source NIkogram)
- [x] Clear Media data (Source Telegram X)
- [x] Go to Source Chat (Source Telegram X)
- [x] Pin Saved Messages (Source Telegram)
- [x] Scrolling Pin Messages (Source Telegram X)
- [x] Customize Double tap (Source )
- [x] Enable Quick Reaction (Source Telegram X)
- [x] Transparent Status Bar (Source Nikogram)
- [x] Emoji set (Source Telegram X)
- [x] Disable Jump to next Channel (Source Nikogram)
- [x] Multi-Select messages or media (Source Telegram X)


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
