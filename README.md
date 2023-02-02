# <img src="https://github.com/Coolboyrajat/Flaticons/blob/main/svg/Star%202.svg" height="30" width="30" /><img align="center" src="TeleGram ++.svg" height="60" width="200" />

## About 
>Based on 8.9.2

Love from 🇮🇳
- Reincarnation of Telegram, Telegram X, Nekogram, Nicegram 

## What's New:

- [ ] New UI, Design from Scratch by [@Radioactive](https://github.com/Coolboyrajat)
- [ ] Customizable widget in Action Bar;
- [ ] Seperate Pinned Tabs;
- [x] Fingerprint Support for locking app;
- [ ] Accent Color 🎨
- [ ] Number of buttons under Profile Pic `[1,2 or 5 user dependent (min 1 required)]`
- [ ] New Icon (duotone)(Animated);
- [ ] Redesign Media Player;
- [ ] Swipe Control in media player;
- [ ] Some Settings will Pop up in the middle & Some from bottom. 
- [ ] Delete Media data inside `Group/Channel` media tab and if `owner/admin` remove source chat.
- [ ] Calender in Siderbar to remember Date (User based)
- [x] N Many Many More tiny things can't be explained...😍🥳 Go for Prototype down below 👇🏻👇🏻

```
Note: Hi everyone the above points is what 
  I want to be integrated in the app,
     But Since I'm not a developer 
    I can't implement this feature.
```

## Demo Preview: <br>

Use [Figma](https://play.google.com/store/apps/details?id=com.figma.mirror&hl=en&gl=US&referrer=utm_source%3Dgoogle%26utm_medium%3Dorganic%26utm_term%3Dfigma+app&pcampaignid=APPU_1_ckfbY8zmHqeNseMP1-6YmAs&pli=1) app for Best Outcomes of 👉🏼 <img src="https://github.com/Coolboyrajat/Flaticons/blob/main/svg/Star%202.svg" height="30" width="30" />[PROTOTYPE](https://www.figma.com/proto/4OuObhrp6NOdEuZ1c1UGBy/Telegram?node-id=645%3A74&scaling=min-zoom&page-id=0%3A1&starting-point-node-id=645%3A74) 👈🏼
>Duotone Icon with Color Palette

<img src="Screenshot.png" height="850" width="410" />

Get ready for more ... Do you like duotone icon in the demo preview [Poll]()

I'm also thinking about a little change in icon for `'PREMIUM USER'`. Do guys what to give any [Suggestion / Discuss]()


## Features:

- [x] Profile Pic as background toggle (Source Nikogram, Telegram X)
- [x] Show either Phone Number or Unique ID or none (Source Nikogram)
- [x] More than 3+ Accounts (Source Telegram X)
- [x] Tablet Mode (Source Nikogram)
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
- [x] Bottom Action Bar (MDgram)

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

Check out how many of people voted for the features to be implemented [Poll](). If you want to join the chat to discuss, suggest new ideas [Click Here]() 

Participate in the Poll which app you used as replacement of OG Telegram [Poll]()
