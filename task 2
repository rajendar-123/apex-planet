<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Responsive Contact Form & To-Do List</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      margin: 0;
      padding: 20px;
    }

    .container {
      max-width: 1000px;
      margin: auto;
      background: white;
      padding: 30px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }

    h2 {
      text-align: center;
      margin-top: 0;
    }

    /* Contact Form */
    form {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 20px;
    }

    form input, form textarea {
      padding: 10px;
      font-size: 16px;
      width: 100%;
      box-sizing: border-box;
    }

    form textarea {
      grid-column: span 2;
      resize: vertical;
    }

    form button {
      grid-column: span 2;
      padding: 12px;
      background-color: #4CAF50;
      color: white;
      border: none;
      font-size: 16px;
      cursor: pointer;
      border-radius: 5px;
    }

    form button:hover {
      background-color: #45a049;
    }

    .error {
      color: red;
      font-size: 14px;
      grid-column: span 2;
    }

    /* To-Do List */
    .todo-section {
      margin-top: 40px;
    }

    .todo-input {
      display: flex;
      gap: 10px;
    }

    .todo-input input {
      flex: 1;
      padding: 10px;
      font-size: 16px;
    }

    .todo-input button {
      padding: 10px 20px;
      background-color: #007BFF;
      color: white;
      border: none;
      border-radius: 5px;
    }

    ul#todoList {
      margin-top: 20px;
      list-style: none;
      padding: 0;
    }

    ul#todoList li {
      padding: 10px;
      background: #e9e9e9;
      margin-bottom: 10px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    ul#todoList button {
      background: red;
      color: white;
      border: none;
      padding: 5px 10px;
      border-radius: 5px;
      cursor: pointer;
    }

    @media (max-width: 600px) {
      form {
        grid-template-columns: 1fr;
      }

      form textarea, form button, .error {
        grid-column: span 1;
      }

      .todo-input {
        flex-direction: column;
      }

      .todo-input button {
        width: 100%;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <h2>Contact Form</h2>
    <form id="contactForm">
      <input type="text" id="name" placeholder="Your Name" required>
      <input type="email" id="email" placeholder="Your Email" required>
      <textarea id="message" rows="5" placeholder="Your Message" required></textarea>
      <div class="error" id="formError"></div>
      <button type="submit">Send Message</button>
    </form>

    <div class="todo-section">
      <h2>Dynamic To-Do List</h2>
      <div class="todo-input">
        <input type="text" id="taskInput" placeholder="Enter a task">
        <button onclick="addTask()">Add Task</button>
      </div>
      <ul id="todoList"></ul>
    </div>
  </div>

  <script>
    // Form Validation
    document.getElementById("contactForm").addEventListener("submit", function(e) {
      e.preventDefault();
      const name = document.getElementById("name").value.trim();
      const email = document.getElementById("email").value.trim();
      const message = document.getElementById("message").value.trim();
      const errorBox = document.getElementById("formError");

      if (!name || !email || !message) {
        errorBox.textContent = "Please fill in all fields.";
        return;
      }

      if (!validateEmail(email)) {
        errorBox.textContent = "Please enter a valid email address.";
        return;
      }

      errorBox.textContent = "";
      alert("Message sent successfully!");
      this.reset();
    });

    function validateEmail(email) {
      const re = /^[^@]+@[^@]+\.[^@]+$/;
      return re.test(email);
    }

    // To-Do List
    function addTask() {
      const taskInput = document.getElementById("taskInput");
      const task = taskInput.value.trim();
      if (task === "") return;

      const li = document.createElement("li");
      li.textContent = task;

      const delBtn = document.createElement("button");
      delBtn.textContent = "Delete";
      delBtn.onclick = () => li.remove();

      li.appendChild(delBtn);
      document.getElementById("todoList").appendChild(li);

      taskInput.value = "";
    }
  </script>
</body>
</html>
