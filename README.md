# Photo Uploader Script

I have a couple of simple portfolios laying around, [**like this one for my photography**](https://github.com/laureanorp/PhotoPortfolio)

Since updating HTML manually is boring, I coded this script to update my portfolios.

First, I install this package with pip. Then, images to be added to the portfolio are placed on an input folder. When the script runs, they are compressed to a configurable max size and exported to an output folder. The necessary HTML img tags are added to the HTML and the changes are pushed to the corresponding repo.

## Setup & usage

1. Clone [my portfolio template](https://github.com/laureanorp/PhotoPortfolio) or your version of it. Open a terminal in the root of the portfolio folder

2. (Optional) Create a python virtual env however you want.

3. install the uploader script package with `pip3 install git+https://github.com/laureanorp/photo_uploader_script.git`

4. Test that it works with `photo-uploader --help`. You may need to add it to your PATH. 

5. Prepare the input and output folder on your portfolio repo. The input folder should have your own photos. You may need to remove my own photos that are already preset on the index.html, inside `<div class="photo-grid">`.

TODO ADD PHOTO

6. Run the script with `photo-uploader --input new_photos --output photos_resized`. Remember, input and ouput folders should match the ones in the repo.

7. A summary will appear on the console. Confirm that you want to push your changes.

8. (Optional) Set up GitHub Pages for your own repo if you want an easy way to deploy your portfolio.


## Technical notes

- I didn't add certain parameters to the script to keep simple. In case you want more granular contorl over how the script works, inside `photo_uploader/main.py` you can find:

```python 
MAX_WIDTH = 1500
MAX_HEIGHT = 2000

HTML_FILE_RELATIVE_PATH = 'index.html' 
```

- JPG, JPEG, and PNG are supported

- New photos are added to the top of HTML social-media-timeline style

- When processed, all photos are renamed with an index before the name: "10_landscape,jpg", so the newer/older order can be preserved
