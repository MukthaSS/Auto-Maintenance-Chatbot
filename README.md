# 🚗 Auto Maintenance Chatbot (C++)

## 📘 Project Overview
The **Auto Maintenance Chatbot** is a C++ program designed to simulate an intelligent, self-learning chatbot that assists users with automobile maintenance queries.  
It demonstrates key **Object-Oriented Programming (OOP)** concepts such as **inheritance**, **polymorphism**, **templates**, **composition**, and **file handling**.  

If the chatbot doesn’t know an answer, it can **learn new responses** from the user and store them in a file for future use — creating a persistent memory system.

---

## 🧠 Features

✅ **Self-Learning Chatbot:**  
Learns new keyword–response pairs dynamically from user input.

✅ **Persistent Memory:**  
Stores all learned responses in a text file (`MJ-details.txt`) and loads them automatically on startup.

✅ **Object-Oriented Design:**  
Implements **Encapsulation**, **Inheritance**, **Polymorphism**, **Templates**, and **Composition**.

✅ **Emergency Assistance:**  
Includes a separate emergency service class with contact information for roadside assistance.

✅ **Custom Greetings:**  
Each chatbot class (base and derived) provides unique greetings through function overriding.

---

## 🏗️ Class Structure

### 1. **`Response<T1, T2>`**
A **template class** that stores a keyword and its corresponding response.  
Demonstrates the use of **C++ templates** for generic programming.

```cpp
template <typename T1, typename T2>
class Response {
private:
    T1 keyword;
    T2 response;
public:
    // Constructors, Getters, Setters
};
```
## 2. Chatbot (Base Class)

**Handles:**
- Reading and writing responses from/to file.  
- Matching user input to keywords.  
- Learning new responses dynamically.  

**Key Methods:**
- `respond()`
- `learn()`
- `loadResponses()`
- `saveResponseToFile()`
- `toLowerCase()`

---

## 3. AutoMaintenanceChatbot (Derived Class)

**Inherits from:** `Chatbot`  
Provides specific car service-related features and overrides the greeting function.

```cpp
void greet() override {
    cout << "Hello! Welcome to the Auto Maintenance Workshop. I'm " 
         << name << ". How can I assist you today?" << endl;
}
```
### 4. EmergencyService (Composition Class)

Independent class that provides emergency contact details.
Used inside WorkshopChatbot to demonstrate composition.
```cpp
class EmergencyService {
public:
    void provideEmergencyInfo() {
        cout << "In case of roadside emergencies, contact +92 316 5119292." << endl;
    }
};
```
### 5. WorkshopChatbot (Derived Class)

Inherits from: AutoMaintenanceChatbot
Includes an EmergencyService object.
This chatbot can both handle normal conversations and emergency requests.

### 🧩 How It Works

When the program starts, it loads previous keyword–response pairs from MJ-details.txt.

It greets the user and waits for input.

If the input matches a known keyword → prints the response.

If not known → asks the user to teach it the new keyword and response.

Saves the new data to the file so it remembers in the future.

Typing “bye” or “exit” ends the chat.

Typing “emergency” shows roadside assistance info.

### 💻 Example Interaction
```cpp
Hello! Welcome to the Auto Maintenance Workshop. I'm MJ's Bot. How can I assist you today?
You: hi
I don't understand. Can you teach me a response for this?
Enter a keyword or phrase: hi
Enter the response for this keyword or phrase: Hello! How are you today?
I've learned a new response!

You: hi
Hello! How are you today?

You: oil change
We recommend changing oil every 5000 km.

You: emergency
In case of roadside emergencies, please contact +92 316 5119292 for immediate assistance.

You: bye
Goodbye! Have a great day!
```
### 🧰 Technologies Used

##### Language:

**C++** 

##### Concepts:

**Templates**

**Inheritance**

**Polymorphism**

**Encapsulation**

**Composition**

**File Handling**

**String manipulation**
