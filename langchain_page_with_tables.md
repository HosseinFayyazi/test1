---
author_profile: false
layout: single
title: LangChain
---

<div dir="rtl" align="right">

# LangChain

**عنوان پروژه:** بررسی چارچوب LangChain  
**نام دانشجو:** فرخنده خوشنود  
**ایمیل:** F.khoshnoud24@gmail.com  
**مقطع:** دانشجوی مجازی هوش مصنوعی، دانشگاه فردوسی مشهد  

</div>

---

<div dir="rtl" align="right">

## مقدمه

مدل‌های زبانی بزرگ (LLMs) مانند GPT امکان تولید متن، پاسخ به سوالات و حتی
تولید کد را فراهم کرده‌اند.  
اما استفاده مستقیم از این مدل‌ها برای ساخت یک سیستم واقعی، چالش‌هایی مانند
مدیریت حافظه، اتصال به ابزارها و طراحی جریان کاری دارد.

**LangChain** چارچوبی است که این فرایند را ساده می‌کند و امکان ساخت
برنامه‌های مبتنی بر مدل‌های زبانی را فراهم می‌کند.

</div>

---

<div dir="rtl" align="right">

## چرا LangChain؟

- ساده‌سازی توسعه برنامه‌های مبتنی بر LLM  
- امکان اتصال به ابزارها و دیتابیس‌ها  
- پشتیبانی از مدل‌های مختلف (OpenAI، DeepSeek، Anthropic و ...)  
- معماری ماژولار و قابل گسترش  

</div>

---

<div dir="rtl" align="right">

## معماری کلی

LangChain از مؤلفه‌های مختلفی تشکیل شده است:

</div>

<div align="center">

| مؤلفه         | توضیح                          |
|---------------|--------------------------------|
| Chat Models   | اجرای مدل‌های گفتگو            |
| Tools         | اجرای ابزارهای خارجی           |
| Memory        | حفظ تاریخچه مکالمه             |
| Retrievers    | بازیابی اطلاعات                |
| Vector Stores | ذخیره بردارهای امبدینگ         |
| Embeddings    | تبدیل متن به بردار عددی        |

</div>

<div dir="rtl" align="right">

این معماری باعث می‌شود بتوان بخش‌های مختلف را به‌صورت ترکیبی استفاده کرد.

</div>

---

<div dir="rtl" align="right">

## مدل‌های گفتگو (Chat Models)

مدل‌های گفتگو به جای دریافت یک متن خام، لیستی از پیام‌ها را دریافت می‌کنند:

- system → تعیین رفتار مدل  
- human → پیام کاربر  
- assistant → پاسخ مدل  

</div>

---

<div dir="rtl" align="right">

## مثال کد: اتصال به OpenAI

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
