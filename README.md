
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

## License

This project is open-source and available under the MIT License.
