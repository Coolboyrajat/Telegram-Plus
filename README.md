# <img src="https://github.com/Coolboyrajat/Flaticons/blob/main/svg/Star%202.svg" height="30" width="30" /><img align="center" src="TeleGram ++.svg" height="60" width="200" />

![TeleGram ++](https://github.com/Coolboyrajat/Telegram-Plus/assets/67316346/cc96b5fb-a22d-4733-9aae-78e4161fb669)

## About 
>Based on 9.6.7

Love from 🇮🇳
- Reincarnation of Telegram, Telegram X, Nekogram, Nicegram, MDgram 

## What's New:

- [x] New UI, Design from Scratch by [@Radioactive](https://github.com/Coolboyrajat)
- [x] Customizable widget in Action Bar;
- [x] Separate Pinned Tabs;
- [ ] Separate interaction between Profile & Text in all Chats
- [x] Fingerprint Support for locking app;
- [x] Accent Color 🎨
- [x] Number of buttons under Profile Pic `[1,2 or 5 user dependent (min 1 required)]`
- [x] New Icon;
- [ ] Redesign Media Player;
- [ ] Swipe Control in media player;
- [ ] Delete Media data inside the `Group/Channel` media tab and if `owner/admin` remove source chat.
- [x] Calender in Sidebar to add events (User-based)
- [ ] Payment through QR code scanning;💡
- [x] N Many Many More tiny things can't be explained...😍🥳 Go for Prototype down below 👇🏻👇🏻

```
Note: Hi everyone the above points is what 
  I want to be integrated into the app,
   But Since I'm not a core developer 
    I can't implement this feature.
```

## Demo Preview:

<p align="center"> 👉🏼 First Glance 👈🏼 </p>

![Glance Preview](https://github.com/Coolboyrajat/Telegram-Plus/assets/67316346/3a005146-9527-419e-b0a6-3cce393b0515)
![Glance Preview (1)](https://github.com/Coolboyrajat/Telegram-Plus/assets/67316346/6bbf63f3-be91-43de-9c99-743f0ceab211)

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

### Biometric FingerPrint Authentication (Java-Based Code)

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
<br>

- I would appreciate any ideas or suggestions. If you want to join the chat to discuss, suggest new ideas [Click Here](https://discord.gg/YqeTbs3Y)
- Check out how many people voted for the features to be implemented [Poll]().
- Participate in the poll & see how many people are already excited to see a live version [Poll]()
- Most used variant [strats]()

<br>

### [YOU CAN CONTACT ME, IF YOU ARE A DEVELOPER AND TRY TO HELP ME BUILD THE APP.]()
[<img src="https://assets-global.website-files.com/6257adef93867e50d84d30e2/636e0b5493894cf60b300587_full_logo_white_RGB.svg" height='50' width='150' />](https://discord.gg/YqeTbs3Y)
