# Sass Cheatsheet

## What is Sass?

Sass is the most commonly used CSS Preprocessor (see notes about CSS Preprocessors --> [Notes Jour-18](../../../../simplon/notes/notes-semaine-4/Jour-18/notes-jour-18.md)), it allows you to go even beyond what vanilla CSS can offer.

## Table of content

* [What is Sass](#what-is-sass)
* [How to Install it](#how-to-install-sass)
* [Compiling .scss into .css](#how-to-compile-scss-into-css)
* [Automate the Process](#automate-the-process)

## How to install Sass

You can go to [their website](https://sass-lang.com/install) to find multiple ways to install Sass on your computer.

## How to compile SCSS into CSS

In order to turn a .scss file into a .css file, you need to run the `sass` command in order to compile your sass file into a single css file.

For example:

`sass input.scss output.css`

This will give you a shiny new css file to use however you like.

## Automate the process

But what if you have to go back and forth a lot, and modify the .scss often?

Well, there is a way to automate the process, so that everytime you save your .scss it will automatically compile it to your .css. You just need to add the `--watch` attribute to the original command to tell sass to keep a constant track of your .scss file.

`sass --watch input.scss output.css`