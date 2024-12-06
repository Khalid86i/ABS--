<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>نظام إدارة الموظفين</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            display: none; /* Hide content initially */
        }
        header {
            background-color: #4CAF50;
            color: white;
            padding: 10px;
            text-align: center;
        }
        .container {
            padding: 20px;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }
        table, th, td {
            border: 1px solid #ddd;
        }
        th, td {
            padding: 8px;
            text-align: left;
        }
        th {
            background-color: #f2f2f2;
        }
        button {
            background-color: #4CAF50;
            color: white;
            border: none;
            padding: 10px 15px;
            cursor: pointer;
        }
        button:hover {
            background-color: #45a049;
        }
        #passwordScreen {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f4f4f4;
        }
        #passwordScreen div {
            text-align: center;
            padding: 20px;
            background: white;
            border: 1px solid #ddd;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        #passwordScreen input {
            padding: 10px;
            margin-top: 10px;
            width: 80%;
        }
    </style>
</head>
<body>
    <div id="passwordScreen">
        <div>
            <h2>أدخل كلمة المرور</h2>
            <input type="password" id="passwordInput" placeholder="كلمة المرور">
            <button onclick="checkPassword()">دخول</button>
        </div>
    </div>

    <header>
        <h1>نظام إدارة الموظفين</h1>
    </header>
    <div class="container">
        <h2>إضافة موظف جديد</h2>
        <form id="employeeForm">
            <label for="name">اسم الموظف:</label>
            <input type="text" id="name" name="name" required><br><br>

            <label for="job">الوظيفة:</label>
            <input type="text" id="job" name="job" required><br><br>

            <label for="hours">عدد الساعات:</label>
            <input type="number" id="hours" name="hours" required><br><br>

            <label for="absences">عدد الغيابات:</label>
            <input type="number" id="absences" name="absences" required><br><br>

            <button type="submit">إضافة الموظف</button>
        </form>

        <h2>قائمة الموظفين</h2>
        <table>
            <thead>
                <tr>
                    <th>اسم الموظف</th>
                    <th>الوظيفة</th>
                    <th>عدد الساعات</th>
                    <th>عدد الغيابات</th>
                </tr>
            </thead>
            <tbody id="employeeTable">
                <!-- Employee rows will appear here -->
            </tbody>
        </table>
    </div>

    <script>
        const employeeForm = document.getElementById('employeeForm');
        const employeeTable = document.getElementById('employeeTable');

        employeeForm.addEventListener('submit', function(event) {
            event.preventDefault();

            const name = document.getElementById('name').value;
            const job = document.getElementById('job').value;
            const hours = document.getElementById('hours').value;
            const absences = document.getElementById('absences').value;

            const row = document.createElement('tr');
            row.innerHTML = `
                <td>${name}</td>
                <td>${job}</td>
                <td>${hours}</td>
                <td>${absences}</td>
            `;

            employeeTable.appendChild(row);

            employeeForm.reset();
        });

        function checkPassword() {
            const passwordInput = document.getElementById('passwordInput');
            const password = passwordInput.value;

            if (password === '7111') {
                document.body.style.display = 'block';
                document.getElementById('passwordScreen').style.display = 'none';
            } else {
                alert('كلمة المرور غير صحيحة!');
            }
        }
    </script>
</body>
</html>
