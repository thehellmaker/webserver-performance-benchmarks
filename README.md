# Webserver Performance Benchmarks (Multi Language & Framework)

This repository contains simple web servers written in **Go (Gin)**, **Rust**, **Node.js (Express)**, **TypeScript (Express)**, and **Python (FastAPI)**. Each server performs the same task:

1. Accepts a JSON request with the format 
```json
{
    "graphName": "xyz"
}
```
2. Parses the JSON and prints the `graphName`.
3. Returns the same JSON as the response.

All servers are designed to be lightweight and easy to test. Each server runs on **port 8080**, so you can test them one at a time.

---

## **How to Run**

### **1. Clone the Repository**
```bash
git clone https://github.com/thehellmaker/webserver-performance-benchmarks.git
cd webserver-performance-benchmarks
```

### **2. Run the Servers**
Each server can be started independently. Navigate to the respective directory and follow the README instructions.

---

## **Testing with k6**

### **1. Install k6**
Follow the [k6 installation guide](https://k6.io/docs/getting-started/installation/) for your platform.

### **2. Go to the test folder**
```bash
cd test
```

### **3. Run the k6 Script**
A k6 script (`test.js`) is provided to test the server. Ensure the server is running on **port 8080** before executing the script by going to the respective language folder and running it.

## 1M requests
```bash
 k6 run -u 50 -i 1000000 --duration 1h --tag testname=million_request_test test.js
```

## 10M requests
```bash
 k6 run -u 50 -i 10000000 --duration 1h --tag testname=10_million_request_test test.js
```

The results of these benchmarks have been updated in the respective folders of different languages

---

## **License**

This project is licensed under the **Apache License 2.0**. See the [LICENSE](LICENSE) file for details.

---

## **Contributing**

Contributions are welcome! Please open an issue or submit a pull request for any improvements or fixes.

---

## **Acknowledgments**

- Thanks to the developers of Go, Rust, Node.js, TypeScript, and FastAPI for their amazing frameworks.
- Special thanks to the k6 team for providing a powerful load-testing tool.

---

Enjoy testing and exploring the multi-language web servers performance benchmarks! 🚀