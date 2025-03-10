# FAQ Backend API  

## Table of Content  
- Overview  
- Features  
- Technologies Used  
- Installation  
- API Usage  
- Admin Panel  
- Testing API Endpoints using Postman  
- Running Tests  

## Overview  

The **FAQ Backend API** is a robust, multilingual API built using **Django** that allows users to manage Frequently Asked Questions (FAQs). This API supports features like retrieving FAQ entries in different languages, a Django-powered admin panel to manage FAQs easily, and a flexible backend that can be extended for various use cases. It is built to handle a variety of FAQ-related operations, such as fetching, adding, and translating FAQs into multiple languages.  

## ✅ Features  

- **FAQ Management**: Supports CRUD (Create, Read, Update, Delete) operations on FAQ entries.  
- **Multilingual Support**: FAQs can be retrieved in multiple languages (default is English).  
- **Django Admin Panel**: A user-friendly web interface to manage FAQ data easily.  
- **Database**: Uses **SQLite** by default, with the flexibility to use other databases like PostgreSQL or MySQL.  
- **API Endpoints**: Exposes multiple endpoints to manage FAQ data, including the ability to fetch FAQs in various languages.  

## 📍 Technologies Used  

- **Django**: Web framework used to build the backend.  
- **Django REST Framework**: For building RESTful APIs.  
- **SQLite** (default): For local database management.  
- **Python 3.x**: Programming language used to write the backend.  
- **Pytest**: Testing framework used for writing and running tests.  
- **googletrans**: Library used to integrate Google Translate API for automatic language translation.  

## Installation  

To get the FAQ Backend API up and running on your local machine, follow the steps below:  

### 1. Clone the Repository  

Clone this repository to your local machine:  

```bash
git clone https://github.com/ANJALINITA/BharatFD_Assignment_Anjali.git  
cd BharatFD_Assignment_Anjali  
```  

### 2. Create a Virtual Environment  

Create a virtual environment to keep dependencies isolated:  

```bash
python -m venv venv  
```  

### 3. Activate the Virtual Environment  

- On **Windows**:  

  ```bash
  venv\Scripts\activate  
  ```  

- On **macOS/Linux**:  

  ```bash
  source venv/bin/activate  
  ```  

### 4. Install Dependencies  

Install the necessary dependencies from the `requirements.txt` file:  

```bash
pip install -r requirements.txt  
```  

### 5. Run Migrations  

Set up the database by applying the migrations:  

```bash
python manage.py migrate  
```  

### 6. Start the Development Server  

Run the Django development server:  

```bash
python manage.py runserver  
```  

Once the server is up and running, the API will be available at `http://127.0.0.1:8000/`.  

## API Usage  

The following endpoints are available for interacting with the FAQ data:  

### 1. Get All FAQs  

- **Endpoint**: `/api/faqs/`  
- **Method**: `GET`  
- **Response**:  

  ```json
  {
    "status": "success",
    "total_faqs": 3,
    "faqs": [
      {
        "id": 1,
        "question": "What is Django?",
        "answer": "Django is a Python web framework."
      },
      {
        "id": 2,
        "question": "How do I install Django?",
        "answer": "You can install Django using pip: `pip install django`."
      },
      {
        "id": 3,
        "question": "Is Django good for beginners?",
        "answer": "Yes, Django is beginner-friendly and well-documented."
      }
    ]
  }
  ```  

### 2. Get FAQs in a Specific Language  

- **Endpoint**: `/api/faqs/?lang=<language_code>`  
- **Method**: `GET`  
- **Parameters**:  
  - `lang`: The language code for the translation (e.g., `hi` for Hindi, `es` for Spanish).  

#### Example Request:  

```bash
GET /api/faqs/?lang=hi  
```  

#### Example Response (in Hindi):  

```json
{
  "status": "success",
  "total_faqs": 3,
  "faqs": [
    {
      "id": 1,
      "question": "Django क्या है?",
      "answer": "Django एक Python वेब फ्रेमवर्क है।"
    },
    {
      "id": 2,
      "question": "मैं Django कैसे इंस्टॉल करूं?",
      "answer": "आप Django को pip के माध्यम से इंस्टॉल कर सकते हैं: `pip install django`।"
    },
    {
      "id": 3,
      "question": "क्या Django शुरुआत करने वालों के लिए अच्छा है?",
      "answer": "हां, Django शुरुआत करने वालों के लिए आसान है और इसका दस्तावेज़ अच्छी तरह से उपलब्ध है।"
    }
  ]
}
```  

## Admin Panel  

Django comes with a built-in admin panel for managing FAQ entries. To access the admin panel:  

1. **Create a Superuser**: Run the following command to create a superuser:  

   ```bash
   python manage.py createsuperuser  
   ```  

   Follow the prompts to create a superuser with a username, email, and password.  

2. **Access the Admin Panel**: Start the Django server:  

   ```bash
   python manage.py runserver  
   ```  

   Then, navigate to `http://127.0.0.1:8000/admin/` in your browser.  

3. **Log in**: Use the superuser credentials you just created to log in to the admin panel.  

4. **Manage FAQs**: In the admin panel, you will see a section for **FAQs**. You can add, edit, and delete FAQ entries from here.  

## Running Tests  

To run tests for the API, use the following command:  

```bash
python manage.py test  
```  

This will run all the test cases defined in the `tests.py` file and ensure the API endpoints are functioning correctly.  

## Thank You!  

Thank you for exploring the **FAQ Backend API** project! If you have any questions or encounter any issues, feel free to reach out!  

Happy coding! 😊  
