---
title: "Css Reset"
date: 2021-09-16T16:00:35+06:30
---
FrontEnd Web Developer တိုင်း သိထားပြီးသားဖြစ်မယ့်ကိစ္စလေးပါ၊ brower အမျိုးမျိုးကနေ useragent style တွေဆိုတာ UI/UX ကို အထောက်အပံ့ဖြစ်စေဖို့ ရည်ရွယ်ပြီး စီမံပေးလိုက်ကြတာဆိုပေမယ့် ကျွန်တော့်အယူအဆကတော့ "ကိုယ် မလုပ်ဘဲ ဖြစ်လာတာတွေဟာ လုပ်ထားတဲ့အတိုင်းမဖြစ်တဲ့သဘော ဆောင်တယ်"လို့ ယူဆပါတယ်။

Ready-to-use CSS framework တွေပဲ သုံးနေတာဆိုရင်တော့ ဒီကိစ္စ သတိထားမိစရာမရှိပါဘူး၊ framework တွေတိုင်းလိုလိုက သူတို့ style နဲ့သူတို့ reset လုပ်ထားကြပြီးသားမလို့ပါ။ personally, ကျွန်တော် CSS framework တွေ သုံးရတာမကြိုက်ပါဘူး၊ ကိုယ့်စိတ်ကြိုက် ကိုယ်ရေးချင်တာရေးသုံးလိုက်ရတာ ပိုစိတ်တိုင်းကျသလို ခံစားရတဲ့အတွက် ကိုယ်တိုင်ပဲရေးသုံးဖြစ်ပါတယ်။ 

ကျွန်တော့်လို ကိုယ်တိုင်ရေးသုံးတတ်ကြသူတွေအတွက်တော့ browser တွေရဲ့ useragent style တွေက အနှောင့်အယှက်ဖြစ်တာမျိုး ကြုံရတတ်ပါတယ်၊ မလိုအပ်ဘဲ padding, margin, border စတဲ့ style တွေ ပါနေတော့ ကိုယ်က အပျင်းကြီးပြီး တချို့ element တွေအတွက် ဘာ style မှ apply လုပ်မထားခဲ့ရင် တချို့နေရာတွေမှာ အဆင်မပြေဖြစ်တတ်ပါတယ်၊ ဥပမာ ကိုယ်ကတော့ ရေးပြီး chrome မှာထွက်တဲ့ display နဲ့ပဲစမ်းကြည့်ပြီး အဆင်ပြေနေပေမယ့် client က firefox နဲ့ကြည့်မှ တလွဲတွေဖြစ်နေတာမျိုး

ဥပမာ

### CSS
```css
.navrow-nav {
    display: grid;
    grid-template-columns: repeat(6, 1fr);
    grid-template-rows: 1fr;
    grid-column-gap: 0px;
    grid-row-gap: 0px;
    vertical-align: middle;
}

.navcell {
    display: flex;
    padding: 12px;
    font-size: 24px;
    align-items: center;
    justify-content: center;
    border: 1px solid black;
}
```
### HTML
```html
<div class="navrow-nav">
    <div class="navcell">a</div>
    <div class="navcell">b</div>
    <div class="navcell">c</div>
    <div class="navcell">d</div>
    <div class="navcell">e</div>
    <div class="navcell">f</div>
</div>
```
ဒီ code တွေကို run ကြည့်တဲ့အခါ ..

### Reset လုပ်မထားဘဲ Chrome မှာ မြင်ရပုံ
![Example image](/tutorials/css/css-reset-a.png)

### Reset လုပ်ထားပြီး Chrome မှာ မြင်ရပုံ
![Example image](/tutorials/css/css-reset-b.png)

"*" selector နဲ့ margin padding တွေ ဖြုတ်ထုတ်လိုက်တာလောက်ကတော့ ကိစ္စမရှိပေမယ့် တကယ့်လက်တွေ့အသုံးချရတဲ့အခါမျိုးမှာ complexity များရင်များသလို useragent style တွေက လိုက်ပြဿနာပေးတတ်တော့ ဒီကိစ္စ သေချာစဉ်းစားဖို့လိုအပ်လာပါတော့တယ်၊ (Theme Developer တစ်ယောက်အနေနဲ့ ကျွန်တော် WordPress ရဲ့ block library ကို မကြိုက်ရတဲ့အဓိအကြောင်းအရင်းကလည်း အဲကိစ္စပါပဲ)

ဒါ ကိုယ်တစ်ယောက်တည်း ကြုံနေတဲ့ကိစ္စလည်းမဟုတ်တော့ ဒီကိစ္စ solution တွေ အများကြီးရှိပါတယ်။ 

ကိုယ်တိုင် browser တွေရဲ့ useragent style တွေ လိုက်လေ့လာကြည့်ပြီး ကိုယ်လိုချင်တဲ့ပုံစံ reset လုပ်ထားပြီး အသင့်ပြန်သုံးလို့လည်း ရပါတယ်။ ကိုယ်တိုင်မလုပ်ဘဲ သူများလုပ်ထားပြီးသားတွေ ပြုပြင်သုံးချင်တာဆိုရင်လည်း အဆင်သင့်ယူသုံးနိုင်တာတွေ (ကျွန်တော်တွေ့မိသလောက်) စုစည်းပေးထားတာလေးရှိပါတယ်။ ကျွန်တော်စုထားတာတော့မဟုတ်ပါဘူး၊ Chris Coyler ရဲ့ pen လေးကို fork ထားတာပါ

https://codepen.io/wpmyanmar/pen/ZEyvEBo မှာ လေ့လာကြည့်နိုင်ပါတယ်။