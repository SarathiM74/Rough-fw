<!DOCTYPE html> 

<html lang=”en”> 

<head> 

<meta charset=”UTF-8”> 

<meta name=”viewport” content=”width=device-width, initial-scale=1.0”> 

<title>Leave Management System</title> 

</head> 

<body> 

<h1>Leave Management System</h1> 

<form id=”leaveForm”> 

<label for=”leaveType”>Leave Type:</label> 

<select id=”leaveType” name=”leaveType”> 

<option value=”casual”>Casual Leave</option> 

<option value=”medical”>Medical Leave</option> 

<!—Add more leave types as needed  

</select>
<label for=”startDate”>Start Date:</label> 

<input type=”date” id=”startDate” name=”startDate” required> 

<label for=”endDate”>End Date:</label> 

<input type=”date” id=”endDate” name=”endDate” required> 

<label for=”reason”>Reason:</label> 

<textarea id=”reason” name=”reason” rows=”4” required></textarea> 

<button type=”button” onclick=”applyLeave()”>Apply Leave</button> 

</form> 

<div id=”leaveBalance”> 

<h2>Leave Balance</h2> 

<p id=”casualLeave”>Casual Leave: 10 days</p> 

<p id=”medicalLeave”>Medical Leave: 15 days</p> 

<!—Display leave balances for other leave types  

</div> 

<script> 

Function applyLeave() { 

// Fetch values from form 

Const leaveType = document.getElementById(‘leaveType’).value; 

Const startDate = document.getElementById(‘startDate’).value; 

Const endDate = document.getElementById(‘endDate’).value; 

Const reason = document.getElementById(‘reason’).value;
// Implement backend logic for leave application and update leave balance // 

For now, let’s just show an alert 

Alert(`Leave application submitted:\nType: ${leaveType}\nStart Date: ${startDate}\nEnd 

Date: ${endDate}\nReason: ${reason}`); 

} 

// Fetch leave balances from the backend and update the HTML 

// For now, let’s assume some default values 

Document.getElementById(‘casualLeave’).innerText = ‘Casual Leave: 10 days’; 

Document.getElementById(‘medicalLeave’).innerText = ‘Medical Leave: 15 days’; 

</script> 

</body> 

</html>
