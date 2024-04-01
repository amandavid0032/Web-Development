// validation code 
```javascript
$(document).ready(function () {
    $('#myForm').submit(function (event) {
        var isValid = validateForm($(this)); // Pass the form element to the validateForm function
        if (!isValid) {
            event.preventDefault();
        }
    });
});

function validateForm(form) {
    // Remove existing error messages and field highlighting
    form.find('.error-message').remove();
    form.find('.is-invalid').removeClass('is-invalid');
    var isValid = true;
    // Check file input
    var fileInput = form.find('input[name="imagename[]"]');
    var fileName = fileInput.val();
    var allowedExtensions = ['jpg', 'jpeg', 'png'];
    var fileExtension = fileName.split('.').pop().toLowerCase();
    if (fileName === '' || $.inArray(fileExtension, allowedExtensions) === -1) {
        fileInput.addClass('is-invalid');
        fileInput.after('<div class="error-message">Please select a valid image file (jpg, jpeg, or png).</div>');
        isValid = false;
    }
    // Check other required fields
    var requiredFields = ['firstname', 'lastname', 'fathername', 'mothername', 'email', 'password', 'confirm_password', 'street', 'zip_code', 'place', 'country', 'code', 'phone_number'];
    console.log(requiredFields)
    $.each(requiredFields, function (index, fieldName) {
        var inputField = form.find('#' + fieldName);
        if (inputField.val().trim() === '') {
            inputField.addClass('is-invalid');
            inputField.after('<div class="error-message">Please enter ' + fieldName.replace('_', ' ') + '.</div>');
            isValid = false;
        }
    });
    // Check email format
    var emailInput = form.find('input[name="email"]');
    var emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    if (!emailRegex.test(emailInput.val().trim())) {
        emailInput.addClass('is-invalid');
        emailInput.after('<div class="error-message">Please enter a valid email address.</div>');
        isValid = false;
    }
    // Check password match
    var passwordInput = form.find('input[name="password"]');
    var confirmPasswordInput = form.find('input[name="confirm_password"]');
    if (passwordInput.val() !== confirmPasswordInput.val()) {
        passwordInput.addClass('is-invalid');
        confirmPasswordInput.addClass('is-invalid');
        confirmPasswordInput.after('<div class="error-message">Passwords do not match.</div>');
        isValid = false;
    }

    // Check phone number format
    var phoneInput = form.find('input[name="phone_number"]');
    var phoneRegex = /^\d{10}$/;
    if (!phoneRegex.test(phoneInput.val())) {
        phoneInput.addClass('is-invalid');
        phoneInput.after('<div class="error-message">Please enter a valid phone number.</div>');
        isValid = false;
    }

    // Check gender selection
    var genderInputs = form.find('input[name="gender"]:checked');
    if (genderInputs.length === 0) {
        form.find('input[name="gender"]').last().addClass('is-invalid');
        form.find('input[name="gender"]').last().after('<div class="error-message">Please select a gender.</div>');
        isValid = false;
    }

    return isValid;
}

```
