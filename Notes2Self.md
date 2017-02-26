#Notes to self:

Update this:
Need to remove dependence on rmd2md.  RStudio can keep the html (see cv.rmd)
Then the prosedure would be to knit html, move the md to the _md dir, then delete the html
(or .gitignore *.html)


To create a new post
--------------------

- copy a post from _rmd and save as the new post.
- Edit the post to your liking
- Knit to html
- source rmd2md.R
- run `rmd2md()`
- commit
- push


