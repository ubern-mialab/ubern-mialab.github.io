---
layout: default
title: 'MIA Lab: Image basics exercise'
---

<script>
  import Callout from '$lib/Callout.svelte';
</script>

# Image basics

## Overall goal

To get familiar with the libraries that mialab [depends on](https://github.com/ubern-mialab/mialab/blob/main/requirements.txt), so you know what the data types and functions/methods that you'll use for the next several weeks look like.

Libraries here = [numpy](https://numpy.org), [SimpleITK](https://simpleitk.org). Later on, you will also be friends with matplotlib, pillow and scikit-learn. Optionally, if you're very social and like even more friends, you could try nibabel, scikit-image and our homegrown kid, pymia.

## Getting started

This exercise is organized using GitHub Classroom, where every time you commit a change, it automatically runs the test script and evaluates if you did the right thing or not. To attempt the assignment: [https://classroom.github.com/a/zarh_Oy7](https://classroom.github.com/a/zarh_Oy7)

This should create a private repository for you. Then, you can simply open the script `image_basics.py` and edit it, all within the browser or clone it to work on it.

<Callout info>

Note that you'll have to change the location of the repository from `/ubern-mialab/` to `/<your-GitHub-username>/` in the above links, once you have forked correctly.

</Callout>

If you think you've made the right changes to the file, feel free to then *commit* the change, using the green "commit changes..." button if you are using the browser, and don't forget to include a helpful message about what the change really is.

Then, wait for the cogwheels to run: GitHub runs its 'actions' behind the scenes, and you'll either see a red ❌ or a green ✅ next to the commit message you entered previously.

The goal really is to get the green ✅ every time you make a change, which will only happen when all the functions are completed correctly (correctly as defined by the tests in `test_image_basics.py`, please don't cheat ;-)). Clicking on the check mark will show more details about completion of the homework.

Once you're done, please share a link to your fork with us, so we can confirm you've completed the assignment for the bonus grade (if such a need arises).

## Tasks and specifics

The functions to complete, all in [`image_basics.py`](https://github.com/ubern-mialab/01-image-basics/blob/main/image_basics.py):

- [`load_image`](https://github.com/ubern-mialab/01-image-basics/blob/d05df6945dee4841f7016cd2aab28a2eb800ffd7/image_basics.py#L5) - load an image using the SimpleITK Python interface, and return the pixel data based on whether it is a label or not.
- [`to_numpy_array`](https://github.com/ubern-mialab/01-image-basics/blob/d05df6945dee4841f7016cd2aab28a2eb800ffd7/image_basics.py#L18) - transform the SimpleITK image to a numpy ndarray.
- [`to_sitk_image`](https://github.com/ubern-mialab/01-image-basics/blob/d05df6945dee4841f7016cd2aab28a2eb800ffd7/image_basics.py#L28) - transform the numpy ndarray to a SimpleITK image (the reverse of the previous function).
- [`preprocess_rescale_numpy`](https://github.com/ubern-mialab/01-image-basics/blob/d05df6945dee4841f7016cd2aab28a2eb800ffd7/image_basics.py#L42) - rescale the intensities of the `np_img` to the range `[new_min_val, new_max_val]`.
- [`preprocess_rescale_sitk`](https://github.com/ubern-mialab/01-image-basics/blob/d05df6945dee4841f7016cd2aab28a2eb800ffd7/image_basics.py#L56) - rescale the intensities of the `img` to the range `[new_min_val, new_max_val]`, but this time using SimpleITK.
- [`register_images`](https://github.com/ubern-mialab/01-image-basics/blob/d05df6945dee4841f7016cd2aab28a2eb800ffd7/image_basics.py#L67) - execute the `registration_method` on the `img` (hint: `fixed=atlas_img`, `moving=img`); see the helpful comments within the function body.
- [`extract_feature_median`](https://github.com/ubern-mialab/01-image-basics/blob/d05df6945dee4841f7016cd2aab28a2eb800ffd7/image_basics.py#L93) - apply a median filter to the image.
- [`postprocess_largest_component`](https://github.com/ubern-mialab/01-image-basics/blob/d05df6945dee4841f7016cd2aab28a2eb800ffd7/image_basics.py#L103) - get the connected components from the image.

## Help?

- Numpy documentation: [https://numpy.org/doc/stable/user/absolute_beginners.html](https://numpy.org/doc/stable/user/absolute_beginners.html)
- SimpleITK documentation: [https://simpleitk.readthedocs.io/en/master/gettingStarted.html#python-binary-files](https://simpleitk.readthedocs.io/en/master/gettingStarted.html#python-binary-files)

If neither of these two help, reach out to the instructors on Slack. Responses are not guaranteed to be time bound, we will do our best.
