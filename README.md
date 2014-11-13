# About this repository
This repository facilitates the building of static pages (HTML & CSS only) without requiring full access to the Pitchero codebase.

Developers can build reuse the same components, variables and mixins used on the production codebase without the complexity or overhead of our framework.

## Requirements
Pitchero uses [SASS](http://sass-lang.com/) (SCSS flavour) to compile CSS files.

## Getting started
To build a page for our club platform you should create a new HTML file. Duplicate the `template.html` file:

````Bash
cp "clubs/template" "clubs/your-page.html" 
````

Create a separate SASS file which will contain all the styles for your page. Duplicate the `template.scss` file:

````Bash
cp "assets/clubs/template.scss" "assets/clubs/your-page.scss" 
````

Compile your SASS file to the correct directory:

````Bash
sass --watch assets/sass:assets/css
````

Add a link to the compiled CSS file in your HTML
````HTML
<!-- Add your own css file here -->
<link rel="stylesheet" type="text/css" href="/assets/css/clubs/your-page.css" />
````

Edit `your-page.html` and `your-page.scss` to complete the desired design

## Style guidelines
* See the relevant style guide for reusable components (for example `clubs/style-guide.html`)
* Use existing variables for all colours and spacing. See `assets/sass/_core/_variables.scss` for a full list of available variables.
* All CSS class names should be lowercase and hyphenated
* All CSS styles should be namespaced by a page-specific class. For example:
    
    ````SASS
    .your-page-here {
        .feature {
            margin-bottom: $space_size;
        }
    }
    ````
* Do not edit any existing SASS or HTML files
