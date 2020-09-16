This policy template is licensed under the [Creative Common's CC0 1.0 Universal (CC0 1.0) Public Domain Dedication](https://creativecommons.org/publicdomain/zero/1.0/) license.



---------------



# [ORG NAME] Outbound Open Source Security Policy

> ## End User Guideline / Quick Summary
>
> When [ORG NAME] releases code publicly we want to ensure that it can not be used in a malicious way against [ORG NAME] or any other organization. We also want to maintain a reputation as building secure code within the community and avoid negative press. In addition, [ORG NAME] code should only be released externally or publicly if it follows our process and has been properly reviewed by the Security team.
>
> **The least you need to know before publicly releasing your repo:**
>
> - Work with [ORG NAME] Security team to do a review of your code as is and any open security bugs
>
> - The open source repo should not expose anything internal about [ORG NAME] - this means sanitize your comments, remove config files and secrets, and don't reference any internal infrastructure or internal only dependencies.
>
> - Ensure that your project's documentation and `README` clearly explains how to report security issues following our template
>
> - We are not just dumping code out there, you need to commit to maintaining and monitoring the project on an ongoing basis
>
> - It’s not only important for us to know and fix security bugs for internal use;  we owe it to our downstream user community to ensure code we commit and code contributed by others is secure
>
> - Failure to follow the rules can result in your public project being taken down



## Purpose

To ensure that [ORG NAMES]'s external facing software repositories do not expose known software vulnerabilities or non-public information. Further, to ensure that any security issues identified by external parties for our external facing repositories are communicated and triaged in a timely manner.

## Policy

### Contributions Subject to Security Review

All contributions to public facing open source projects where [ORG NAME] is officially identified as the contributor must be approved by [ORG NAME] Security prior to the initial public release. An official [ORG NAME] contribution is one committed to a repository owned by [ORG NAME] or where [ORG NAME] is credited with the copyright.

Contributions by [ORG NAME] employees to public repositories and open source projects as part of an individual's job role should be reviewed by [ORG NAME] Security subject to this policy.

### Security Review Requirements for External Release

Before software subject to review is released, the Security team **must** perform the following checks:

1. Ensure that the software has been sanitized of internal information, including comments, internal commit history, configuration variables, inclusion of non-public libraries, etc.

2. Ensure there is no disclosure of internal infrastructure or processes (e.g., does not describe our deployment or CI/CD in comments or notes)

3. Ensure that there are no obvious security holes and that the release does not include any known open vulnerabilities

4. Review the project's README file and any other major documentation to ensure there are no instructions which will conflict with internal security requirements or best practices

5. If vulnerabilities have been risk accepted internally, **this does not mean they are automatically accepted for external publication**. Security approval must be obtained, and if granted, any known defects accepted must be clearly documented in source code and/or documentation for downstream users

6. A full application security review should be performed based on internal standards and best practices 

7. Review the project `README` and `CONTRIBUTING` documents for proper security directions for contributors; a `SECURITY` section or file must be included based on the template below

8. Ensure the project is explicitly listed in our Bug Bounty Program scope

In addition, the following security checks should be performed:

1. The documentation clearly presents security requirements, trade-offs, and implementations. For example, if we removed functionality for secret management based on our internal tools, downstream users should be warned against using secrets stored inline or in a plaintext config file

2. Security filters and security specific functionality should be commented and the comments should be reviewed and modified by the Security team as needed

3. Review the config settings on the repo, e.g., ensure proper RBAC, wikis disabled, etc.

### Security Contact and Security Bug Reporting Requirements

The `README` or equivalent for each official public facing [ORG NAME] owned/maintained repository must include a "Security" section (or should point the user to a local `SECURITY.md`) which at a minimum should include contact information for [ORG NAMES]'s Security team and should direct public users and contributors to submit bug reports and security fix patches directly to [ORG NAMES]'s internal Security team first (e.g., via bug bounty program), rather than through a normal public pull request. *See the template at the bottom of this document for an example.*

If there is a `CONTRIBUTING` document in the repository, it should also clearly explain that security bugs and patches should first be submitted privately to the internal Security team, and not just as a regular pull request or issue. *See the template at the bottom of this document for an example.*

All open source repositories that are active within [ORG NAME] should be included in [ORG NAMES]'s bug bounty program. When new repositories are published publicly, [ORG NAME] Security should update the bug bounty scope publication. Information about the bug bounty program should be included in the security section and/or the `SECURITY.md` file.

Some contributors may still publish security fixes or pull requests with security implications publicly and directly. If the repository management system provides issue tagging, a "security" tag should be attached. The [ORG NAME] Security team should be automatically notified whenever an issue is tagged with "security".

### Security Review of Non-[ORG NAME] Contributor Pull Requests

Whether or not [ORG NAME] merges external contributor contributions into the internal version of the software, these contributions should be reviewed for security concerns, and the Security team should be brought in as necessary before being accepted by [ORG NAME] project maintainers in the official external repo. ([ORG NAME] wants to maintain its reputation for "good code" and allowing clearly buggy security software damages our organization's open source reputation in the community.)

When external contributions are merged back into a separate internal version of the software, at least two internal [ORG NAME] software engineers must review the code, even if already approved by the public repo maintainer team. If there are any concerns about the security impact of a particular pull request, the Security team should be contacted to review the code before it is accepted.

If the contribution **constitutes a new major feature or a major change** in functionality, the full application security review must be completed before those changes are put into production within [ORG NAME]'s internal environment.

When code that originates from a non-[ORG NAME] contributor is brought into an internal-only version of the repo it should be clear that the code was originally written by someone outside of [ORG NAME] (e.g., commit comment / inline comments pointing back to the external PR). This helps to track down authorship in cases where the code is put into [ORG NAME]'s internal repo by a [ORG NAME] engineer who did not author the code. If the code is used internally as a submodule or library then the public review should usually be sufficient.

### Tracking of Security Bugs Reported From External Contributors

Project maintainers should encourage external contributors to utilize [ORG NAME]'s bug bounty program. If a security researcher prefers to work directly with [ORG NAME, they should be encouraged to practice [responsible disclosure](# "link to [ORG NAME]'s responsibile disclosure policy") and [coordinated disclosure](https://blogs.technet.microsoft.com/ecostrat/2010/07/22/coordinated-vulnerability-disclosure-bringing-balance-to-the-force/) principles so that [ORG NAME] can release a quality fix internally and externally, rather than playing catch-up.

The owner/maintainer of the external [ORG NAME] repository is responsible for fixing the bugs in a timely manner. The [internal SLAs](# "link to [ORG NAME]'s security vuln remediation SLAs") are in force by default, however, the Security team and the project owner must be cognizant that an individual who wants to practice responsible disclosure may release the security vulnerability irresponsibly if he/she feels we are not acting quick enough. The external contributor should be kept up to date with timely and appropriate updates, but should not be provided any internal access beyond what is scoped in our bug bounty without a proper legal contract/agreement.

If however, an issue or pull request is submitted directly to the repo or a elsewhere publicly (chat, mailing list, etc.) **without first notifying our internal Security team** it should be treated with a higher priority than normal and the Security team may impose an expedited timeline for remediation or patching.

Whether or not the security issues is being tracked in the public repo, it must be tracked internally and should be included in normal security bug reporting.

### Only Authorized External Servers/Locations

The open sourcing of any [ORG NAME] proprietary software must be approved by [ORG NAME] management prior to its release. An official, [ORG NAME] controlled external server/account on SaaS service (e.g., GitHub) must be setup and maintained for hosting the official [ORG NAME]-maintained repository. Only one main public repository should be setup, the repo should not be mirrored to multiple services (e.g., both GitHub and GitLab) unless it is very clear which is the primary/official.

Employees must not release, branch, or mirror any [ORG NAME] software to a personal or public facing server **from an internal repository**. Instead, personal mirrors/branches should only be sourced from [ORG NAME]'s official public repositories. This restriction applies even if the original software used within [ORG NAME] was open source; simply because the inbound license was open source does not grant an employee the right to release the changes (subject to specific licensing requirements).

[ORG NAME] Software Engineering management must maintain an inventory of all public facing repos, which should include the name of the software, primary maintainer/owner, a description, public facing URL, and whether [ORG NAME] still uses the software internally. When the primary maintainer/owner switches teams or leaves [ORG NAME] a new primary maintainer/owner must be assigned.

[ORG NAME] Security retains the right to review security configurations, permissions, etc. for all repository hosting and to make necessary changes for security and compliance reasons.

### Permissions on External Repository Hosting/Servers

Repository and organization owners must be limited in accordance with other RBAC policies and standards. Only [ORG NAME] employees may be members of the organization (*in GitHub terminology*) or similar. When an individual is no longer employed with [ORG NAME] their access must be removed; where possible this should be done via tying access to an SSO mechanism.

### Release of Previously Internal [ORG NAME] Code

When [ORG NAME] open sources a repository for the initial public release, it must start a new commit history (i.e., cut and paste without the `.git` folder and do a new `git init`). If the project will have both a public and internal version, new internal commit history after the public release must not be pushed to the public version of the repository. Instead, the public repository should be cloned, the changed files should be directly copied into the local clone and then pushed from here back to the public repository. Changes must not be pushed from the internal repo to the external repo since this may include internal history or comments.

If the main repo itself will not be ported as-is to the public version (e.g., we want to maintain a separate internal version to reference internal services, vault, etc.), then the team should create a new repo on our internal version control system (e.g., for repo "coolToolX" `clone`, re-`init` as "ext-coolToolX"). The owning team should modify this repo and make all changes and arrive at the final "public release ready" state. The security review will be performed on this version of the code. This internal prep repo may be decommissioned after public release, but [ORG NAME] must always maintain an internal mirror of any public repo for internal-only comments and for integration with internal tools and automated scanners. See "Ongoing Monitoring of Public Repos" below.

### Greenfield Open Source Projects

A greenfield open source project is one where the software starts out in the public sphere from the first commit as opposed to being an existing project within [ORG NAME] that is then ported externally. In this case, all development, documentation, etc. will happen in public. [ORG NAME] is still the primary maintainer, but there is typically no inbound-outbound flow and the version used by [ORG NAME] is not hosted privately/internally.

Greenfield projects must only be for software that will not result in exposure of [ORG NAME]s non-public intellectual property and must not be for core competitive competencies (such as [SECRET SAUCE EXAMPLE]). Greenfield software must not be dependent upon internal [ORG NAME] systems or [ORG NAME] specific practices.

Because all development and documentation for such software will be public, comments, pull requests, naming conventions, etc. must not reference [ORG NAME] internal systems, problems, or other systems. Any commits or discussion must be created with consideration for a public audience.

For internal integration, greenfield software must either be treated as library or extended for internal use with another repository that modifies or uses the public repository as a submodule. (For clarity: The flow should only be from external-->internal so that internal configs and implementations are never publicly revealed).

All greenfield projects must have an internal owning team. Security bugs should still be initially reported and managed internally to [ORG NAME] consistent with this policy.

While the repository lives publicly, the Security team must continue to be engaged as if this was an internal software project since the software powers [ORG NAME]. This includes design reviews, production readiness reviews, and vulnerability tracking.

**For the avoidance of doubt, [ORG NAME] Security must be notified and approved before the greenfield repo is started. This is because there may be non-code issues and other setup needed for monitoring.**

### Use and Inclusion of Third Party Libraries and Dependencies

In addition to maintaining the code in the open source repo, the [ORG NAME] repo maintainer must ensure that any required and optional dependencies are updated appropriately to compatible versions that do not contain known security vulnerabilities (e.g., you are using `npm`, `nuget`, etc. to pull down a package as part of the build process configured in the repo). Any packages or libraries included must be updated in a timely manner.

### Public Hosting of a Public Repository in a Packaged Format

If the [ORG NAME] project will be publishing releases to a public package management system, then this must be registered ahead of time and the account must be registered using the email address "opensource@[ORG NAME].com". If this code is being ported from an internal project that used a local/private repository remove and updates references accordingly. Further, ensure there are no naming conflicts with existing tools that may be hosted on popular hosting platforms.

> *Example:*
>
> Joe creates a node module called "[ORG NAME]-awesome-tool"
>
> The README instructs users of the project to issue the command "`yarn add [ORG NAME]-awesome-tool`"
>
> This means that by default for a normal user using `yarn` will be pulling the package from "`https://yarnpkg.com/en/package/[ORG NAME]-awesome-tool`"
>
> [ORG NAME] must own and control this public repository for the package "https://yarnpkg.com/en/package/[ORG NAME]-awesome-tool"
>

The same applies for other package management systems.

### Automated Package Publishing

Project maintainers may setup automated packaging mechanisms using [ORG NAME] owned/controlled services to aide in automated deployments. If such automated packaging and release mechanism are in place, documentation and naming conventions must make it clear which are approved/stable releases versus those which are development/bleeding-edge. It is recommended that stable releases be manually approved and deployed. [ORG NAME] employees must only use approved stable packages for internal production environments, unless there is prior, documented managerial approval to use some other build. Security reserves the right to prohibit non-stable package usage based upon incident or risk assessment. In emergency situations (valid business reason with manager approval or security reason) may permit the usage of a non-approved bleeding edge package temporarily.

The public automation build and any test environments for [ORG NAME] OSS must not be in a [ORG NAME] production environment (i.e., should be in a special subscription or a hosted service if builds will automatically include PRs from outside of [ORG NAME]).

### Community Editable Documentation

All documentation posted to community/publicly must be under [ORG NAME] control. If a OSS maintainer wishes to allow the community to contribute/edit documentation, then a non-wiki solution must be used that includes a review/approval workflow, such as:

- GitHub pages tied to a repo versus using the GitHub project wiki
- A "docs" folder within the main project if they choose.

Wiki functionality that allows edits to be made without an approval workflow on a hosting platform must be disabled. 

### Ongoing Monitoring of Public Repos

The public facing repo for software which [ORG NAME] releases publicly and continues to user internally must be actively monitored for changes, comments, and pull requests. This is true whether or not the software is under active development inside of [ORG NAME]. If [ORG NAME] no longer uses the software internally, the internal [ORG NAME] maintainer should continue to monitor the software for pull requests and bug reports. If [ORG NAME] will no longer maintain or monitor the repository, then this should clearly be documented in the public readme for the repository.

The Security team should ensure a designated point person / owner is assigned at all times to monitor the public facing repository.

All public repositories must make it clear whether the project is currently supported by [ORG NAME] or has been abandoned for official support.

### Internal Mirror for Public Projects

An internal mirror must exist for every public repo for a [ORG NAME] open source project. This mirror is used for non-public discussions, comments, automated scanning, and bug reports. It is a one way flow and should generally be treated as a read-only/reference mirror for the public repo.

Security should report any bugs found on the public repo by referencing the internal mirror version. [ORG NAME] Security should treat this repo the same as other internal repos in terms of scanning and bug reporting. [ORG NAME] Security will issue bugs and issues on this internal repo. Fixes should be applied directly to the public repo and not pushed from internal mirror -> public repo (once the mirror updates, Security will close the bug).

### Identification of Unauthorized Open Sourcing of Internal Software

The [ORG NAME] Security team should perform a periodic audit of GitHub, StackOverflow, Quora, and other common websites looking for unauthorized exposure of our internal libraries or code snippets.

If any unauthorized code (complete or partial) is found externally, the Security team should ensure the individual who published the code takes it down when possible. If necessary, the Security team should escalate to the legal team to work with the service provider or website owner to have the code permanently removed. All normal incident response procedures should be followed.

Individual employees that wish to present code snippets, algorithms, etc. in public blog posts or presentations must obtain manager approval prior to the release. If a significant amount of code will be released (as determined by the employee's manager) publicly, the Security team must approve the release as well.

### Public Project End of Life / End of Support / Decommission

Projects which are used internally must continue to be maintained until they are removed from production within [ORG NAME]. Decommission/deprecation is NOT an excuse to stop monitoring the public repo, issues, and activity. The owning/maintaining team must formally announce and document when [ORG NAME] ends support for a project used by the community.

A best practice is to announce a deprecation period to give people an opportunity to migrate; however, in all cases there MUST be a "final" end of support announcement added in the README for the project.

When [ORG NAME] will no longer be supporting the open source project:

- Make it clear publicly that we are not supporting the project anymore
- Provide guidance on support, forking, or alternative projects to downstream users

#### Transfer of Ownership

[ORG NAME] does NOT transfer ownership of repos or packages to third parties or even current/former [ORG NAME] employees or contractors. It is permissible to fork the project when allowed by license, but it must have a new name for repos and packages. Discuss with Security if you need further guidance. See [this case study](https://www.theregister.co.uk/2018/11/26/npm_repo_bitcoin_stealer/) for more information on this topic.

#### Additional Recommended Actions

In addition to utilizing these templates in the README of your project, you should attempt to provide notification to users in other ways, such as:

- If you have a project mailing list, chat, or forum then announce the decommission multiple times (e.g., 60 days out, 30 days out, 7 days out, last day)
- You should issue a warning triggered in the build process or during an update that will be shown to downstream users during build process
- The community can fork, rename, and make a new package if someone else wants to maintain the project going forward

#### Deprecation / Decommissioned Repo Templates

Use the below templates as appropriate for your needs. Discus with Security if you would like to make major deviations.

### General Monitoring Requirements

[ORG NAME] Security team should periodically review public facing [ORG NAME] owned repositories for compliance with this policy and for security bugs, internal information leakage, etc.



------------

# Templates

## README.MD Security Section Template

Your `README` should explicitly point to `SECURITY.md` in addition to any security information you may want to include in your `README`.

[Template for Security Section of README](security-section-for-README.md)

## CONTRIBUTING.MD Security Section Template
Your `CONTRIBUTIING` should explicitly point to `SECURITY.md` in addition to any security information you may want to include. You can use the following as a section template:

[Template for Security Section of CONTRIBUTING](security-section-for-CONTRIBUTING.md)

## SECURITY.md Template
You should include the following content in a SECURITY.md file within your project. Your README and CONTRIBUTING documents should clearly reference this file and may include portions of this document directly within those documents.

[Template for SECURITY document](SECURITY-template.md)

## Deprecation Template
Use this template to announce that you will be ending support for this library in your project's `README`. This date should be at least 30 days AFTER the planned internal decommission, and should be publicly posted as soon as possible. If the repo is already no longer used, this message can be posted immediately.

[Template for deprecation notice](deprecation-notice-template.md)


## Decommission Template
Use this template once the project is fully decommissioned and will not longer be maintained. This should REPLACE the decommission message and MUST be shown in the project repo's main README.

[Template for decommission notice](decommission-notice-template.md)