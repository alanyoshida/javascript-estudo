# Event Bubbling and Capturing

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Bubbling vs Capturing</title>
  <style>
    div {
      border: 1px solid red;
      padding: 5px;
      min-height: 10px;
    }
  </style>
  <script>
    window.onload = function(){
      var divs = document.getElementsByTagName('div');

      function capture() {
          log('capture: ' + this.firstChild.nodeValue.trim())
      }

      function bubble() {
          log('bubble: ' + this.firstChild.nodeValue.trim())
      }

      for (var i = 0; i < divs.length; i++) {
          divs[i].addEventListener('click', capture, true);
          divs[i].addEventListener('click', bubble, false);
      }

      var $log = $('#log');

      function log(msg) {
          $log.append('<p>' + msg + '</p>');
      }
    }
  </script>
</head>
<body>
  <script src="http://code.jquery.com/jquery.min.js"></script>
  <div>1
      <div>2
          <div>3
              <div>4
                  <div>5</div>
              </div>
          </div>
      </div>
  </div>
  <section id="log"></section>

<textarea cols="60" rows="30">
Event capturing
When you use event capturing

               | |
---------------| |-----------------
| element1     | |                |
|   -----------| |-----------     |
|   |element2  \ /          |     |
|   -------------------------     |
|        Event CAPTURING          |
-----------------------------------
the event handler of element1 fires first, the event handler of element2 fires last.

Event bubbling

When you use event bubbling

               / \
---------------| |-----------------
| element1     | |                |
|   -----------| |-----------     |
|   |element2  | |          |     |
|   -------------------------     |
|        Event BUBBLING           |
-----------------------------------
the event handler of element2 fires first, the event handler of element1 fires last.
</textarea>
</body>
</html>
```
