# Vectoriser

Convert raster images to SVG, with gradient and feature recognition
Final project for the Building AI course

## Summary

A way to generate SVG objects from raster images.


## Background

Image analysis is used for facial recognition and other object identifiaton tools. Neural networks and other methids have been extensively used for this and gnerally work on raster data. Images may also be transformed into vector data, with reduced data volume and possibly faster manipulations in slower machines and in browsers.  The objective of this project is to create an easy to use library for vectorisation of images.

Vectorisation is possible in tools such as Inkscape. Inkscape generally uses thresholding to divide an image into multiple shapes with specific colors and transparencies.  It works well but cannot be used for feature recognition and object extraction. This project will attempt to use understanding gained from the elements of AI course to create a tool which will: -

* Take an input raster image
* Use thresholding and convolutional matrices for feature recognition (e.g face, balls, etc)
* Use an existing vector dataset of that feature class progressively transformed to match the raster image.
* That object is then removed from the image and next object searched for
* The final vector image generated is one where entities can be can be much more easily extracted and manipulated

## How it is used

This will be a library that can be included in other programs.
The initial program will be in Perl (as this is the language I am most familiar with) with later ports to C etc.

```
#!/usr/bin/perl

use Vectoriser

my $vec=new Vectoriser({src="imageFileName.jpg",featureSet=["faces","arms","hands"]});
$vec->save("svgImageFile.svg");
$vec->listObjects();
$vec->deleteObject();
$vec->addObject($svgObject);


```

## Targets

The applications for this library could be many. I am interested in learning AI in greater depth. This and other things I am interested in are:-

### Perl AI
Prior to this project starting, I will be creating another [repository](https://github.com/saiftynet/ElementsOfAI-Perl) to recode the exercises done in the elementsOfAI course in Perl. Why use Perl? It is easier for me (I struggled with Python as I did the course, my code was probably rubbish)  and similar tools already exist in Perl.  It will teach me as I continue develping this and other tools, and hopefully be a resource for other AI coders in Perl.

### Xray prostheses recognition
Recogise prosthesis, identify brand.

### Avatar extraction
Generate avatars from captured images
