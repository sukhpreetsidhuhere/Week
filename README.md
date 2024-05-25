# Bored API Example

This is a simple web application that uses the Bored API to suggest activities when you're feeling bored. When you click the "Get Activity" button, it fetches a random activity from the API and displays it on the page.

## Features

- Fetches a random activity using the Bored API.
- Displays the activity on the web page.
- Simple and easy-to-understand code.

## How to Use

1. **Download the Code**: Download the `index.html` file containing the HTML and JavaScript code.
2. **Open in Browser**: Open the `index.html` file in your web browser.
3. **Get Activity**: Click the "Get Activity" button to fetch and display a random activity.

## Code Explanation

### HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bored API Example</title>
    <style>
        #activity {
            margin-top: 20px;
            font-size: 20px;
        }
    </style>
</head>
<body>
    <h1>Feeling Bored?</h1>
    <button id="boredButton">Get Activity</button>
    <div id="activity"></div>

    <script>
        document.getElementById('boredButton').addEventListener('click', function() {
            fetch('https://www.boredapi.com/api/activity/')
                .then(response => response.json())
                .then(data => {
                    document.getElementById('activity').innerText = `Activity: ${data.activity}`;
                })
                .catch(error => {
                    console.error('Error fetching activity:', error);
                    document.getElementById('activity').innerText = 'Failed to fetch activity. Please try again.';
                });
        });
    </script>
</body>
</html>
