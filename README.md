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

    // Generate PDF
    const { jsPDF } = window.jspdf;
    const pdf = new jsPDF();
    pdf.text(coverLetter, 10, 10);
    pdf.save('cover_letter.pdf');
});
