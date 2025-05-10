# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.

Happy Coding! 💻✨

//First, define a simple CSS animation. Let's say we want a button to bounce when clicked:

@keyframes bounce {
    0% { transform: scale(1); }
    50% { transform: scale(1.2); }
    100% { transform: scale(1); }
}

.animated-btn {
    background-color: #3498db;
    color


@keyframes bounce {
    0% { transform: scale(1); }
    50% { transform: scale(1.2); }
    100% { transform: scale(1); }
}

.animated-btn {
    background-color: #3498db;
    color: white;
    padding: 10px 20px;
    border: none;
    cursor: pointer;
    transition: all 0.3s ease;
}

.animated-btn.bounce {
    animation: bounce 0.5s ease-in-out;
}

//Let's store the animation preference in localStorage and retrieve it when needed.

function savePreference(key, value) {
    localStorage.setItem(key, value);
}

function getPreference(key) {
    return localStorage.getItem(key);
}

//Now, let's make the button bounce when clicked and store the user's preference.

document.addEventListener("DOMContentLoaded", function() {
    const button = document.querySelector(".animated-btn");

    // Retrieve user preference
    const animationPreference = getPreference("animationEnabled");

    if (animationPreference === "true") {
        button.classList.add("bounce");
    }

    button.addEventListener("click", function() {
        button.classList.add("bounce");

        // Store user preference
        savePreference("animationEnabled", "true");

        // Remove animation after it's completed
        setTimeout(() => {
            button.classList.remove("bounce");
        }, 500);
    });
});

