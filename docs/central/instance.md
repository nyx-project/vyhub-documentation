# Instance

## Creating an instance

Instances are created in the [central dashboard](https://vyhub.net/dashboard)

Checkout this [Youtube video](https://www.youtube.com/watch?v=MprML-EaGew) if you need any help


## Using a custom domain

Specify the custom domain in the `create instance` dialog.

> Setting a CNAME record in your DNS settings is required to use a custom domain.  
> Check out the [custom domain guide](custom_domain.md).

## Updating an instance

Instances can be updated in the `edit version` dialog on the details page.  

You can either specify a version or use the auto update functionality.

> Downgrades are not possible.

## Admins

Admins can be added and removed on the details page by giving the exact VyHub username.

> Log out and back into your instance to update the users admin status.

### Removing the admin status
If you do not want to wait for the user to log out and back in again (after removing in the central details page),
you can force the removal by clicking on the X near the admin status on the users dashboard. 

> Caution: if you did not remove the admin status in the central details page, the user will get its status back after a new log in.


### Troubleshoot

#### Instance is "stuck" in status provisioning while using a custom domain

1. Did you already set your CNAME record? It is needed for the provisioning to work.
2. Is your domain using DDOS protection like Cloudflare? Deactivate any services like this for your (sub)domain.
3. Debug with the [custom domain](custom_domain.md#debugging-with-the-cname-checker) guide
4. Contact us!
