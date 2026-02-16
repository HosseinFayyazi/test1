<div dir="rtl" align="right">

# <span dir="ltr">LangChain</span>

**عنوان پروژه:** بررسی چارچوب <span dir="ltr">LangChain</span>  
**نام دانشجو:** فرخنده خوشنود  
**ایمیل:** <span dir="ltr">F.khoshnoud24@gmail.com</span>  
**مقطع:** دانشجوی مجازی هوش مصنوعی، دانشگاه فردوسی مشهد  

---

## مقدمه

مدل‌های زبانی بزرگ (<span dir="ltr">LLMs</span>) مانند <span dir="ltr">GPT</span> امکان تولید متن، پاسخ به سوالات و حتی تولید کد را فراهم کرده‌اند.  
اما استفاده مستقیم از این مدل‌ها برای ساخت یک سیستم واقعی، چالش‌هایی مانند مدیریت حافظه، اتصال به ابزارها و طراحی جریان کاری دارد.  

<span dir="ltr">LangChain</span> چارچوبی است که این فرایند را ساده می‌کند و امکان ساخت برنامه‌های مبتنی بر مدل‌های زبانی را فراهم می‌کند.  

---

## چرا <span dir="ltr">LangChain</span>؟

- ساده‌سازی توسعه برنامه‌های مبتنی بر <span dir="ltr">LLM</span>  
- امکان اتصال به ابزارها و دیتابیس‌ها  
- پشتیبانی از مدل‌های مختلف (<span dir="ltr">OpenAI</span>، <span dir="ltr">DeepSeek</span>، <span dir="ltr">Anthropic</span> و ...)  
- معماری ماژولار و قابل گسترش  

---

## معماری کلی

<span dir="ltr">LangChain</span> از مؤلفه‌های مختلفی تشکیل شده است:

| مؤلفه | توضیح |
|--------|--------|
| <span dir="ltr">Chat Models</span> | اجرای مدل‌های گفتگو |
| <span dir="ltr">Tools</span> | اجرای ابزارهای خارجی |
| <span dir="ltr">Memory</span> | حفظ تاریخچه مکالمه |
| <span dir="ltr">Retrievers</span> | بازیابی اطلاعات |
| <span dir="ltr">Vector Stores</span> | ذخیره بردارهای امبدینگ |
| <span dir="ltr">Embeddings</span> | تبدیل متن به بردار عددی |

این معماری باعث می‌شود بتوان بخش‌های مختلف را به‌صورت ترکیبی استفاده کرد.

---

## مدل‌های گفتگو (<span dir="ltr">Chat Models</span>)

مدل‌های گفتگو به جای دریافت یک متن خام، لیستی از پیام‌ها را دریافت می‌کنند:

- <span dir="ltr">system</span> → تعیین رفتار مدل  
- <span dir="ltr">human</span> → پیام کاربر  
- <span dir="ltr">assistant</span> → پاسخ مدل  

</div>

---

## مثال کد: اتصال به <span dir="ltr">OpenAI</span>

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
```

<div dir="rtl" align="right">

### توضیح بخش‌های کد

| بخش | توضیح |
|------|--------|
| <span dir="ltr">ChatOpenAI</span> | ساخت شیء مدل |
| <span dir="ltr">messages</span> | تعریف پیام‌های مکالمه |
| <span dir="ltr">invoke</span> | ارسال درخواست |
| <span dir="ltr">response.content</span> | دریافت خروجی مدل |

---

## استفاده از <span dir="ltr">DeepSeek</span> در <span dir="ltr">LangChain</span>

### نصب کتابخانه

</div>

```bash
pip install -qU langchain-deepseek
```

<div dir="rtl" align="right">

### تنظیم <span dir="ltr">API Key</span>

</div>

```python
import getpass
import os

if not os.getenv("DEEPSEEK_API_KEY"):
    os.environ["DEEPSEEK_API_KEY"] = getpass.getpass("Enter your API key: ")
```

<div dir="rtl" align="right">

### ساخت مدل

</div>

```python
from langchain_deepseek import ChatDeepSeek

llm = ChatDeepSeek(
    model="deepseek-chat",
    temperature=0
)
```

<div dir="rtl" align="right">

### فراخوانی مدل

</div>

```python
messages = [
    ("system", "Translate English to French"),
    ("human", "I love programming")
]

ai_msg = llm.invoke(messages)
print(ai_msg.content)
```

<div dir="rtl" align="right">

---

## کاربردها

| کاربرد | توضیح |
|---------|----------|
| چت‌بات | پاسخ‌گویی خودکار به کاربران |
| سیستم پرسش و پاسخ | استخراج پاسخ از داده‌ها |
| اتصال به دیتابیس | ترکیب <span dir="ltr">AI</span> با اطلاعات واقعی |
| تولید محتوا | نوشتن متن، مقاله و کد |
| دستیار هوشمند | اجرای وظایف چندمرحله‌ای |

---

## نتیجه‌گیری

<span dir="ltr">LangChain</span> یکی از مهم‌ترین چارچوب‌ها برای توسعه سریع برنامه‌های مبتنی بر مدل‌های زبانی است.  
با استفاده از آن می‌توان مدل‌های مختلف را به‌راحتی ترکیب کرد، ابزارها را متصل نمود و سیستم‌های هوشمند واقعی ایجاد کرد.

</div>
