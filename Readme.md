# Project Overview 🌟

To enable a clipboard copy function for a button in your HTML project, you can use the following code. I have created a sample card design with a button to demonstrate how it works. Please review the files to understand how I connected these elements to a button and the working process involved. 
You'll free to use this code to your project and get a help from this.

## Technologies Used 💻

- HTML
- CSS 
- JavaScript

## Features 🚀

- Custom CSS Notification


## 🟢 Clipboard Function Usage
- To enable clipboard copy functionality for buttons in your HTML project without creating separate JavaScript files for each button, you can consolidate all the clipboard handling into a single JavaScript file. Below is the step of how you can achieve this:


**Java Script Code** (You can call this file name what you want. in my example I call it `script.js`)
```javascript
document.getElementById('copyButton').addEventListener('click', function(event) { //"copyButton" is the Button ID that used in HTML file
    event.preventDefault();
    
    var linkToCopy = this.getAttribute('href');
    
    
    var tempInput = document.createElement('input');
    tempInput.value = linkToCopy;
    document.body.appendChild(tempInput);
    
    
    tempInput.select();
    
    document.execCommand('copy');
    
    document.body.removeChild(tempInput);
    
    // Display a custom notification
    var notification = document.getElementById('notification'); //this is the place that HTML code notification div class read
    notification.textContent = 'Link copied to clipboard'; //You can change this what you want to display
    notification.style.display = 'block';
    
    // Hide the notification after a short delay
    setTimeout(function() {
        notification.style.display = 'none';
    }, 5000); //5000ms - 5sec (You can change the time as you wish)
});
```
02. Now go to the HTML file that you want to connect the clipboard function and add call the javascript file inside the body tag in `<script src=""></script>` As the example in `index.html` file you can see in line no 43, I called the `script.js` file as the function file for the clipboard.

03. In my Java Script Code I added custom notification for the success message. For that in your HTML file also you need to add `<div id="notification" class="notification"></div>` this one to your project. Otherwise custom notification will not displaying in front end.
For your understand in this `index.html` file I added that in line number 40. (If you like You can place this after the button class also)

04. For the Custom Notification Styling I create separate style sheet for your understand and you can change this style as your wish.
In this example notification style file name is `notification.css`

05. To Connect the Function to the relevant button(s) you need to fallow below steps.
    - Go to your HTML file and inside of the button variable if you want to copy something or add a link to this you need to create `<a href="#"></a>`. So in that tag for the connect this function add the **button ID** after the link or content. for the demonstration In the `index.html` file you can see this in line number 20. I added this like this way : `<a href="#" id="copyButton"></a>`

    - **Additional Content :** If  you not create your button in button variable, don't worry. all the things are happen same way. Just you need to add button ID after the link or your content inside the `<a href="#"></a>` tag.




# Copyright Statement ©️

This Project was developed by [Tharindu Darshana](https://github.com/tdbpathiraja) at DaviQ Technologies and is protected under the following copyright:

The "Card Structure and its CSS" is a basic open-source template used to demonstrate how the functions work, along with other JavaScript functions and custom notifications developed by the project's author mentioned above.

©️ 2024 DaviQ Technologies | Released
