# Use your own domain for your instance

Read this guide for further information on how to use your own domain with VyHub.  
You do not need to use your own domain, we offer you with a free vyhub.app domain (e.g. gaming.vyhub.app)

1. Buy your own domain at a domain name registrar of your choice (e.g. [Namecheap](https://www.namecheap.com/))
2. Set the domains CNAME record to the corresponding VyHub url

## Get your own domain

> A domain name is the name of a website (like vyhub.net or google.com)

In this guide we will use [Namecheap](https://www.namecheap.com/), which offers good prices and is one of the biggest registrars in the world.

### Choose your desired domain name, add to cart and checkout


![Enter a domain name](../assets/custom_domain_guide/example_domain_search.jpg)
Enter a domain name and check for it's availability

![Add to cart](../assets/custom_domain_guide/domain_add_cart.jpg)
Add to cart and follow the checkout process

> You do not need to add any of the "recommended packages" namecheap offers.


## Set the domains CNAME record

> You need to set the CNAME record to our servers, that you can reach VyHub with your domain.

Please search and follow the tutorials on how to set the CNAME record provided by your registrar.

### CNAME Value

![Find the CNAME value](../assets/custom_domain_guide/instance_details_page.jpg)
Find the value on the instance details page

### Setting the CNAME with a Namecheap.com domain
Follow this [guide](https://www.namecheap.com/support/knowledgebase/article.aspx/9646/2237/how-to-create-a-cname-record-for-your-domain/) provided by namecheap. 

1. Sign into your Namecheap account
2. Select `Domain list` on the left
3. Click the `Manage` button next to your domain
4. Navigate to the `Advanced DNS` tab
5. Click `Add New Record` in the `Host Records` section
6. Select `CNAME Record`
7. Enter the CNAME value from your instance in the `Value` column (leave host empty unless you want to use a subdomain e.g. vyhub.yourdomain.com)
8. Click the `Save All Changes` button

