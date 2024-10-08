<!DOCTYPE html>
<html lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تحدي الألغاز</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f0f0f0;
            padding: 20px;
        }
        #quiz {
            display: none;
            margin-top: 20px;
        }
        .hidden {
            display: none;
        }
    </style>
</head>
<body>

    <h1>تحدي الألغاز</h1>
    <p>اختر عدد اللاعبين:</p>
    <button onclick="startGame(1)">لعبة فردية</button>
    <button onclick="startGame(2)">لعبة جماعية</button>

    <div id="quiz" class="hidden">
        <h2>اللغز: <span id="puzzle"></span></h2>
        <input type="text" id="answer" placeholder="اكتب إجابتك هنا">
        <button onclick="checkAnswer()">تحقق من الإجابة</button>
        <p id="result"></p>
    </div>

    <script>
        const puzzles = [
            { question: "ما هو العدد الذي إذا ضرب في 2 ثم أضيف إليه 10 يصبح 30؟", answer: "10" },
            { question: "أنا شيء يمكنك كسره دون لمسه. ما أنا؟", answer: "الوعد" }
        ];

        let currentPuzzleIndex = 0;
        let playerCount = 0;

        function startGame(players) {
            playerCount = players;
            currentPuzzleIndex = 0;
            document.getElementById('quiz').classList.remove('hidden');
            showPuzzle();
        }

        function showPuzzle() {
            if (currentPuzzleIndex < puzzles.length) {
                document.getElementById('puzzle').innerText = puzzles[currentPuzzleIndex].question;
                document.getElementById('answer').value = '';
                document.getElementById('result').innerText = '';
            } else {
                document.getElementById('quiz').innerHTML = `<h2>انتهت اللعبة! شكراً للعب!</h2>`;
            }
        }

        function checkAnswer() {
            const userAnswer = document.getElementById('answer').value;
            if (userAnswer === puzzles[currentPuzzleIndex].answer) {
                document.getElementById('result').innerText = "إجابة صحيحة!";
            } else {
                document.getElementById('result').innerText = "إجابة خاطئة!";
            }
            currentPuzzleIndex++;
            setTimeout(showPuzzle, 2000); // عرض اللغز التالي بعد 2 ثانية
        }
    </script>

</body>
</html>
# -
ختيار الموردين 
