# Callysto Creators Training Manual

This is the Callysto Creators Training manual containing best practices and guidelines for content creators to help standardize the code and notebooks produced for the Callysto project. It also contains processes and procedures used during notebook development and review.

## Launching the gitbook
The contents here are set up as a gitbook that can easily be run locally using the following steps.

1. Install npm (only need to run once)
```
npm install gitbook-cli -g
```
2. Build the gitbook
In the folder containing the markdown documents
```
gitbook init
```
3. Launch the gitbook
```
gitbook serve
```

By default, the book will be available at [localhost:4000](http://localhost:4000/)

Changes made to the content of the gitbook will be reflected in the book as soon as they are saved, providing convenient preview functionality.
