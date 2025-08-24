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
