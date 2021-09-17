# Design Implementation Guidance

This file will help you understand and guide you through the process of implementing a design into a responsive webpage
for QuantConnect. This process consists of 3 phases, understanding the template, understanding the design, and
implementing HTML.

### Understanding the template

The template consists of an HTML file `page.html` and a folder with resources `resources`. These two will allow you to
open a minimal version of QuantConnect in your browser without needing a server.

In the backend, page.html is implemented using a template and multiple files (one for header, footer, scripts, etc).
Because of this, HTML, JS, and CSS changes should be limited to a small portion of the file shown below:

```
<!--- Your Code Update starts here --->
<div id="page-id" style="min-height:calc(100vh - 550px)">

    <p>Your edits goes inside this div</p>

</div>
<!-- Do not Update below here  -->
```

This code can be found between lines 249 and 256 of the original `page.html` file.

### Understanding the design

The design files are inside the design folder, there you will find an export of all the files needed to implement the
design. Images are exported larger than how they are shown in the design template, you will need to define its size
using css. The reason behind it is to address image quality in high-resolution screens.

Some designs have a different header than the one in the page.html, this does not need to be implemented. The header of
the page is out of the editing zone. The same logic applies to the footer or the lack of it.

### Implementing Html, CSS & JS

While implementing the page please follow this checklist:

- [ ] Use as much as possible bootstrap for the layout of elements in the page.
- [ ] Use as much as possible of the css defined in the `qc.default.css`.
- [ ] CSS classes are lowercase words separated by `-`. Example `my-super-class`.
- [ ] For large css implementations. For example landing pages, please write all the style in a new `.scss` file.
- [ ] View ports: (We aim to have responsive page across all the view sizes but this is a good start)
    - [ ] Works on 4k full screen.
    - [ ] Works on 1900px screen view.
    - [ ] Works on 1200px screen view.
    - [ ] Transition to mobile is smooth.
    - [ ] Works on mobile view.
- [ ] Verified using a browser ruler that new elements align with existent view components.
- [ ] Aligning Tables:
    - [ ] Numbers and money are right aligned, preferable in a monospaced font.
    - [ ] Attributes like: types, status, in general text in columns are left aligned.
- [ ] Font coherence, with other elements of the same importance. Size, Color, family, weight
- [ ] Avoid using `!important` in css if not, please justify why you are using it.
- [ ] All clickable elements have a hover effect (background, font color and pointer), if it is not clear what action
  should do please ask.
- [ ] Modals can be escaped using esc button or clicking outside the modal.
