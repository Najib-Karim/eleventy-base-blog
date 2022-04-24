---
layout: layouts/base.njk
title: Contact
templateClass: tmpl-post
eleventyNavigation:
  key: Contact
  order: 5
---

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
      fieldset { width: 320px;
           border: 2px ridge black;
           padding: 10px;
           margin-bottom: 10px; }
      input, textarea {margin-top: 10px;
                        display:block;}
    </style>
</head>
<body>

<h1>Contact me</h1>
<form name="contact" method="post" data-netlify="true">
  <fieldset><legend>Your Information</legend>
  <label>First Name: <input type="text" id="name" name="name"></labe><br><br>
  <label>Surname: <input type="text" id="surname" name="surname"></labe><br><br>
  <label>E-mail: <input type="email" id="email" name="email"></labe><br><br>
  </fieldset>
  <label>Message: </label> <br>
   <textarea name="message" rows="3" cols="20"></textarea><br>
  <button class="form_submit" type="submit">Submit</button> <br><br>
  
</form>

{{ content | safe }}

</body>
</html>
<script>
    //get default border colours (to use on input when validation passes)
    var borderStylePass = document.querySelector('#name').style.border;
    //set fail border colours (to use on input when validation fails)
    var borderStyleFail = '1px solid red';
    //get the form submit button
    var submit_button = document.querySelector('.form_submit');
    //attach form event listener
    submit_button.addEventListener("click", function(event){
        //get the form "name" elemement
        var name = document.querySelector('#name');
        //get the form "surname" elemement
        var name = document.querySelector('#surname');
        //get the form "email" element
        var email = document.querySelector('#email');
        //all validation is assumed to be passed until tested
        blnValidated = true;
        //change the border as it the validation passed
        name.style.border = borderStylePass;
        //if validation fails change the bln to false and change the input border colour
        if(!name.value){
            blnValidated = false;
            name.style.border = borderStyleFail;
        }
         surname.style.border = borderStylePass;
        //if validation fails change the bln to false and change the input border colour
        if(!surname.value){
            blnValidated = false;
            surname.style.border = borderStyleFail;
        }
        //if validation fails change the bln to false and change the input border colour
        email.style.border = borderStylePass;
        if(!email.value){
            blnValidated = false;
            email.style.border = borderStyleFail;
        }
        //if validation failed do not allow the form to submit the data
        if(!blnValidated){
            event.preventDefault();
        }
    }, false);
</script>
