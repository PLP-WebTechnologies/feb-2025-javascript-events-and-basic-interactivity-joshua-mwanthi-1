# feb-2025-avasjcript-events-and-basic-interactivity

HTML Structure: Create a basic HTML structure with a form, a button, and a section to display interactive elements.

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Webpage</title>
  CSS Styling: Add minimal CSS for styling.
  
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
        }
        .hidden {
            display: none;
        }
        .error {
            color: red;
        }
    </style>
</head>
<body>
    <h1>Interactive Webpage with JavaScript</h1>
    <form id="userForm">
        <label for="username">Username:</label>
        <input type="text" id="username" name="username" required>
        <span id="error" class="error hidden">Username cannot be empty</span>
        <br><br>
        <button type="submit">Submit</button>
    </form>
    <br>
    <button id="toggleButton">Toggle Visibility</button>
    <div id="interactiveElement" class="hidden">
        <p>This is an interactive element.</p>
    </div>
    <script src="script.js"></script>
</body>
</html>


 
JavaScript: Implement event listeners, form validation, and interactive elements.

document.addEventListener('DOMContentLoaded', () => {
    const form = document.getElementById('userForm');
    const usernameInput = document.getElementById('username');
    const error = document.getElementById('error');
    const toggleButton = document.getElementById('toggleButton');
    const interactiveElement = document.getElementById('interactiveElement');

    // Form validation
    form.addEventListener('submit', (event) => {
        if (usernameInput.value.trim() === '') {
            event.preventDefault();
            error.classList.remove('hidden');
        } else {
            error.classList.add('hidden');
            alert('Form submitted successfully!');
        }
    });

    // Toggle visibility of the interactive element
    toggleButton.addEventListener('click', () => {
        if (interactiveElement.classList.contains('hidden')) {
            interactiveElement.classList.remove('hidden');
        } else {
            interactiveElement.classList.add('hidden');
        }
    });
});
