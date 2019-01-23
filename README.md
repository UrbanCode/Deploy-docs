# Deploy-docs
HCL-branded KC

Before running the KC, install Python, MkDocs, and the UrbanCode MkDocs windmill theme.

#Starting the KC
1. Set the UrbanCode Windmill theme to the WINDMILL_DIR environment variable.
2. In the root directory, run:
```
mkdocs serve
```
This will start a local instance of the documentation.

3. To build the distributable site files, run:
```
mkdocs build
```
This will create the `site` folder with the static HTML files.
