# SumOfSales

## Summary
This project provides a single-page web application titled "Sales Summary 562" that dynamically calculates and displays the total sales from a CSV file. It utilizes the Fetch API to load `sales.csv`, processes the data to sum sales specifically for entries where the `category` is less than or equal to 12, and presents the final, rounded sum directly on the page.

## Live Demo
[Live Demo](https://shantanu-data.github.io/sumofsales/)

## Setup
This project is a static web application consisting of a single HTML file with embedded CSS and JavaScript. Therefore, no specific setup, installation, or build process is required. You can simply open the `index.html` file directly in your web browser.

## How to Use
To use the application, simply open the `index.html` file in your web browser, or visit the [Live Demo](https://shantanu-data.github.io/sumofsales/) link. The page will automatically fetch the `public/sales.csv` data (relative to the `index.html` file), perform the necessary calculations, and display the total sales for categories `<= 12` in the designated area.

## Code Explanation
The application's functionality is entirely contained within a single `index.html` file, demonstrating a lightweight, client-side web application approach.

*   **HTML (`index.html`):**
    The core structure of the page is defined here. It sets up a responsive viewport, a clear page title ("Sales Summary 562"), and a main content container. The most critical element is a `div` with the ID `total-sales`, which serves as the placeholder where the dynamically calculated sum of sales will be displayed. It also includes a `<span>` with a `loading-text` class to provide feedback while data is being processed.

*   **CSS (Embedded in `<style>` tags):**
    Basic styling is provided directly within the `<style>` tags in the HTML head. This CSS ensures a clean and centered layout, applies a modern sans-serif font, and visually enhances the main container with shadows and rounded corners. The `.sales-display` class formats the total sales figure to be prominent and easily readable, while `.loading-text` and `.error-text` classes provide distinct styling for status messages.

*   **JavaScript (Embedded in `<script>` tags):**
    All dynamic logic resides within the `<script>` tag at the end of the `<body>`.
    *   It waits for the DOM (Document Object Model) content to be fully loaded (`DOMContentLoaded` event) before executing.
    *   It uses the `fetch()` API to asynchronously retrieve the `sales.csv` file from the `public/` directory.
    *   Upon successful retrieval, the CSV text is processed: first split into individual lines, and then each line (representing a record) is split by commas to get individual values.
    *   The script identifies the `category` and `sales` columns by their headers from the first line of the CSV.
    *   It then iterates through each data row (skipping the header), parsing the `category` and `sales` values as floating-point numbers.
    *   A key part of the logic is the conditional summation: `totalSales` is incremented only if the `category` value is less than or equal to 12.
    *   Finally, the calculated `totalSales` is rounded to two decimal places (`toFixed(2)`) and displayed within the `total-sales` HTML element.
    *   Robust error handling is included to catch potential issues such as network errors, empty CSV files, or missing critical `category` or `sales` columns in the CSV, providing informative messages to the user.

## License
This project is licensed under the MIT License.