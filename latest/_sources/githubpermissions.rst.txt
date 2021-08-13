
Configuration of access in github
==================================

Intro
-----

Github  assigns each person a role which generally describes it type of access within a Github organisation.
However Github allows to specify access more granular by assigning permission levels
to persons or teams for specific repositories. So you can either give a person directly more permissions
to a repository, or assign a person to a team which has more rights to a repository.

Role
-----

src: https://docs.github.com/en/organizations/managing-peoples-access-to-your-organization-with-roles/permission-levels-for-an-organization


a person can be given a general role type:

* collaborator
    - give external people read(write) access to only specific repositories
    - for TorXakis collaborators are listed at: https://github.com/orgs/TorXakis/outside-collaborators
* member of organization
    - gets a member's default permissions which you can configure in the organisation settings
    - members can be grouped in a team, where a team can be given more permissions
    - for TorXakis members are listed at: https://github.com/orgs/TorXakis/people
* owner of organization
    - has full control over everything in organization (kind of root)
    - this role should be limited, but to no less than two people, in your organization.
    - for TorXakis look at people's page for person with Owner label: https://github.com/orgs/TorXakis/people

Permission level
----------------

Lookup permissions of a person
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Look up the permissions for a person for all repositories:

- goto the organisation's people page: https://github.com/orgs/TorXakis/people
- find the person of interest in the list
- at the person's row clich the select box and select ``Manage``
- you are redirected to a page which lists for all repositories in the organisation what access
  level the person has
- when you click on the ``Manage`` button behind a repository you get redirected to
  a page which display how this access level is determined.


Change permissions of a person
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

A person can be given more permissions by making the person member of a team with more permissions"

- goto the organisation's teams page: https://github.com/orgs/TorXakis/teams
- click on the team you want the person to be assigned to
- on the specific team's page click on the top on ``Members``
- on the members page use the search box to search for the person you want to add, and then click the ``Add a member`` button.

A person or team can be given a specific "permission level" to some repo.
eg. give person/team  "Admin" permission level:

- goto a repository's url https://github.com/ORGANISATION/REPONAME <br>
  e.g. https://github.com/orgs/TorXakis/TorXakis
- click above on page on ``Settings``
- on left menu click on ``Manage access``
- an overview is shown of people and their access rights
- if a specific person or team is not listed,
  then on the right top click on ``Invite teams or people`` button
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

* To push to a normal branch you need ``Write`` permission
  however to push to protected branches you need ``Maintain`` or ``Admin`` permission.

* Protected branches are branches where you are required to do pull requests to get something pushed to.
  To merge a pull request in protected branch you must be allowed to push to the protected branch.
  So to merge a pull request you need ``Maintain`` or ``Admin`` permission.

* Only with the ``Admin`` you can do the action ``Merge pull requests on protected branches, even if there are no approving reviews``.
  So in general you do not want to give people that permission. So ``Maintain`` permission is then better to give.

Conclusion
----------

- make only a few people ``Owner``.
- make people who only need access to a single repo an outside collaborator for which we specifically set some
  access permission to only that specific repository. All other repositories are inaccessible.
- members of the organisation have by default ``Read`` permission to all repositories in
  the organisation. Note that this default permission can be changed. To give them more permissions
  add them to one of the following teams:

  * ``Develop`` team: ``Write`` permission ; cannot merge pull request
  * ``Maintain`` team:  ``Maintain`` permission; can merge pull request

- note: for some repositories in the organisation the above teams may have no rights configured.
