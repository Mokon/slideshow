This is a perl script which creates a slideshow based on the contents of the
directory in which it is executed. The contents must be in the prescribed
format:

  A) There must exist a regular file named section_background.jpg in the
     current working directory. This file will be used as the background image
     for the section header slides.
  B) There must exist a directory named music in the current working
     directory. This directory must contain at least one music file. The music
     files here will be played during the slide show in lexicographic order.
     If the music runtime is longer than the slides then this music will be
     cut off.
  C) There must exist a directory named slides in the current working
     directory. This directory must contain a directory structure with the
     the slides for the slideshow in the prescribed format:

     1) For each file in this directory if the file is a directory then its
        name will be used for the section header slide. The directory name
        must be in the format <two digits>-<string>. Where the two digits are
        numbers used to specify a sorting order and the <string> is used for
        the section header slide text. This string must not contain spaces.
        Any dashes (-) in this string will be converted to spaces in the
        slide text. Each word in this text will be capitalized.
     2) For each regular file in this directory the file must be an image
        file. This image will be converted to a picture slide in the
        slideshow. The name of this file must be in the format
        <four digit year>-<two digit month>-<lexicographic sorting string>.
        The slide generated from this file will contain a text giving the year
        and the month specified in the file name. There must not be any spaces
        in the file name.

     Each section directory the slides directory will be recursively entered
     and iterated with the same rules specified here. The directory tree
     is iterated lexicographically in a depth first order. Section header
     slides after the first depth in the tree will use a reduced font size
     for their text.

After this script has been run a file called output.img will be created. This
file can be opened with the imagination slideshow editor. Please note
imagination tends to segfault if there are any errors in the slideshow
project. Also note that there seems to be a bug in imagination around the
screen size. This can be fixed by entering file, then going to properties,
and setting the project settings to the desired dimensions. After this the
project can be exported as a vod formated video.
