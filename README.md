
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Temple Information and Visit Planner</title>

    <style>
        body {
            font-family: Arial, sans-serif;
            background: #fff8e7;
            margin: 0;
            text-align: center;
        }

        header {
            background: #a84300;
            color: white;
            padding: 20px;
        }

        .container {
            padding: 20px;
        }

        .temple {
            background: white;
            padding: 18px;
            margin: 15px auto;
            max-width: 400px;
            border-radius: 12px;
            box-shadow: 0 2px 8px #ccc;
        }

        .temple img {
            width: 100%;
            border-radius: 10px;
        }

        button {
            background: #a84300;
            color: white;
            padding: 12px 18px;
            border: none;
            border-radius: 6px;
            margin: 8px;
        }

        input {
            padding: 10px;
            margin: 10px;
            width: 80%;
            max-width: 250px;
        }

        #message {
            color: green;
            font-weight: bold;
        }
    </style>
</head>

<body>

<header>
    <h1>Temple Information</h1>
    <p>Explore temples and plan your visit</p>
</header>

<div class="container">

    <h2>Famous Temples</h2>

    <div class="temple">
        <img src="https://placehold.co/400x200/f3d5a5/713b14?text=Tirumala+Temple"
             alt="Tirumala Temple">
        <h3>Tirumala Venkateswara Temple</h3>
        <p>Location: Tirupati, Andhra Pradesh</p>
        <p>A famous temple dedicated to Lord Venkateswara.</p>
        <p>Visiting hours: Check the official temple website.</p>
    </div>

    <div class="temple">
        <img src="https://placehold.co/400x200/f3d5a5/713b14?text=Yadadri+Temple"
             alt="Yadadri Temple">
        <h3>Yadadri Temple</h3>
        <p>Location: Yadadri, Telangana</p>
        <p>A famous temple dedicated to Lord Lakshmi Narasimha.</p>
        <p>Visiting hours: Check the official temple website.</p>
    </div>

    <h2>Plan Your Visit</h2>

    <div class="temple">
        <label for="templeName">Choose a temple:</label><br>

        <select id="templeName">
            <option value="Tirumala Venkateswara Temple">
                Tirumala Temple
            </option>
            <option value="Yadadri Temple">
                Yadadri Temple
            </option>
        </select>

        <br><br>

        <label for="visitDate">Select visit date:</label><br>
        <input type="date" id="visitDate">

        <br>

        <button onclick="planVisit()">Plan My Visit</button>

        <p id="message"></p>
    </div>

</div>
<script>
    function planVisit() {
        const temple =
            document.getElementById("templeName").value;

        const date =
            document.getElementById("visitDate").value;

        const message =
            document.getElementById("message");

        if (date === "") {
            message.style.color = "red";
            message.textContent = "Please select a visit date.";
            return;
        }

        const selectedDate = new Date(date + "T00:00:00");

        if (selectedDate < new Date(new Date().toDateString())) {
            message.style.color = "red";
            message.textContent = "Please select today or a future date.";
            return;
        }

        message.style.color = "green";
        message.textContent =
            "Your visit is planned for " + temple +
            " on " + date + ".";
    }
</script>

</body>
</html>
