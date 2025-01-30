# Test

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Opt-in Form</title>
    <script>
        function toggleOptin() {
            let fields = document.querySelectorAll('input[type="text"], input[type="tel"]');
            let allFilled = Array.from(fields).every(input => input.value.trim() !== '');
            let optin1 = document.getElementById('optin-container1');
            let optin2 = document.getElementById('optin-container2');

            if (allFilled) {
                optin1.style.display = 'none';
                optin2.style.display = 'block';
            } else {
                optin1.style.display = 'block';
                optin2.style.display = 'none';
            }
        }
    </script>
</head>
<body>
    <form action="submit_form.php" method="post">
        <label for="firstname">First Name:</label>
        <input type="text" id="firstname" name="firstname" required oninput="toggleOptin()"><br><br>
        
        <label for="lastname">Last Name:</label>
        <input type="text" id="lastname" name="lastname" required oninput="toggleOptin()"><br><br>
        
        <label for="country">Country:</label>
        <input type="text" id="country" name="country" required oninput="toggleOptin()"><br><br>
        
        <label for="phone">Phone:</label>
        <input type="tel" id="phone" name="phone" required oninput="toggleOptin()"><br><br>
        
        <label for="company">Company:</label>
        <input type="text" id="company" name="company" required oninput="toggleOptin()"><br><br>
        
        <div id="optin-container1">
            <input type="checkbox" id="optin" name="optin" value="yes" required>
            <label for="optin">I agree to receive communications</label><br><br>
        </div>
        
        <div id="optin-container2" style="display: none;">
            <input type="checkbox" id="optin2" name="optin2" value="yes" required>
            <label for="optin2">I agree to the terms and conditions I agree to the terms and conditions I agree to the terms and conditions</label><br><br>
        </div>
        
        <button type="submit">Submit</button>
    </form>
</body>
</html>
