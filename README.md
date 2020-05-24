# courseassembler-templates
The source code for the templates used by Course Assembler.

![Course Assembler Designs](screenshot.png)

This repository is the source code to the designs used by Course Assembler. You can download and modify the code if required.

If you use the [Coursesuite API](https://www.coursesuite.com) you can upload a zip package of a template to make it privately available through the design page programatically for your apikey. Any files other than the required files (see below) in the zip package will be persisted as-is when publishing.

## Creating your own themes

Pull requests or additional themes may be accepted and used (with credit).

Themes currently require 4 files which must be named properly. These files are all considered to be HandlebarsJS templates and will have specific token replaced during the publishing process:

* \_package.css - contains all the styles including embedded resources (e.g. dataurls).
* \_package.js - the main script runtime and all its required script libraries.
* index.html - the main HTML content
* preview.jpg - thumbnail for design tab screen (reccomended size 160 x 120px or larger)

### Available tokens

* api: (string) Compatibility setting; one of ["scorm12", "scorm2004", "imscp", "none"]
* enough-count: (integer) count of pages required to complete
* navbg: (hex colour) selected background colour, e.g. "#189082"
* navlock: (boolean) whether navigation is freeform or sequential
* navtext: (rgb string) foreground text colour, one of ["255,255,255", "0,0,0"]
* option-course-copyright: (string) "© Anonymous 2020. All rights reserved."
* option-course-description: (string) "This course was assembled at www.courseassembler.com"
* option-course-name: (string) "New features in CourseAssembler"
* option-ga-id: (string) Google analytics ID
* pages: (array) The pages used in the course, array of:
    * audio: (string) name of audio file for this page, if set, e.g. "d237ff96c68b03b9db61a7c818792dc5.mp3"
    * content: (string) renderer source for content, one of ["plugin", "h5p", "file", "media"]
    * depth: (integer) 0 for outdented, 1 for intented
    * href: (string) url to content relative to root of package "data/file-ka2ajdgo-0.html"
    * index: (integer) order the page appears, zero based
    * score: (integer/float) page score or timestamp required
    * title: (string) "Course Introduction"
* rule: (string) Completion rule setting; one of "[last", "show-enough"]
* template: (string) Name of selected template, e.g. "Dark/Green"
* tier: (integer) Always 99
* timestamp: (string) The timestamp the package was published, in base36, e.g. "kal3zldx"

## Licence

MIT Licenced

Parts of these files include script references to third party libraries which may have their own licences. See the source code for credits and references.