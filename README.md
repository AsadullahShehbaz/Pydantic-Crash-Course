# 🐍 Pydantic Crash Course – For FastAPI & ML/AI Students

Welcome to the **Pydantic Crash Course** repo! 🎯  
This is a beginner-to-intermediate guide to **Pydantic** — a powerful Python library for **data validation** and **data parsing** that is widely used in **FastAPI** and also extremely useful in **Machine Learning / AI projects**.

---

## 📌 What is Pydantic?

Pydantic is a **data validation** and **settings management** library for Python.  
It uses **Python type hints** to:
- Parse incoming data into Python objects 📥
- Automatically validate data against your declared types ✅
- Give helpful error messages when validation fails ❌

> ⚡ Pydantic ensures your data is *always clean* before your app or model uses it.

---

## 🚀 Why Learn Pydantic?
- **FastAPI**: It's the backbone of request/response validation.
- **ML/AI Projects**: Helps validate incoming data before feeding it into your models.
- **Data Science Pipelines**: Prevents dirty data from breaking transformations.
- **Typed & Clean Code**: Self-documenting, type-safe code.

---

## 📚 Topics Covered in This Crash Course

This repo contains **7 example codes** that cover:

1. **Basic Model Creation** – Your first Pydantic model
2. **Field Types & Validation** – Strings, numbers, emails, URLs, lists, dicts
3. **Custom Validators** – Using `field_validator` and `model_validator`
4. **Optional Fields & Defaults** – `Optional` and default values
5. **Nested Models** – Handling complex JSON structures
6. **Data Conversion** – Automatic type coercion
7. **Advanced Validation** – Conditional checks, domain-specific rules

---

## 🛠️ Installation
Install Pydantic (**v2 recommended**):

```bash
pip install pydantic
```
If you are using FastAPI:
```
pip install fastapi uvicorn
```

Basic Example : 
```python 
from pydantic import BaseModel, EmailStr
from typing import List

class User(BaseModel):
    name: str
    email: EmailStr
    age: int
    skills: List[str]

# Example usage
data = {
    "name": "Alice",
    "email": "alice@example.com",
    "age": 25,
    "skills": ["Python", "ML"]
}

user = User(**data)
print(user)          # ✅ Valid data
print(user.model_dump())  # Convert to dict
```
Output  : 
```
name='Alice' email='alice@example.com' age=25 skills=['Python', 'ML']
{'name': 'Alice', 'email': 'alice@example.com', 'age': 25, 'skills': ['Python', 'ML']}
```

🎯 Who is this for?

- FastAPI Beginners – Learn how request/response models work.
- ML/AI Students – Validate training data, configs, and API inputs.
- Data Scientists – Avoid pipeline crashes due to invalid data.
