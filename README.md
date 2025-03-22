<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Start Your Interview</title>
    <link rel="icon" type="image/png" href="favicon.png">
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <div class="box">
            <h2>Start Your Interview</h2>
            <div class="dropdown">
                <button id="languageButton">Select language</button>
                <div class="content">
                    <a href="#" data-language="python">Python</a>
                    <a href="#" data-language="java">Java</a>
                    <a href="#" data-language="cpp">C++</a>
                    <a href="#" data-language="javascript">JavaScript</a>
                    <a href="#" data-language="c">C</a>
                    <a href="#" data-language="go">Golang</a>
                    <a href="#" data-language="swift">Swift</a>
                </div>
            </div>
            <button id="main_button">Start your interview</button>
        </div>
    </div>

    <script>
        document.addEventListener("DOMContentLoaded", function () {
            const languageButton = document.getElementById("languageButton");
            const dropdownContent = document.querySelector(".dropdown .content");
            const mainButton = document.getElementById("main_button");

            let selectedLanguage = "python"; // Default language

            // Update selected language when a language is clicked
            dropdownContent.querySelectorAll("a").forEach((link) => {
                link.addEventListener("click", function (e) {
                    e.preventDefault();
                    selectedLanguage = this.getAttribute("data-language");
                    languageButton.textContent = this.textContent; 
                });
            });
            mainButton.addEventListener("click", function () {
                window.location.href = `interview.html?language=${selectedLanguage}`;
            });
        });
    </script>
</body>
</html>
