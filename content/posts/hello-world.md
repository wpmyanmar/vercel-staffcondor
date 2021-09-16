---
title: "Modern Blogging: Hugo, Vercel & Git"
date: 2021-09-16T07:55:04+06:30
---

ဒီ blogလေးက စမ်းလုပ်ထားတာပါ၊ ဒီလို blogမျိုး  အခမဲ့ရနိုင်ပါတယ်၊ tech-blogging လုပ်လိုသူတွေအတွက်တော့ အဆင်ပြေပါတယ်၊ Git CLI နဲ့ MD လောက် နားလည်ရင်အလွယ်တကူလုပ်နိုင်ပါတယ်။ ဘယ်လိုလုပ်ရလဲဆိုတာ ပြောပြပေးလိုက်ပါတယ်

## Todos

1. Create a Git Repo
2. Create Hugo site
3. Push to Git
4. Signup Vercel
5. Deploy Hugo from Git (Your reop)

### Create a Git Repository

Git အကောင့်ရှိဖို့လိုပါတယ်၊ Git CLI သုံးတတ်မှအဆင်ပြေပါလိမ့်မယ်၊ Git ကိုသုံးပြီး vercel မသုံးဘဲ git pages, pages.dev, netifly စသဖြင့် သုံးချင်သုဲံးလို့ရပါတယ်၊ ဒီမှာတော့ vercel ပဲသုံးထားပါတယ်။ vercel သုံးမယ်ဆို repo name ကို အဆင်ပြေရာပေးလို့ရပါတယ်၊ subdomain ကို ပြင်ခွင့်ပေးထားတဲ့အတွက် project name or repo name ဘာဖြစ်ဖြစ် သိပ်ကိစ္စမရှိပါဘူး။

### Create Hugo Site

Hugo ဆိုတာ Static site generator တခုပါ၊ ကိုယ်တိုင် static page တွေ ရေးပြီး သုံးရရင် အချိန်ကုန်အလုပ်ရှုပ်တာ သက်သာဖို့ hugo သုံးတာပါ၊ တခြား static site generator တွေလည်းအများကြီးရှိပါတယ်၊ hugo ကို အရင် install ရပါမယ်

```bash
snap install hugo #or
brew install hugo #or
port install hugo

#for Ubuntu base distros
apt install hugo
```

Hugo ကို install ပြီးရင်တော့ hugo site တခု create ပါမယ်

```bash
hugo new site site-name 
```

hugo new site ဆိုတာ hugo site တခု generate လုပ်တဲ့ command ပါ နောက်က site-name ဆိုတဲ့ dir name ထဲမှာ hugo generate လိုက်တဲ့ project ရှိပါမယ်၊ hugo မှာ default theme အဆင်ပြေပြေပါမလာပါဘူး၊ theme တခုခု install လုပ်ပြီးသုံးရပါတယ်၊ theme တွေကိုတော့ https://themes.gohugo.io မှာ ကြိုက်ရာရွေးနိုင်ပါတယ်

```shell
cd site-name

git clone theme-repo

echo "theme = \"theme-name\" " >> config.toml
# theme specific configurations can be found in theme documentation 

hugo new posts/helloWorld.md
# creating new post

echo " draft: false " >> post/helloWorld.md
# default new post was draft by braft: "true", so, we need to remove that line or set draft: "flase" to publish the post

hugo server -D
# running locally
```

### Push

hugo server -D command က local မှာ deploy ပြီး စမ်းတာပါ၊ ready ဖြစ်ရင်တော့ git repoထဲကို ပို့ပါမယ်၊ ဒီနေရာမှာတော့ Git ကို CLI ကနေ သုံးတတ်ရင် အဆင်ပြေပါတယ်

```shell
git init

git remote add origin your-git-repo

git add .

git branch -M main

git commit -m "your commit message"

git push -u origin main
```

### Signup vercel

Github account ကိုသုံးပြီး https://vercel.com မှာ signup လုပ်နိုင်ပါတယ်။

### Deploy

Vercel မှာ deploy တာကတော့ လွယ်ပါတယ်၊ ကိုယ့် repoကို ရွေး၊ import ပြီး deploy လိုက်ရုံပါပဲ၊ git repo လုပ်မထားနိုင်ရင်လည်း vercel template တွေထဲမှာ hugo ပါပါတယ်၊ template ထဲကနေ hugoကို ရွေးပြီး deploy လိုက်ရင်လည်းရပါတယ်။ 

ကျွန်တော့် siteမှာ သုံးထားတာကတော့ hello-friend ဆိုတဲ့ theme ပါ။