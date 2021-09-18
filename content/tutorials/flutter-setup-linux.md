---
title: "Flutter Setup Linux"
date: 2021-09-18T06:48:44+06:30
categories: [frameworks]
tags: [flutter, setup, development, programming, frameworks, android]
---

Linux မှာ Flutter (Android Application Development Framework) ကို snap package manager သုံးပြီး setup လုပ်တဲ့အကြောင်းကို ပြောပြပေးသွားမှာပါ။ 

Ubuntu base Linux Distro တွေမှာတော့ snapd က ပါဝင်ပြီးဖြစ်ပေမယ့် မပါဝင်သေးတဲ့ Distro တွေအတွက်ကတော့ snap ကို https://snapcraft.io/ ကနေ download & install နိုင်ပါတယ်။ 

Flutter framework ကို Linux မှာ setup လုပ်ရာမှာ snap ကို သုံးတာ အဆင်ပြေဆုံးဖြစ်လို့ snap ကို သုံးပြပေးတာပါ။ 

snap ကို သုံးပြီး လိုအပ်တဲ့ install လုပ်ရမှာတွေက 

- Android Studio (For Android SDK)
- An IDE (IntelliJ IDEA or VSCode)
- Flutter SDK (with Dart)

Commands:
```bash
# Install Android Studio
sudo snap install android-studio --classic

# Install an IDE
sudo snap install intellij-idea-community --classic #IDEA Community
sudo snap install code --classic #VSCode

Install Flutter SDK
sudo snap install flutter --classic 
```
Android Studio install ပြီးရင် Android SDK download လုပ်ဖို့လိုပါသေးတယ်၊ Android Studio >> Standard Setup ပြီးရင် Android SDK ကို Download & Install ဖို့နေရာရောက်ပါမယ်၊ Latest Android SDK version ကို install ပါ။ Android Studio Setup ပြီးတဲ့အခါ Android Studio (IDE) ကို restart လုပ်ပါ။ (ပိတ်လိုက်လည်းရပါတယ်)

Android SDK setup ပြီးရင်တော့ Android Studio ကို ထားခဲ့လိုက်လို့ရပါပြီ၊ Android Studio IDE ကို Flutter Development အတွက်သုံးချင်ရင်တော့ Flutter plugin နဲ့ Dart plugin ကို install ပါ။ ကျွန်တော်တော့ Android Studio ကို မသုံးပါ (လေးလို့) 

သုံးမယ့် IDE အတွက် Flutter & Dart SDK plugin ကို install ပါ IntelliJ IDEA (Community) အတွက် Plugins ကနေ flutter လို့ ရှာပြီး install နိုင်ပါတယ်။ VSCode မှာတော့ Ctrl+Shift+X ကိုနှိပ်ပြီး flutter လို့ရှာပြီး install နိုင်ပါတယ်၊ flutter plugin install တာနဲ့ Dart plugin ပါ install မလားလို့မေးပါမယ်၊ install ပေးလိုက်ပါ။ 

ပြီးရင်တော့ terminal ကနေ ``` flutter doctor ``` command ကို ရိုက်လိုက်ပါ၊ လိုအပ်ချက်တွေပြပေးပါလိမ့်မယ်၊ instruction အတိုင်းလိုက်လုပ်ပေးလိုက်ရုံပါပဲ။ 

Android SDK License Aggrement ကို accept ပေးဖို့ command ကတော့ 
```bash 
flutter doctor --android-licenses
```
Android SDK License Aggrement ကို accept လုပ်ရာမှာ Java Error "Exception in thread "main" java.lang.NoClassDefFoundError" ဆိုတာဖြစ်လာခဲ့ရင် Android Studio ကနေ SDK Manager >> SDK Tools မှာ SDK Command Line Tools ကို check (အမှန်ခြစ်)ပေးပြီး apply ကို နှိပ်ပါ။ လိုအပ်တဲ့ package တွေ download ပြီးရင် OK & Close လိုက်ရင် အဆင်ပြေသွားပါလိမ့်မယ်။

နောက်တကြိမ် ```flutter doctor``` command ကို ပြန် run ကြည့်လိုက်ရင် ခုလိုတွေ့ရပါမယ်

![Success image](/tutorials/flutter/envset/done.jpeg)

Btw, emulator အနေနဲ့ chrome ကို သုံးလို့ရပါတယ်၊ platform specific codeတွေ ရေးဖို့မလိုဘူးဆိုရင် browser ကနေပဲ JIT/AOT ကို အရသာခံရတာ အဆင်ပြေပါတယ်။ 

Flutter နဲ့ ပါတ်သက်တဲ့ tutorial လေးတွေနဲ့ Dart Programming Language Fundamental လေးတွေအကြောင်းတော့ ဒီblogမှာ စိတ်ပါရင် ရေးတင်ပေးပါဦးမယ်

ZOOS.ICU ကနေ free online class လုပ်ပေးဖို့လည်းရှိပါတယ်