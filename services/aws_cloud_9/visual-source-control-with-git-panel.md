---
id: Visual source control with Git panel
title: Visual source control with Git panel
created: 1683841041000
updated: 1683841041000
---
# Visual source control with Git panel

{% hint style="info" %}
This page was generated from content adapted from the [AWS Developer Guide](https://github.com/awsdocs/aws-cloud9-user-guide.git)
{% endhint %}

## Managing source control with Git panel

- **Note**  
The interface options for initializing or cloning a repo are available only if you don't already have a Git repository added to workspace folder in your environment\. If you already have a working directory for a repository, the Git panel window displays the status of the working directory and the staging area\. The **Git panel** menu is also available to provide access to Git commands that you can run against the repository\.<a name="initialize-repo-proc"></a>
- **Note**  
If you're accessing a repository hosted on an external site \(GitHub, for example\), you also need to enter a user name and password for the site to complete the process\.
- **Important**  
You might not want to commit every file in your working directory to the repository\. For example, you're unlikely to want to add files generated during runtime to your project's repository\. With Git panel, you can mark files to be ignored by adding them to a list in a `.gitignore` file\.  
To update the list in `.gitignore`, right\-click a file that hasn't been added to the staging area and select **Add File to \.gitignore**\. The IDE opens the `.gitignore` file and the name of the selected file is added to the list of ignored files\.  
For information about using pattern matching in `.gitignore` to exclude file types, see the relevant [reference in the git\-scm\.com site](https://git-scm.com/docs/gitignore)\.
- **Note**  
You can also unstage specific changes or all changes\. For a single file, pause on the file and then choose **\-**\. Alternatively, right\-click it and choose **Unstage Changes**\. To unstage all changes, go to the **Git panel** menu and choose **Unstage All Changes**\.
- **Note**  
You can also use the `amend` and `signed-off` options when committing files with Git panel\. The `amend` option modifies the commit message of the most recent commit\. The `sign-off` option can identify who performed the commit in the Git log\.  
You can also reverse a commit by going to the **Git panel** menu and choosing **Undo Last Commit**
- **Note**  
If you're working with a remote repository, [publish the new branch](#publish-branch-proc) to the upstream remote repository to allow others to access your content\.<a name="switch-branches-proc"></a>
- **Note**  
You need to enter a user name and password when pushing and pulling changes to and from most hosted repositories \(such as those on GitHub, for example\)\.


## Reference: Git commands available in Git panel

- **Note**  
You can access detailed documentation on the Git commands listed from the official Git site: [https://git\-scm\.com/doc](https://git-scm.com/doc)\.

