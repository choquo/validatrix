#Validatrix 
####A simple lightweight form validation script based on javascript / jquery
Just include the script & css and add the class `.required` to your required fields that's all, just 2kb.

**[View Demo](http://develus.com/github/validatrix)**

![](http://develus.com/github/validatrix/assets/img/capture.png)

##How to use
Add class `.required` to your required fields
    
	<input class="required" name="" />

Include the validatrix script, the script requires jQuery
   
	<script src="//code.jquery.com/jquery-1.11.2.min.js"></script>
	<!-- Validatrix -->
	<link rel="stylesheet" href="validatrix/validatrix.css">
	<script src="validatrix/validatrix.js"></script>
	<script>
	$(function(){
	   $("#submit-form").click(function(){
	     if( validatrix() ){
	       alert("Submit Form");
	       }else{
	       console.log("Some fields are required");
	     }
	   return false; //Prevent form submition
	   });
	});
	</script> 

####HTML Form layout example - IMPORTANT:
You need wrap every form element with a `<div>` tag for a good performance.
The script (for now) only works with this specific form layout:
	
	<form>
		<!-- text -->
		<div>
			<input type="text" class="required">
		</div>
		
		<!-- select -->
		<div>
			<select class="required">
				<option>option 1</option>
				<option>option 2</option>
			</select>
		</div>

		<!-- radios & checkboxes -->
		<div>
			<label>
				<input type="radio" class="required" /> Option 1
			</label>
			<label>
				<input type="radio" class="required" /> Option 2
			</label>
		</div>
		<!-- ... -->
	</form>



###Custom warnings

You can edit the warning values in the file `validatrix.js`

	var warnings = {
	  text : '*This text field is required',
	  textarea: '*This textarea is required',
	  select: '*Select an option',
      radio: '*Select a radio option',
	  checkbox: '*Check one option'
	};