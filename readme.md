## Description

WordPress AJAX calls load the entire WordPress environment and are never cached. This plugin allows you to specify which plugins your AJAX call requires to complete and disables loading of all other plugins to save server resources and increase completion speed. 
 

## Install

1. Drop fast-ajax.php directly into /wp-content/mu-plugins/.
2. You are done!. 

## Usage

```
jQuery.ajax({
    type: "POST",
    url: ajaxurl,
    data: {
        action: 'some_special_action',
        special_data: data,
        fast_ajax: true,
        load_plugins: ["plugin-directory/plugin-file.php"] /* notice here we are using a JSON string to declare which plugins we are wanting to load for this operation */
    },
    dataType: 'json',
    timeout: 20000,
    success: function (response) {
        console.log(response);
        /* handle actions here */
    },
    error: function (request, status, err) {
        var response = {};
        console.log(err);
        /* handle error here */
    }
});
```