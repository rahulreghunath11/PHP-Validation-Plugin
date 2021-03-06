# PHP-Bootstrap Validaton Plugin 

A PHP plugin to validate form using the bootstrap validator without writing any javascript.

## Installation

Using composer 
    
    composer require rahulreghunath/php-rvalidation
    
## Usage

Include 
   * __Form class__
   * __jQuery__
   * __bootstrap js,css__
   * __bootstrapValidator.min.js__
   * __bootstrapValidator.min.css__
    
in your page
   
    $obj = new Form;


It uses two functions

* 1. validate() to validate a particular field with given validation rules

 eg:
    ```$obj -> validate(field_name,array("validation rules"));```

     
        validation rules are 
        
                "required" - use if it is a required field
                
                "min"=>"minium length" - to set minium length
                
                "max"=>"maxium length" - to set minium length
                
                "email" - use if it is email field
                
                "mobile" - Indian (10 digit) mobile number ( can be customized )
                
                "pin" - Indian Zip code ( can be customized )
                
                "different"=>"different_field different_field_name"
                
                "identical"=>"identical_field identical_field_name"
                
                "remote"=>"remotelocation"
                
                "regexp"=>"type of field"
                
                    type of fields are : text,name,age address,pin,mobile number etc
                    
                    "rmsg" - used with remote validation to display custom error message if remote 
                    validation is failed 

eg:
    ```$obj -> validate("password",array("required","label"=>"password","regexp"=>"name"));```

* 2. applyvalidations() to apply the generated validation rules to the page 
    Only work if bootstrap validater is included in the page.
    
eg:
    ```<script>
        <?php $obj->applyvalidations("form_id");?>
    </script>```
