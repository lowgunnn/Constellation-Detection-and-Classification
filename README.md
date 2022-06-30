# Constellation-Detection-and-Classification
Template Matching Algorithm that detects Constellations from a given image

A computer vision task, assigned with detecting constellations in an image. 

A template matching approach is taken, where template images of known constellations are provided and a constellation is detected if it matches a template.
The implemented algorithm recognises a constellation by aligning the four largest stars in a constellation with a template's four largest stars.

This allows us to detect constellation regardless of any inconsistencies in scaling and rotation with respect to the original template. This also inadvertently accounts for the differences in rotation brought from different viewpoints for the same constellation anywhere around the world.

The stars are scaled and rotated in an attempt to fit the template's co-ordinates, while this would greatly distort the image for mismatched templates, a correct template would produce a neat fit
Different metric procedures were used to outline the similarity between a template's stars and a test constellation image.

Contour Matching - Compares the extracted contour of star's after the transformation to fit the template. Distorted images no longer have contours resembling a star, this can be used to measure similarity between templates.
Star Positioning - Measures the centre of the stars, and how far from each other the transformation has displaced them. A cutoff point is provided to account for a small margin of error of the transformation.
Star-Brightness-Ranking Correction - When extracting the 4 brightest stars, it was found that the correct stars are chosen but at times in the wrong order. To correct this we use contour matching to first identify the correct permutation of the star's brightness, and then use Star Positioning to determine the best template match.
