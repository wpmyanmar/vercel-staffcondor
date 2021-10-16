---
title: wgcf Using Cloudflare WARP with Wireguard Client on Ubuntu
---

# wgcf Using Cloudflare WARP with Wireguard Client on Ubuntu

Cloudflare WARP က Ubuntu အတွက် official CLI tool ထုတ်ပေးထားတာရှိပါတယ်၊ ဒါပေမယ့် Wireguard Client နဲ့ သုံးရတာ ပိုအဆင်ပြေသလို ဂစ်တိုးဘာညာလုပ်ချင်ရင်လည်း လွယ်လို့ Wireguard Client နဲ့ အသုံးပြုပုံရေးပေးတာပါ။ 

1. Install Wireguard Client

2. Download & Set Permission for wgcf

3. Register, Generate Wireguard Profile & Use it

## 1. Installing Wireguard Client on Ubuntu

Terminal ကနေ apt package manager သုံးပြီး install အလွယ်တကူနိုင်ပါတယ်။

```shell
sudo apt update && \
sudo apt install wireguard -y
```

## 2. Downloading wgcf & Setting Permission for wgcf

wgcf, Unofficial, cross-platform CLI for Cloudflare Warp ကို release page https://github.com/ViRb3/wgcf/releases ကနေ ကိုယ့်စက်နဲ့ အဆင်ပြေမယ့် package ရွေးပြီး Download လုပ်ပါ၊ အများစု amd64 သုံးကြလို့ Command မှာ wgcf_2.2.9_linux_amd64 package ကို Download လုပ်ပုံပြပေးထားပါတယ်။ 

```shell
cd && \
mkdir -p execpkgs/wgcf && \
cd execpkgs/wgcf && \
wget https://github.com/ViRb3/wgcf/releases/download/v2.2.9/wgcf_2.2.9_linux_amd64 && \
mv wgcf_2.2.9_linux_amd64 wgcf && \
sudo chmod +x wgcf
```

## 3. (A) Registering Cloudflare WARP

Register လုပ်တဲ့အခါမှာ Cloudflare ရဲ့ Terms of Service ကို agree ပေးရပါတယ်၊ default အတိုင်း Yes မှာ ရွေးပေးထားပြီးသားမို့ command ကို execute ပြီး enter ခေါက်လိုက်ရုံပါပဲ

```shell
sudo ./wgcf register
```

## 3. (B) Generating Wireguard Profile 

Register လုပ်ပြီးရင် wgcf-account.toml လေး ရလာမယ်၊ အဲဒါကို Wireguard Client နဲ့ သုံးဖို့ Wireguard profile အဖြစ် generate လုပ်ရပါမယ်

```shell
sudo ./wgcf generate
```

## 3. (C) Usage

Wireguard profile generate လုပ်ပြီးရင် current working dir ထဲမှာ wgcf-profile.conf ဆိုတဲ့ configuration file လေး ရပါမယ်၊ အဲဒါကို /etc/wireguard/ dir ထဲကို ရွှေ့ပြီး wg-quick up command နဲ့ အသုံးပြုနိုင်ပါပြီ

```shell
sudo mv wgcf-profile.conf /etc/wireguard/ && \
ln -s /usr/bin/resolvectl /usr/local/bin/resolvconf && \
sudo wg-quick up wgcf-profile
```

`ln -s /usr/bin/resolvectl /usr/local/bin/resolvconf` command က resolvectl ကို wireguard က resolvconf အဖြစ်သုံးတာဖြစ်တဲ့အတွက် link လုပ်ပေးလိုက်တာပါ၊ အဲလိုလုပ်မပေးရင် resolvconf command not found ဆိုတဲ့ error တက်လာပြီး သုံးမရဖြစ်နိုင်လို့ပါ။

WARP+ ဂစ်တိုးတာဘာညာ လုပ်ချင်ရင် generate မလုပ်ရင် toml file ထဲမှာ account လိုင်စင်ကီးကိုရှာပြီး တိုးလို့ရသလို mobile app ထဲက key ကိုယူပြီး အဲထဲထည့် generate လုပ်လို့ရပါတယ်၊ အဲလိုထည့်ပြီးမှ generate လုပ်သုံးပေါ့။ **မရိုးသားတာကတော့ မလိုအပ်ရင်မလုပ်တာအကောင်းဆုံးပါပဲ။** 
