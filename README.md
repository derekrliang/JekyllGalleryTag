JekyllGalleryTag
================

Jekyll plugin to generate thumbnails from a directory of images and display them with a Liquid tag

Installation
--------------
0. Install [ImageMagick](http://www.imagemagick.org/) and the [RMagick gem.](https://github.com/rmagick/rmagick)
1. Drop `galleries.rb` into your Jekyll site's `_plugins` folder.
2. Add the following to your `_config.yml` and customize to taste.

``` yaml
gallerytag:
    source_dir: images/gallery
    destination_dir: images/thumbs
    thumb_width: 150
    thumb_height: 150
    columns: 4
```

* `source_dir` — The path (relative to your top Jekyll directory) to the folder containing your gallery images.
* `destination_dir` — The path to you thumbnails (relative to your top Jeyll directory). Recommened to different to `source_dir` directory name.
* `thumb_width` — The width, in pixels, you want your thumbnails to have
* `thumb_height` — The height, in pixels, you want your thumbnails to have
* `columns` — How many columns galleries should display when the Liquid tag is used.


Usage
-------

Jekyll will automatically generate (during builds) thumbnails for any images in the folder specified in `_config.yml`. To display them in a post, you would use a Liquid tag set up like this:

```
{% gallery galleryname %}
subfolder/myfirstimage.jpg:: A caption!
subfolder/myseconfimage.png:: Another caption
subfolder/mythirdimage.jpg
subfolder/myfourthimage.png
subfolder/myfifthimage.jpg
{% endgallery %}
```

Jekyll will output some HTML that is (intentionally) similar to what WordPress does for galleries in posts, making it relatively simple to tweak your CSS. It will also add `rel` attributes to the links, which contain the "galleryname" text as shown in the above example. This makes is easy to integrate a lightbox script like [FancyBox.](http://fancyapps.com/fancybox/)

You can see it in action on my personal blog, [here.](http://matt.harzewski.com/2012/03/13/winterspyre-a-minecraft-creation/)