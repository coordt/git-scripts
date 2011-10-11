**git-start-branch**
	*Usage:* ``git start-branch branch``
	
	* Creates a new branch
	* Alias for git checkout -b branch
	
	Designed to be a complement to the previously-coded git-finish-branch

**git-finish-branch**
	*Usage:* ``git finish-branch branch [tag]``
	
	* Merges a branch into the master branch (with no-ff)
	* Tags the merge with either the passed tag or the date in the 
	  form ``MMDDYYYY``
	* If you specify the tag, and the tag exists, it will fail
	* If you don't specify the tag, and the tag exists, it appends a number,
	  e.g. ``04012010-1`` or ``04012010-2``
	* Pushes the changes to the origin repository
	* Deletes the branch

	Designed to finish up a local topic/feature branch

**git-pull-branch**
	*Usage:* ``git pull-branch <branchname>``
	
	* Pulls the ``<branchname>`` branch from origin and tracks it
	
	A simple shortcut to get a remote branch from the server.

**git-push-branch**
	*Usage:* ``git push-branch <branchname>``
	
	* Pushes the ``<branchname>`` branch to origin
	* Tracks the branch so ``git pull origin`` will also pull this branch
	
	A simple shortcut to get a local branch on a server without having to 
	execute three different commands

**git-move-commits**
	*Usage:* ``git move-commits <num-commits> <correct-branch>``
	
	* Moves the last ``num-commits`` commits to ``correct-branch``
	* If ``correct-branch`` doesn't exist, the script creates it
	* if ``correct-branch`` does exist, the script merges the commits
	
	If you commit to the wrong branch (especially ``master``), this script 
	will fix that for you.

**git-branch-from**
	*Usage:* ``git branch-from <commit-reference> <new-branch-name>``
	
	If you made several commits to a branch (especially ``master``), and in retrospect, you really should have been doing that on a new branch, this will create a new branch from the ``commit-reference`` and reset current branch to the ``commit-reference``.

**git-export**
	*Usage:* ``git export <commit-reference> [<filename>]``
	
	Exports a tar-gzipped archive of the ``commit-reference``. If ``<filename>`` is omitted, the archive is saved as ``<commit-reference>.tar.gz``.

**git-status-u**
	*Usage:* ``git status-u``
	
	* Git emulation of the Subversion command ``svn status -u``
	
	If you want to know what is going to be updated when you pull in a remote
	repository, this will show you.

**linkscripts**
	*Usage:* ``linkscripts``
	
	Simply creates a symbolic link for any script starting with ``git-`` in
	this directory to ``/usr/local/bin``\ .
	
	This is handy so you can easily update the scripts in a repository, and
	have them located elsewhere, but still make them seen by git.