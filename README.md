## Upload Preview jQuery Plugin
How to Preview an Image Before it is Uploaded Using jQuery

## What is that?
This jQuery plugin provides an easy way to preview your uploads before they're actually uploaded to the server. So if you selected an image or audio file from your hard drive, it will generate a live preview of the selected image or audio player for the audio file.

## How it works?
To get access to the not uploaded data, we can use the HTML5 file reader api. This api provides reading local files. This step is pretty important, because we need to this data in order to show it in the browser window. To get more information about the file reader, you can read the offical documentation.

## Initialization

### 1. Copy jQuery & plugin:

```html
  <script type="text/javascript" src="http://code.jquery.com/jquery-2.0.3.min.js"></script>
  <script type="text/javascript" src="assets/js/uploadPreview.min.js"></script>
```

### 2. Set up your upload form e.g.:

```html
  <div id="image-preview">
    <label for="image-upload" id="image-label">Choose File</label>
    <input type="file" name="image" id="image-upload" />
  </div>
```

### 3. Load the plugin function as often as you need and fill it with the parameters:
```javascript
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
```

## Customization
You're free to customize the CSS and HTML for the input, preview & label fields. Feel free to change it as you wish. There's no need that you put it all together as you can see in step 2. The preview box might be located somewhere else on your page as the input field is.

### Submitting Files

Submitting the files with optional callbacks

```javascript
  var successCallback = function(data, status, jqXHR) { ... };
  var errorCallback = function(jqXHR, status, error) { ... };
  myFileUploader.submit(successCallback, errorCallback);
```

Listening to file submit complete event

```javascript
  $(document).on('file-preview:submit:complete', function(e) {
    if (e.status == 'success') {
     // The event object has data, status and jqXHR
    } else if (e.status == 'error') {
      // The event object has error, status and jqXHR
    } else if (e.status == 'no-files') {
    }
  });
```

#### Options

| Key                   | Description                                                           | Optional |
| --------------------- | --------------------------------------------------------------------- | -------- |
| preview_table         | The table that will contain the file previews. e.g. "#pictures-table" | Yes      |
| preview_row_template  | A function that will return a template                                | Yes      |
| url                   | URL where the post request is made to                                 | No       |

**NOTE:** It is not necessary to pass the url on initialize. It can be set before submit by calling the `url`
function with the url as the argument.


