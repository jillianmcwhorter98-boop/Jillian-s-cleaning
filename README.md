# Jillian-s-cleaning<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Jillian's Cleaning Service</title>
    <style>
        body { font-family: sans-serif; margin: 0; background: #f0f4f8; color: #333; }
        header { background: #2c3e50; color: white; padding: 25px; text-align: center; border-bottom: 5px solid #3498db; }
        .container { padding: 20px; max-width: 450px; margin: auto; }
        .card { background: white; padding: 20px; border-radius: 15px; box-shadow: 0 5px 15px rgba(0,0,0,0.1); }
        h2 { color: #2c3e50; margin-top: 0; }
        label { font-weight: bold; display: block; margin-top: 15px; color: #555; }
        input, select { 
            width: 100%; padding: 12px; margin-top: 5px; 
            border-radius: 8px; border: 1px solid #ddd; box-sizing: border-box; font-size: 16px;
        }
        button { 
            width: 100%; background: #3498db; color: white; border: none; 
            padding: 15px; margin-top: 25px; border-radius: 8px; 
            font-size: 18px; font-weight: bold; cursor: pointer; 
        }
        button:active { background: #2980b9; transform: scale(0.98); }
    </style>
</head>
<body>

<header>
    <h1>Jillian's Cleaning</h1>
    <p>Professional & Reliable Service</p>
</header>

<div class="container">
    <div class="card">
        <h2>Book a Session</h2>
        
        <label>Service Type</label>
        <select id="service">
            <option value="Standard House Clean">Standard House Clean</option>
            <option value="Deep Cleaning">Deep Cleaning</option>
            <option value="Office/Commercial">Office/Commercial</option>
            <option value="Move In/Out">Move In/Out</option>
        </select>

        <label>Your Name</label>
        <input type="text" id="custName" placeholder="Enter your full name">

        <label>Preferred Date</label>
        <input type="date" id="bookDate">

        <button onclick="sendJillianSMS()">Text Jillian to Book</button>
    </div>
</div>

<script>
    function sendJillianSMS() {
        const myNumber = "2062558039"; 
        const service = document.getElementById('service').value;
        const name = document.getElementById('custName').value;
        const date = document.getElementById('bookDate').value;

        if(!name || !date) {
            alert("Please provide your name and a date so Jillian can help you!");
            return;
        }

        // The text message Jillian will receive
        const message = `Hi Jillian! I'd like to book a ${service} for ${date}. My name is ${name}.`;

        // The universal SMS link for Android
        const smsUrl = `sms:${myNumber}?body=${encodeURIComponent(message)}`;

        window.location.href = smsUrl;
    }
</script>

</body>
</html>
