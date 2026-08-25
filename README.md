# Suggested workflow
## Create branch

Create a branch off of the 'master' branch that matches the version of the draft to be published. For example, if the next version of the branch is draft-xxx-yyy-zzz-01, create a branch for v01 using the following command:

	`git checkout -b v01`
	
However, keep this branch "clean", as in do not make changes in the branch directly. Instead, allow PR to update the branch.

Do this for every version of the draft.

## Make it the default branch

In the GitHub UI for the repository, as admin, set the branch you have created as the default branch in the Settings (for the repository) menu. Update this every time a new branch is created for a new version of the branch.
	
## Create a tag

Next, create a git tag for the draft-xxx-yyy-zzz.xml as follows:

	`git tag draft-xxx-yyy-zzz-00`

This will tell 'make' which version of the draft to build

Remember to push the tag along with any other changes to the remote.

	`git push tag -a`

Or type the following command to push all tags. Git will ignore duplicate tags:

	`git push origin --tags`
	
# Building the draft

To build the draft, type make in the root of the repository

	`make`	

# Fixing and tracking issues

Before proposing any change to the draft, open an issue under the GitHub Issues tab describing the problem or suggestion. All technical discussion should happen there. Once the draft has been adopted as a working group item, discussion should also take place on the WG mailing list, with a pointer to the GitHub issue for tracking.

Only after there has been sufficient discussion and rough consensus on the issue should a PR be created. Create the PR from a branch named `issue-xx`, where `xx` is the GitHub issue number, e.g.:

	`git checkout -b issue-42`

Link the PR to the issue using the Development panel on the PR page (or by including `Closes #42` in the PR description) so that the issue is automatically closed when the PR is merged. Make sure the PR is targeted at the correct version branch.

# Publishing the draft

Once the draft is published, that version of the branch should be collapsed into the 'master' branch, and the above steps to 'Create a branch for the version of the draft' should be followed.





