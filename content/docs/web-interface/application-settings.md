## Application settings

On each application you will find the settings page.
In this article we will shortly walk through its content.

### Collaborators

Per application you can manage the permission settings of wercker users, wercker
offers three types of [roles and permissions](/docs/web-interface/roles-and-permissions.html).

But what if you want to add someone that is not a wercker user yet, you can
use the same input field to send an invite email, when signed up, the user can directly
access your application.

When the owner of an application is an organization you can only manage the
permissions of teams. The owners team of an organization always has `admin` access.

[Read more on roles and permissions &rsaquo;](/docs/web-interface/roles-and-permissions.html)


### Deploy targets

Here you can setup deploy pipeline targets. Want read more on deploying
with wercker, continue reading using the following link.

[Read more on deploying &rsaquo;](/docs/deploy/index.html)


### Pipeline

Here you can set `environment variables` that are application-wide,
these are available during every build and deploy.

This can be used for information that you don't want to store in your repository
(i.e. login information or keys).

Want to read more on `environment variables`, continue reading using the following link.

[Read more on environment variables &rsaquo;](/docs/environment-variables/index.html)


### SSH Keys

Here you manage `SSH keys` that you can leverage during builds and deploys.
Want to read more on `SSH Keys`, continue reading the following link.

[Read more on SSH keys &rsaquo;](/docs/ssh-keys/index.html)


### Options

This is a grouped section of settings. Here you can adjust the following
settings:


### Support

When you are in need of support, you can hit the support switch and send us a message via
the UserVoice pop-up.

By activating wercker support you give the wercker team `builds + deploys` permissions.
This allows us to see the details and debug the issue at hand.


#### Clear cache

Here you can clear the `$WECKER_CACHE_DIR`. Want to read more on how to use the
wercker cache directory, continue reading the following link.

[Read more on wercker cache &rsaquo;](/docs/pipelines/wercker-cache.html)


#### Webhook

When wercker is not picking up your commits or wercker shows a `broken webhook` warning,
you can hit the 'Fix webhook' button. Note that you need to be an
`admin` on your repository in order to fix the webhook.

[Read more on webhooks &rsaquo;](/docs/faq/how-do-webhooks-work.html)


#### Repository access

Here you can update the settings how we checkout your code.
For instance, if your builds fail during the `get code` step, you may need to reset
the key used to check out the code or in the case of a public application, you may want to
configure your application to be checked without an SSH key.

[Read more on repository access &rsaquo;](/docs/web-interface/repository-access.html)


#### Public / private

Set your application to be publicly viewable, anonymous users can now view all builds.
This ideal for when you are managing an `Open source` application. Users can track
the results of there commits before creating a `Pull Request`.

If you are creating a wercker `pipeline step` your application needs to be public.
Your published `pipeline step` will gain an extra page with details.


#### Ignored branches

Here you can set which for which branchname wercker should **not** trigger a build.
It supports a maximum of 10 branchnames, and each branchname should be separated
with a **space**.

By default all applications with a GitHub repository have already one branchname
prefilled, the branchname `gh-pages` is ignored for users who deploy to Github pages.
If you don't make use of GitHub pages you can remove or ignore this setting.

#### Infrastructure stack

Here you can switch the wercker stack for your application.
New builds and deploys will use this stack upon switching. Want to read more on our infrastructure
stacks, continue reading using the following link.

[Read more on stacks &rsaquo;](/docs/pipelines/stacks.html)

#### API user

This section is only visible when the owner of an application is an organization.
Normally the owner’s GitHub or Bitbucket credentials are used for setting the
status of builds and to make various API calls.

An organization doesn’t have the option to connect to GitHub or Bitbucket, so you
can select an organization member whose credentials will be used.


#### Transfer ownership

Here you can transfer the ownership of an application to another wercker user or
an organization.

We give an extra warning when you’re about to transfer ownership, because at this
moment it is not possible to transfer an application back to a user or to another organization.

#### Delete application

*“Danger, Will Robinson!”* Here you can choose to delete your application and all its settings.
