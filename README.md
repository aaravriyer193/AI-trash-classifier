
# AI Waste Sorter

The **AI Waste Sorter** is a browser-based application that classifies waste items into one of four categories: **Plastic, Paper, Metal, Organic**.
It combines two technologies:

1. **TensorFlow\.js MobileNet** – to recognize the object in the uploaded image.
2. **OpenAI API** – to map the recognized object into a waste category.

This project demonstrates how artificial intelligence can be applied in environmental sustainability and waste management education.

---

## Features

* Upload any image of a waste item directly in the browser.
* TensorFlow\.js predicts what the object is (e.g., bottle, banana, can, box).
* OpenAI classifies the object into a waste type: Plastic, Paper, Metal, or Organic.
* Runs entirely in the browser with a clean and responsive user interface.
* Beginner-friendly and requires no installation other than a browser.

---

## Project Structure

```
ai-waste-sorter/
│── index.html      # Main application file (contains HTML, CSS, and JavaScript)
│── README.md       # Documentation and setup instructions
```

---

## Installation and Setup

Follow these steps to run the project locally:

### Step 1: Clone the Repository

Open a terminal and run:

```bash
git clone https://github.com/YOUR-USERNAME/ai-waste-sorter.git
cd ai-waste-sorter
```

This will download the project files into a folder called `ai-waste-sorter`.

---

### Step 2: Obtain an OpenAI API Key

1. Go to the [OpenAI API Key page](https://platform.openai.com/account/api-keys).
2. Click **Create new secret key**.
3. Copy the generated key. It will look similar to this format:

```
sk-proj-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

⚠️ Important: Never share your API key publicly. Treat it like a password.

---

### Step 3: Add Your API Key to the Code

Open the `index.html` file in a text editor.
Find the placeholder line that looks like this:

```javascript
const OPENAI_API_KEY = "YOURKEYHERE";
```

Replace `YOURKEYHERE` with your actual OpenAI API key.

---

### Step 4: Run the Application

You have two options to run the application:

**Option A: Open Directly**

* Double-click `index.html`.
* It will open in your default browser.

**Option B: Use a Local Server (recommended for API requests)**
If you have Python 3 installed, run this command in the project folder:

```bash
python3 -m http.server 8000
```

Now open a browser and go to:

```
http://localhost:8000
```

---

## How It Works

1. The user uploads an image of waste material.
2. The **TensorFlow\.js MobileNet model** runs directly in the browser and predicts what the object is (for example: "water bottle" or "banana").
3. The prediction is then sent to the **OpenAI API**.
4. OpenAI maps the prediction into **one of four categories**:

   * Plastic
   * Paper
   * Metal
   * Organic
5. The category result is displayed on the page in real time.

Example workflow:

* Uploading a picture of a **soda can** → MobileNet predicts "can" → OpenAI classifies it as **Metal**.
* Uploading a picture of a **banana peel** → MobileNet predicts "banana" → OpenAI classifies it as **Organic**.

---

## Example Categories

* Plastic → bottles, food containers, plastic bags
* Paper → books, cartons, newspapers
* Metal → cans, utensils, aluminum foil
* Organic → fruit peels, food leftovers, leaves

---

## Security Notes

* For demonstration purposes, this example places the OpenAI API key directly inside the HTML file.
* In real applications, never expose your key in frontend code. Instead, use a backend server to handle API calls securely.

---

## Requirements

* A modern web browser (Chrome, Edge, Safari, or Firefox).
* An OpenAI API key.
* An active internet connection (for loading TensorFlow\.js and OpenAI).

---

## Contributing

If you’d like to improve the waste categories, enhance the user interface, or extend the functionality, feel free to fork the repository and submit a pull request. Contributions are welcome.

---
## How It Works – Detailed Explanation

The **AI Waste Sorter** is designed to guide the user step by step from uploading an image to seeing a waste classification. The system leverages machine learning and AI technologies to make accurate predictions, all within the browser. The following sections describe each stage in detail:

---

### 1. Uploading an Image

The process begins when the user selects an image of waste using the file input in the web interface. The image could be anything from a plastic bottle to food scraps.

* **Preview:** Once an image is selected, it is displayed in the preview area so the user can confirm the correct file has been chosen.
* **File Validation:** The system ensures that only image files are accepted to avoid errors during classification.

---

### 2. Object Recognition with TensorFlow\.js

After the image is selected, the application uses **TensorFlow\.js** with the pre-trained **MobileNet** model to identify the object in the image.

* **Pre-trained Model:** MobileNet has been trained on millions of images of everyday objects. It can recognize common items such as bottles, cans, boxes, fruits, and more.
* **Prediction Output:** The model returns a list of possible object labels ranked by confidence. The app selects the label with the highest confidence for further processing.

Example: Uploading an image of a soda can might produce predictions like:

```
1. "soda can" – 92% confidence
2. "tin can" – 5% confidence
3. "aluminum container" – 3% confidence
```

The top label, in this case `"soda can"`, is chosen for the next step.

---

### 3. Waste Classification via OpenAI API

The recognized object label is sent to the **OpenAI API**.

* **Purpose:** OpenAI’s model interprets the object label and maps it to one of the four predefined waste categories: Plastic, Paper, Metal, or Organic.
* **Prompt Design:** The API request includes a prompt instructing the AI to provide a short, precise category.
* **Output Handling:** The AI response is captured and displayed in the interface. It ensures that ambiguous or unknown labels are automatically assigned to the correct category based on context.

Example mapping:

* `"soda can"` → **Metal**
* `"banana peel"` → **Organic**
* `"cardboard box"` → **Paper**

This step allows the system to convert general object recognition results into actionable waste classifications.

---

### 4. Displaying the Result

Once the AI returns the category:

* **User Feedback:** The category is displayed below the image in a clearly styled box.
* **Immediate Visibility:** Users can immediately see whether the item is Plastic, Paper, Metal, or Organic.
* **Multiple Predictions:** While the system focuses on the top prediction, additional details can be logged to the console for advanced users or debugging purposes.

---

### 5. Optional Enhancements

Although the current implementation focuses on simplicity:

* **Category Expansion:** Additional categories such as Glass, Electronics, or Hazardous Waste could be added in the future.
* **Confidence Display:** Advanced versions could show confidence levels from MobileNet alongside the AI classification.
* **Backend Integration:** For production use, a server could handle OpenAI requests to avoid exposing API keys in the frontend.

---

### Summary

The AI Waste Sorter simplifies waste classification into a four-step pipeline:

1. User uploads an image.
2. MobileNet identifies the object in the image.
3. OpenAI maps the object to a waste category.
4. The result is displayed to the user instantly.

This process allows anyone, regardless of technical background, to understand and use AI for waste management education and awareness.

---

## License

This project is open-source and available under the MIT License.
