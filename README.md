## Upload Preview jQuery Plugin
How to Preview an Image Before it is Uploaded Using jQuery

## What is that?
This jQuery plugin provides an easy way to preview your uploads before they're actually uploaded to the server. So if you selected an image or audio file from your hard drive, it will generate a live preview of the selected image or audio player for the audio file.

## How it works?
To get access to the not uploaded data, we can use the HTML5 file reader api. This api provides reading local files. This step is pretty important, because we need to this data in order to show it in the browser window. To get more information about the file reader, you can read the offical documentation.

## Installation
### 1. Copy jQuery & plugin:
  <script type="text/javascript" src="http://code.jquery.com/jquery-2.0.3.min.js"></script>
  <script type="text/javascript" src="assets/js/uploadPreview.min.js"></script>

### 2. Set up your upload form e.g.:
  <div id="image-preview">
    <label for="image-upload" id="image-label">Choose File</label>
    <input type="file" name="image" id="image-upload" />
  </div>

### 3. Load the plugin function as often as you need and fill it with the parameters:
  <script type="text/javascript">
  $(document).ready(function() {
    $("input[type=file]").uploadPreview({
      input_field: "#image-upload",   // Default: .image-upload
      preview_box: "#image-preview",  // Default: .image-preview
      label_field: "#image-label",    // Default: .image-label
      label_default: "Choose File",   // Default: Choose File
      label_selected: "Change File",  // Default: Change File
      no_label: false                 // Default: false
    });
  });
  </script>

## Customization
You're free to customize the CSS and HTML for the input, preview & label fields. Feel free to change it as you wish. There's no need that you put it all together as you can see in step 2. The preview box might be located somewhere else on your page as the input field is.

# Image File Example
  <style type="text/css">
  #image-preview {
    width: 400px;
    height: 400px;
    position: relative;
    overflow: hidden;
    background-color: #ffffff;
    color: #ecf0f1;
  }
  #image-preview input {
    line-height: 200px;
    font-size: 200px;
    position: absolute;
    opacity: 0;
    z-index: 10;
  }
  #image-preview label {
    position: absolute;
    z-index: 5;
    opacity: 0.8;
    cursor: pointer;
    background-color: #bdc3c7;
    width: 200px;
    height: 50px;
    font-size: 20px;
    line-height: 50px;
    text-transform: uppercase;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    margin: auto;
    text-align: center;
  }
  </style>

  <script type="text/javascript">
  $(document).ready(function() {
    $.uploadPreview({
      input_field: "#image-upload",
      preview_box: "#image-preview",
      label_field: "#image-label"
    });
  });
  </script>

  <div id="image-preview">
    <label for="image-upload" id="image-label">Choose File</label>
    <input type="file" name="image" id="image-upload" />
  </div>


