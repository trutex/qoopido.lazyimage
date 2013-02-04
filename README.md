Qoopido Lazyimage
===========================
jQuery plugin to lazy load images.


installation & usage
---------------------------
Download and extract the ZIP file of the emerge package from [here](https://github.com/dlueth/qoopido.lazyimage/blob/master/packages/qoopido.lazyimage.zip?raw=true) and put the contents somewhere onto your webspace.

Finally add jQuery and qoopido.lazyimage.min.js to your script block and you are all set.

Example HTML:
```html
<img alt="" data-lazyimage="img/example.png" />
```

Corresponding Javascript:
```javascript
<script type="text/javascript">
;(function($, window, document, undefined) {
    'use strict';

    $(document).ready(function() {
        $('img[data-lazyimage],.lazyimage')
            .on('requested.lazyimage', function(event) {
                // do something when the image gets requested
            })
            .on('loaded.lazyimage', function(event) {
				// do something when the image was loaded
			})
        .lazyimage({
        	interval:   20,     // default
        	threshold:  'auto', // default
        	auto:       0.5,    // default (meaning 0.5 * screen width/height threshold)
        	visibility: true    // default
		});
    });
})(jQuery, window, document);
</script>
```