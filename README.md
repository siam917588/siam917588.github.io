<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cover Letter Generator</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Cover Letter Generator</h1>
    <form id="coverLetterForm">
        <label for="name">Name:</label>
        <input type="text" id="name" required>

        <label for="fathersName">Father's Name:</label>
        <input type="text" id="fathersName" required>

        <label for="mothersName">Mother's Name:</label>
        <input type="text" id="mothersName" required>

        <label for="religion">Religion:</label>
        <input type="text" id="religion" required>

        <label for="birthDate">Birth Date:</label>
        <input type="date" id="birthDate" required>

        <label for="education">Academic Education:</label>
        <textarea id="education" required></textarea>

        <label for="skills">External Skills:</label>
        <textarea id="skills" required></textarea>

        <button type="submit">Generate Cover Letter</button>
    </form>

    <div id="output"></div>

    <script src="script.js"></script>
</body>
</html>

body {
    font-family: Arial, sans-serif;
    margin: 20px;
}

h1 {
    color: #333;
}

form {
    margin-bottom: 20px;
}

label {
    display: block;
    margin: 10px 0 5px;
}

input, textarea {
    width: 100%;
    padding: 8px;
    margin-bottom: 10px;
}

button {
    padding: 10px 15px;
    background-color: #4CAF50;
    color: white;
    border: none;
    cursor: pointer;
}

button:hover {
    background-color: #45a049;
}

document.getElementById('coverLetterForm').addEventListener('submit', function(event) {
    event.preventDefault();

    const name = document.getElementById('name').value;
    const fathersName = document.getElementById('fathersName').value;
    const mothersName = document.getElementById('mothersName').value;
    const religion = document.getElementById('religion').value;
    const birthDate = document.getElementById('birthDate').value;
    const education = document.getElementById('education').value;
    const skills = document.getElementById('skills').value;

    const coverLetter = `
        Dear Hiring Manager,

        My name is ${name}, and I am writing to express my interest in the position. 
        I am the son of ${fathersName} and ${mothersName}, and I practice ${religion}. 
        I was born on ${birthDate}.

        I have completed my academic education in the following fields:
        ${education}

        Additionally, I possess the following skills:
        ${skills}

        Thank you for considering my application. I look forward to the opportunity to discuss my qualifications further.

        Sincerely,
        ${name}
    `;

    document.getElementById('output').innerText = coverLetter;
});

