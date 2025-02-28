---
title: Making a GitHub App public or private
intro: 'When setting up a {% data variables.product.prodname_github_app %}, you can make it public so that other GitHub users or organizations can install the app, or private so that you can only install it on the account that owns the app.'
redirect_from:
  - /apps/building-integrations/setting-up-and-registering-github-apps/about-installation-options-for-github-apps
  - /apps/building-github-apps/installation-options-for-github-apps
  - /apps/building-integrations/managing-github-apps/changing-a-github-app-s-installation-option
  - /apps/managing-github-apps/changing-a-github-app-s-installation-option
  - /apps/managing-github-apps/making-a-github-app-public-or-private
  - /developers/apps/making-a-github-app-public-or-private
  - /developers/apps/managing-github-apps/making-a-github-app-public-or-private
  - /apps/creating-github-apps/creating-github-apps/making-a-github-app-public-or-private
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
topics:
  - GitHub Apps
shortTitle: Visibility
---

## About visibility for {% data variables.product.prodname_github_app %}s

You can make your {% data variables.product.prodname_github_app %} public or private. {% ifversion fpt %}If you set your {% data variables.product.prodname_github_app %} to public, any user on {% data variables.product.prodname_dotcom_the_website %} or {% data variables.product.prodname_ghe_cloud %} can install it. If you set your {% data variables.product.prodname_github_app %} to private, it can only be installed on the account that owns the app.

{% elsif ghes %}If you set your {% data variables.product.prodname_github_app %} to public, anyone on your {% data variables.product.prodname_ghe_server %} instance can install it, but the app is not available outside of your instance. If you set your {% data variables.product.prodname_github_app %} to private, it can only be installed on the account that owns the app.

{% elsif ghec %}If you set your {% data variables.product.prodname_github_app %} to public, and the {% data variables.product.prodname_github_app %} is owned by an {% data variables.product.prodname_emu %} account, accounts owned by your enterprise can install it, but the app cannot be installed on accounts outside of your enterprise. If a {% data variables.product.prodname_github_app %} is owned by an account that is not an {% data variables.product.prodname_emu %}, and the app is set to public, any user on {% data variables.product.prodname_dotcom_the_website %} or {% data variables.product.prodname_ghe_cloud %} can install the app. If you set your {% data variables.product.prodname_github_app %} to private, it can only be installed on the account that owns the app.{% endif %}

{% ifversion fpt or ghec %}You can create a {% data variables.product.prodname_github_app %} from your individual user account and make it available for organization accounts to install. You do not need an enterprise plan or an organization account to create a {% data variables.product.prodname_github_app %} for organizations even if the organization is owned by an enterprise on {% data variables.product.prodname_ghe_cloud %}.{% endif %}

If you want to make your app available to {% ifversion ghes %}other {% endif %}{% data variables.product.prodname_ghe_server %} instances, then you need to use an app manifest. The {% data variables.product.prodname_ghe_server %} instance will create the app from the manifest and provide you with the required information. For more information, see "[AUTOTITLE](/developers/apps/building-github-apps/creating-a-github-app-from-a-manifest)."

If it is important for {% ifversion ghes %}other {% endif %}{% data variables.product.prodname_ghe_server %} users to be able to use your tool, consider using {% data variables.product.prodname_actions %} instead of a {% data variables.product.prodname_github_app %}. Public actions are available on {% data variables.product.prodname_ghe_server %} instances with GitHub Connect. For more information, see "[AUTOTITLE](/github-ae@latest/admin/github-actions/managing-access-to-actions-from-githubcom/enabling-automatic-access-to-githubcom-actions-using-github-connect)" and "[AUTOTITLE](/admin/github-actions/getting-started-with-github-actions-for-your-enterprise/about-github-actions-for-enterprises)."

For information about changing the visibility of a {% data variables.product.prodname_github_app %}, see "[AUTOTITLE](/apps/maintaining-github-apps/modifying-a-github-app)."

### Public installation flow

Public {% data variables.product.prodname_github_apps %} have a landing page with an **Install** button, so that other people can install the app in their repositories. {% ifversion fpt or ghec %}If your {% data variables.product.prodname_github_app %} is public to all users on {% data variables.product.prodname_dotcom_the_website %}, you can also choose to publish it to {% data variables.product.prodname_marketplace %}. For more information, see "[AUTOTITLE](/apps/publishing-apps-to-github-marketplace/github-marketplace-overview/about-github-marketplace)."{% endif %}

### Private installation flow

Private {% data variables.product.prodname_github_apps %} can only be installed on the user or organization account of the app owner. Limited information about the app will exist on a landing page for the app, but the **Install** button will only be available to organization owners and app managers for the organization that owns the app, or the personal account if the {% data variables.product.prodname_github_app %} is owned by an individual account.