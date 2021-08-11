
Configuration of access in github
==================================

Role
-----

src: https://docs.github.com/en/organizations/managing-peoples-access-to-your-organization-with-roles/permission-levels-for-an-organization


a person can be given a general role type:

* collaborator
   give external people read(write) access to only specific repositories
* member of organization
    - gets a member's default permissions which you can configure in the organisation settings
    - members can be grouped in a team, where a team can be given more permissions
* owner of organization
    - has full control over everything in organization (kind of root)
    - this role should be limited, but to no less than two people, in your organization.

Permission level
----------------

a person or team can be given a specific "permission level" to some repo.
eg. give person/team  "Admin" permission level:

- goto repo url https://github.com/ORGANISATION/REPONAME
- click above on page on "settings"
- on left menu click on "Manage access"
- an overview is shown of people and their access rights
- if a specific person or team is not listed,
  then on the right top click on "Invite teams or people" button
  then in popup window

  * type name of person or team
  * select ``Admin`` role
    and click "add .." button on the bottom

- if a specific person or team is already listed then using the select box behind them you can change the permission level


The page https://docs.github.com/en/organizations/managing-access-to-your-organizations-repositories/repository-permission-levels-for-an-organization
lists the possible permissions for an organization repository are:

Read:
  Recommended for non-code contributors who want to view or discuss your project
Triage:
  Recommended for contributors who need to proactively manage issues and pull requests without write access
Write:
  Recommended for contributors who actively push to your project
Maintain:
  Recommended for project managers who need to manage the repository without access to sensitive or destructive actions
Admin:
  Recommended for people who need full access to the project, including sensitive and destructive actions like managing security or deleting a repository


The table at https://docs.github.com/en/organizations/managing-access-to-your-organizations-repositories/repository-permission-levels-for-an-organization#repository-access-for-each-permission-level
explicitly tells what actions a "permission level" can do.

From this table I got the following important notes:

* To push to a normal branch you need "Write" permission
  however to push to protected branches you need "Maintain" or "Admin" permission.

* Protected branches are branches where you are required to do pull requests to get something pushed to.
  To merge a pull request in protected branch you must be allowed to push to the protected branch.
  So to merge a pull request you need "Maintain" or "Admin" permission.

* Only with the "Admin" you can "Merge pull requests on protected branches, even if there are no approving reviews".
  So in general you do not want to give people that permission. So "Maintain" permission is then better to give.

Conclusion
----------

- make only a few people owner:  pierre and me owner (and torxakis account)
- make people who only need access to a single repo an outside collaborator for which we specifically set some
  access permission to only that specific repository. All other repositories are inaccesible.
- members of the organisation have by default "Read" permission to all repositories in
  the organisation. To give them more permissions
  add them to one of the following teams:

  * developers team    =>  "Write" permission ; cannot merge pull request
  * maintainers team => "Maintain" permission; can merge pull request


