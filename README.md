# 💸 Pesapal API Integration in Python (Initiate STK Push)

## 🔍 What is Pesapal?
**Pesapal** is a leading payment gateway that enables individuals and businesses across Africa to accept online and mobile payments securely. It supports multiple payment options including:

- **Mobile Money**: M-Pesa, Airtel Money
- **Card Payments**: Visa, Mastercard, American Express
- **Bank Transfers**: Regional bank integrations

Pesapal is widely adopted in countries like Kenya, Uganda, Tanzania, Rwanda, Zambia, Zimbabwe, and Malawi.

---

## ✨ Key Features of Pesapal
- **Online Payment Gateway**: Seamlessly integrates into websites, mobile apps, and custom platforms.
- **STK Push Support**: Directly push payment prompts (e.g., M-Pesa) to a customer’s phone for instant approval.
- **Recurring Payments**: Ideal for subscriptions and automated billing.
- **POS Integration**: Accept payments in physical locations via Pesapal POS.
- **Secure & Compliant**: PCI-DSS compliant for safe handling of sensitive customer data.
- **Developer-Friendly API**: Flexible RESTful API for easy integration.

---

## ✅ Use Cases
- **E-commerce platforms** accepting customer payments online.
- **Service providers** billing for recurring utilities or SaaS offerings.
- **Event management** platforms collecting ticket fees.
- **NGOs & donation platforms** enabling quick, secure giving.

---

## 📌 Project Overview

This repository demonstrates how to consume the Pesapal API using Python to initiate an **STK Push payment** (e.g., via M-Pesa). It is compatible with Python-based applications like **Streamlit**, **Flask**, or **Django**, enabling you to collect payments easily in your apps.

🔗 **Source Code:** [pesapal.py](https://github.com/SHIVOGOJOHN/Pesapal-Api/blob/main/pesapal.py)  
🔗 **API Documentation:** [Pesapal Developer Docs](https://developer.pesapal.com/how-to-integrate/e-commerce/api-30-json/api-reference)

---

## 🛠️ Code Overview

### `PesaPal` Class: Core Functionalities
```python
class PesaPal:
```

### ✅ 1. Authentication
Authenticates with Pesapal to get a Bearer token for secure API calls.
```python
def authentication(self):
```

### ✅ 2. Initiate STK Push Payment
Initiates a mobile payment prompt to the user's phone.
```python
def initiate_payment(self, token, phone, bid_amount, order_id, Fname, Lname):
```

- **Parameters:**
  - `token`: Auth token
  - `phone`: Customer's mobile number
  - `bid_amount`: Amount to be paid
  - `order_id`: Unique order identifier
  - `Fname`, `Lname`: Customer name

- **Example Callback URL**: `https://callbak-1.onrender.com/pesapal/callback`

### ✅ 3. Register IPN (Instant Payment Notification)
Registers a URL to receive payment status notifications from Pesapal.
```python
def register_ipn(self):
```

- **Example IPN URL**: `https://ipn-06ai.onrender.com/pesapal/ipn`

---

## 🔧 Dependencies
- `requests`
- `json`
- `streamlit` (for accessing secrets)

Make sure to store your secrets securely using `st.secrets` or environment variables.

---

## 🚀 How to Use

1. Clone the repo and navigate to the project directory:
   ```bash
   git clone https://github.com/SHIVOGOJOHN/Pesapal-Api.git
   cd Pesapal-Api
   ```

2. Add your credentials to `st.secrets`:
   ```toml
   [general]
   consumer_secret = "your_pesapal_consumer_secret"
   ```

3. Use the `PesaPal` class in your payment workflow:
   ```python
   payment = PesaPal()
   token = payment.authentication()
   response = payment.initiate_payment(token, phone, amount, order_id, first_name, last_name)
   ```

---

## 📞 Support & Reference
For full API details and other integration options, visit the [Pesapal Developer Portal](https://developer.pesapal.com).

