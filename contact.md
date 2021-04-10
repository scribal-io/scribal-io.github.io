---
layout: page
title: Contact Us
---

<style> 
input[type=text], select {
  width: 100%;
  padding: 12px 20px;
  box-sizing: border-box;
  border: 2px solid #ccc;
  border-radius: 4px;
  background-color: #f8f8f8;
  font-size: 16px;
  resize: none;
  margin: 8px 0;
}

input[type=email], select {
  width: 100%;
  padding: 12px 20px;
  box-sizing: border-box;
  border: 2px solid #ccc;
  border-radius: 4px;
  background-color: #f8f8f8;
  font-size: 16px;
  resize: none;
  margin: 8px 0;
}

textarea {
  width: 100%;
  height: 150px;
  padding: 12px 20px;
  box-sizing: border-box;
  border: 2px solid #ccc;
  border-radius: 4px;
  background-color: #f8f8f8;
  font-size: 16px;
  resize: none;
}

input[type=submit] {
  width: 100%;
  background-color: #ac4142;
  color: white;
  padding: 14px 20px;
  margin: 8px 0;
  border: none;
  border-radius: 4px;
  font-size: 16px;
  cursor: pointer;
}

input[type=submit]:hover {
  background-color: #a9a9a9;
}

input[type=text]:hover {
  background-color: #f2f2f2;
}
.form-hidden {
      display: none;
}
/* The alert-danger message box */
.alert-danger {
  padding: 20px;
  color: white;
  background-color: #f44336; /* Red */
  font-family: Arial, Helvetica, sans-serif;
  margin-bottom: 15px;
}

/* The alert-success message box */
.alert-success {
  padding: 20px;
  color: white;
  background-color: #32A852; /* Green */
  font-family: Arial, Helvetica, sans-serif;
  margin-bottom: 15px;
}

/* The close button */
.closebtn {
  margin-left: 15px;
  color: white;
  font-weight: bold;
  float: right;
  font-size: 22px;
  line-height: 20px;
  cursor: pointer;
  transition: 0.3s;
}

/* When moving the mouse over the close button */
.closebtn:hover {
  color: black;
}
</style>

<form id="customer-contact-form" action="https://rqdbhcbh39.execute-api.us-east-1.amazonaws.com/prod/static-site-mailer" accept-charset="UTF-8" method="post" name="customer-contact-form">
  <input type="text" name="name" id="contact_message_name" placeholder="enter your name" required><br/>
  <input type="email" name="email" id="contact_message_phone_or_email" placeholder="enter your email" required><br/>
  <textarea name="message" id="contact_message_text" placeholder="tell us what's on your mind" required></textarea><br/>
  <input type="submit" value="Submit">
  <div class="alert-danger form-hidden" type="text" id="contact-form-failed-to-submit" role="alert"> <strong>Failed to submit the form. Please, try again. </strong>
  </div>
 <div class="alert-success form-hidden" type="text" id="contact-form-was-submitted" role="alert">
  <span class="closebtn" onclick="this.parentElement.style.display='none';">&times;</span> 
 <strong>Thank you! We have received your message. </strong>
</div>
</form>
