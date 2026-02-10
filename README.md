This repository is a template for writing a new IETF individual submission. It has all the Makefiles, Dockerfiles, and other tools needed to build the draft. It has support for validating YANG modules that you may want to include in the draft.

# What do you need
To build the draft from this template, you need to have Docker installed and running on the machine where this repository will be cloned.

# Structure of the repository

The repository consists of the following

- Makefile
- Dockerfile
- start.sh
- src
- src/addstyle
- src/replace.sh
- src/download-dependent-modules.py
- src/validate-and-gen-trees.sh
- src/insert-figures.sh
- src/yang folder: consists of any YANG modules and instance examples for the YANG module
- draft
- draft/Makefile
- draft/draft-rfcxml-general-template-annotated.xml

# Suggested workflow
## Create a clone

To use this repository, first clone it using the command

	`git clone https://github.com/mjethanandani/ietf-id-template.git`

## Create a branch for the version of the draft

### Create branch

Create a branch off of the 'master' branch that matches the version of the draft to be published. For example, if the next version of the branch is draft-xxx-yyy-zzz-01, create a branch for v01 using the following command:

	`git checkout -b v01`
	
However, keep this branch "clean", as in do not make changes in the branch directly. Instead, allow PR to update the branch.

Do this for every version of the draft.

### Make it the default branch

In the GitHub UI for the repository, as admin, set the branch you have created as the default branch in the Settings (for the repository) menu. Update this every time a new branch is created for a new version of the branch.
	
### Create a tag

Next, create a git tag for the draft-xxx-yyy-zzz.xml as follows:

	`git tag draft-xxx-yyy-zzz-00`

This will tell 'make' which version of the draft to build

Remember to push the tag along with any other changes to the remote.

	`git push tag -a`

Or type the following command to push all tags. Git will ignore duplicate tags:

	`git push origin --tags`
	
## Building the draft

To build the draft, type make in the root of the repository

	`make`	

## Fixing and tracking issues

Use the Issues menu in GitHub to keep track of issues that need to be addressed for the draft. Create a branch for every issue, e.g., issue-01, and tag that PR using the Development tab to close the issue when the PR gets committed. Make sure the issue is set to be committed to the correct branch.

## Publishing the draft

Once the draft is published, that version of the branch should be collapsed into the 'master' branch, and the above steps to 'Create a branch for the version of the draft' should be followed.





