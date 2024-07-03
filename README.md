<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TNSTC Web App</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            background-color: #f8f8f8;
        }
        header {
            background-color: #0044cc;
            color: white;
            padding: 1rem;
            width: 100%;
            text-align: center;
        }
        nav {
            width: 100%;
            background-color: #003399;
            overflow: hidden;
        }
        nav a {
            float: left;
            display: block;
            color: white;
            text-align: center;
            padding: 14px 16px;
            text-decoration: none;
        }
        nav a:hover {
            background-color: #ddd;
            color: black;
        }
        main {
            padding: 2rem;
            width: 100%;
            max-width: 600px;
        }
        section {
            margin-bottom: 2rem;
        }
        label {
            display: block;
            margin-bottom: 0.5rem;
        }
        input, select {
            width: 100%;
            padding: 0.5rem;
            margin-bottom: 1rem;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        button {
            padding: 0.5rem 1rem;
            background-color: #0044cc;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        button:hover {
            background-color: #003399;
        }
        footer {
            background-color: #0044cc;
            color: white;
            padding: 1rem;
            width: 100%;
            text-align: center;
            position: fixed;
            bottom: 0;
        }
    </style>
</head>
<body>
    <header>
        <h1>Welcome to TNSTC</h1>
    </header>
    <nav>
        <a href="#home">Home</a>
        <a href="#schedule">Bus Schedule</a>
        <a href="#contact">Contact</a>
    </nav>
    <main>
        <section id="schedule">
            <h2>Search Bus Schedule</h2>
            <form id="busForm">
                <label for="from">From:</label>
                <input type="text" id="from" name="from" required>
                <label for="to">To:</label>
                <input type="text" id="to" name="to" required>
                <label for="date">Date:</label>
                <input type="date" id="date" name="date" required>
                <label for="busType">Bus Type:</label>
                <select id="busType" name="busType" required>
                    <option value="ordinary">Ordinary</option>
                    <option value="express">Express</option>
                    <option value="deluxe">Deluxe</option>
                </select>
                <button type="submit">Search</button>
            </form>
        </section>
        <section id="results" style="display: none;">
            <h2>Bus Schedule Results</h2>
            <div id="scheduleResults"></div>
        </section>
        <section id="contact">
            <h2>Contact Us</h2>
            <p>Email: support@tnstc.com</p>
            <p>Phone: +91 12345 67890</p>
        </section>
    </main>
    <footer>
        <p>&copy; 2024 TNSTC. All rights reserved.</p>
    </footer>
    <script>
        document.getElementById('busForm').addEventListener('submit', function(event) {
            event.preventDefault();
            
            const from = document.getElementById('from').value;
            const to = document.getElementById('to').value;
            const date = document.getElementById('date').value;
            const busType = document.getElementById('busType').value;

            // For demonstration, we're using a static example result.
            const exampleResult = `
                <p>Bus from ${from} to ${to} on ${date}:</p>
                <ul>
                    <li>Bus 101 - 6:00 AM - ${busType}</li>
                    <li>Bus 102 - 8:00 AM - ${busType}</li>
                    <li>Bus 103 - 10:00 AM - ${busType}</li>
                </ul>
            `;

            document.getElementById('scheduleResults').innerHTML = exampleResult;
            document.getElementById('results').style.display = 'block';
        });
    </script>
</body>
</html>
