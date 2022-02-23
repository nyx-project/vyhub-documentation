# Instance

## Creating an instance

Instances are created in the [central dashboard](https://vyhub.net/dashboard)


## Using a custom domain

Specify the custom domain in the `create instance` dialog.

> Setting a CNAME record in your DNS settings is required to use a custom domain

## Updating an instance

Instances can be updated in the `edit version` dialog on the details page.  

You can either specify a version or use the auto update functionality.

> Downgrades are not possible


### Troubleshoot

#### Instance is "stuck" in status provisioning while using a custom domain

1. Did you already set your CNAME record? It is needed for the provisioning to work.
2. Is your domain using DDOS protection like Cloudflare? Deactivate any services like this for your (sub)domain.
3. Contact us!
