
```scss
<a class="logo logo-primary">
    <picture>
        <img src="images/logo.png">
    </picture>
</a>
```
Above the line that specifies the image source for logo.png, add the following code:
```scss
<source type="image/svg+xml" srcset="images/logo.svg">
```

To Add Browser Support with PictureFill

You can get better browser support for the <picture> tag if you implement PictureFill. Go to https://scottjehl.github.io/picturefill to learn more about PictureFill.

If js/picturefill.js does not already exist in your folder, download it using the link above and save it as js/picturefill.js.

Open index.html, and add a reference to picturefill.js in the head tags
```scss
    <script src="picturefill.js" async></script>
```
Above the line that you just added, to create an HTML5 shiv to add <picture>, add the following code:
```scss
    <script>
        // Picture element HTML5 shiv
        document.createElement( "picture" );
    </script>
```
To fix PictureFill for your customers using Internet Explorer 9, you can wrap your <source> elements with a <video> element as shown in the code below:
```scss
    <picture>
        <!--[if IE 9]><video style="display: none;"><![endif]-->
            <source type="image/svg+xml" srcset="images/logo.svg">
        <!--[if IE 9]></video><![endif]-->
        <img src="images/logo.png">
    </picture>
```


