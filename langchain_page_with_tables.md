---
author_profile: false
layout: single
title: LangChain
---

<div dir="rtl" align="right">

# <span dir="ltr">LangChain</span>

عنوان پروژه: بررسی چارچوب <span dir="ltr">LangChain</span><br>
نام دانشجو: فرخنده خوشنود<br>
ایمیل: <span dir="ltr">F.khoshnoud24@gmail.com</span><br>
مقطع: دانشجوی مجازی هوش مصنوعی، دانشگاه فردوسی مشهد

</div>

------------------------------------------------------------------------

<div dir="rtl" align="right">

## مقدمه

مدل‌های زبانی بزرگ (<span dir="ltr">LLMs</span>) مانند
<span dir="ltr">GPT</span>
امکان تولید متن، پاسخ به سوالات و حتی تولید کد را فراهم کرده‌اند.  
اما استفاده مستقیم از این مدل‌ها برای ساخت یک سیستم واقعی، چالش‌هایی مانند
مدیریت حافظه، اتصال به ابزارها و طراحی جریان کاری دارد.

<strong><span dir="ltr">LangChain</span></strong>
چارچوبی است که این فرایند را ساده می‌کند و امکان ساخت
برنامه‌های مبتنی بر مدل‌های زبانی را فراهم می‌کند.

</div>

------------------------------------------------------------------------

<div dir="rtl" align="right">

## چرا <span dir="ltr">LangChain</span>؟

- ساده‌سازی توسعه برنامه‌های مبتنی بر <span dir="ltr">LLM</span>
- امکان اتصال به ابزارها و دیتابیس‌ها
- پشتیبانی از مدل‌های مختلف
  (<span dir="ltr">OpenAI</span>،
   <span dir="ltr">DeepSeek</span>،
   <span dir="ltr">Anthropic</span> و …)
- معماری ماژولار و قابل گسترش

</div>

------------------------------------------------------------------------

<div dir="rtl" align="right">

## معماری کلی

<span dir="ltr">LangChain</span> از مؤلفه‌های مختلفی تشکیل شده است:

</div>

<div align="center" dir="rtl">

| مؤلفه | توضیح |
|------|-------|
| <span dir="ltr">Chat Models</span> | اجرای مدل‌های گفتگو |
| <span dir="ltr">Tools</span> | اجرای ابزارهای خارجی |
| <span dir="ltr">Memory</span> | حفظ تاریخچه مکالمه |
| <span dir="ltr">Retrievers</span> | بازیابی اطلاعات |
| <span dir="ltr">Vector Stores</span> | ذخیره بردارهای امبدینگ |
| <span dir="ltr">Embeddings</span> | تبدیل متن به بردار عددی |

</div>

<div dir="rtl" align="right">

این معماری باعث می‌شود بتوان بخش‌های مختلف را به‌صورت ترکیبی استفاده کرد.

</div>

------------------------------------------------------------------------

<div dir="rtl" align="right">

## مدل‌های گفتگو (<span dir="ltr">Chat Models</span>)

مدل‌های گفتگو به‌جای دریافت یک متن خام،
لیستی از پیام‌ها را دریافت می‌کنند:

- <span dir="ltr">system</span> → تعیین رفتار مدل
- <span dir="ltr">human</span> → پیام کاربر
- <span dir="ltr">assistant</span> → پاسخ مدل

</div>

------------------------------------------------------------------------

<div dir="rtl" align="right">

## مثال کد: اتصال به <span dir="ltr">OpenAI</span>

</div>
```python
from langchain_openai import ChatOpenAI

model = ChatOpenAI(
model="gpt-4o",
api_key="YOUR_KEY"
)

messages = [
("system", "You are a helpful assistant."),
("human", "Explain LangChain in two sentences")
]

response = model.invoke(messages)
print(response.content)
