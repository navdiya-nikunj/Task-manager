# Task-manager

## Introduction

The Task Manager website is a powerful web application designed to help users manage their tasks efficiently. It leverages essential programming concepts such as classes, `switch` statements, and try-catch-finally statements to provide a seamless and error-handling-driven task management experience. In this write-up, we will delve into the details of how these concepts were integrated into the website's codebase.

## Classes

At the core of the Task Manager website is the `TaskManager` class, which encapsulates the logic for adding and removing tasks. The class is instantiated as `taskManager`, allowing us to create and manage task objects with ease. Below is an overview of the class structure:

```javascript
class TaskManager {
    constructor() {
        this.tasks = [];
    }

    addTask(task) {
        this.tasks.push(task);
    }

    removeTask(task) {
        const index = this.tasks.indexOf(task);
        if (index !== -1) {
            this.tasks.splice(index, 1);
        }
    }

    getTasks() {
        return this.tasks;
    }
}
```

The TaskManager class serves as the foundation for task management, enabling us to add, remove, and retrieve tasks efficiently.

## Switch Statements

Switch statements are effectively employed to handle user interactions, specifically when removing tasks. When a user clicks the "Remove" button for a specific task, a switch-like behavior is implemented through a confirmation dialog:

```javascript
// Inside the displayTasks() function
removeButton.addEventListener('click', () => {
    // Handle the remove task action using a switch-like confirmation dialog
    switch (window.confirm('Are you sure you want to remove this task?')) {
        case true:
            taskManager.removeTask(task);
            displayTasks();
            break;
        default:
            break;
    }
});
```

In this code snippet, a switch-like structure is utilized to confirm the user's intent before removing a task, enhancing the user experience.

## Try-Catch-Finally Statements:

Error handling is a vital aspect of the Task Manager website, ensuring robustness and preventing unexpected issues. The website employs try-catch-finally statements to handle potential errors gracefully. For example, when adding a task, the following code block ensures that the task input is validated:

```javascript
try {
    const taskInput = document.getElementById('task-input');
    const task = taskInput.value.trim();

    if (task === '') {
        throw new Error('Task cannot be empty.');
    }

    taskManager.addTask(task);
    taskInput.value = ''; // Clear the input field
    displayTasks();
} catch (error) {
    // Handle errors
    alert(`Error: ${error.message}`);
} finally {
    // This block will always execute
    console.log('Task operation complete.');
}
```

The try-catch-finally structure allows for the graceful handling of errors, providing clear feedback to users and maintaining the website's stability.

## Integration into the Website:

These programming concepts are seamlessly integrated into the website's functionality. The TaskManager class forms the core of task management, while switch-like statements and try-catch-finally blocks ensure smooth user interactions and error handling.

## Code Walkthrough:

The TaskManager class is instantiated at the beginning of the script, serving as the central component for task management.
A switch-like structure is used to confirm task removal, ensuring user intent is verified.
Try-catch-finally statements are strategically placed to validate user inputs and handle potential errors, providing informative error messages and enhancing the user experience.

## Conclusion:

The Task Manager website effectively demonstrates the integration of classes, switch-like statements, and try-catch-finally statements. These programming concepts enhance the website's functionality, making it a powerful tool for managing tasks while ensuring a user-friendly and error-tolerant experience.
