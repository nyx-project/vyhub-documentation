# Self-Hosted Frontend

In both VyHub Cloud and Self-Hosted, a custom frontend can be used. Selfhosting allows for 100% customizability of your
theme!
This allows you to customize the look and feel of
the frontend to match your brand or to add additional functionality.

> Self-hosting the frontend is **not** required to use a **custom domain**. Please check out
> the [custom domain guide](../central/custom_domain.md) for
> more information on how to set up a custom domain.

## Preparing the Frontend files

1. Clone the vyhub-web repository from GitHub:

   `git clone https://github.com/matbyte-com/vyhub-web.git`

2. Install `npm` and run `npm install` in the cloned folder to install the required dependencies.

3. Copy `public/config.js.example` to `public/config.js` and adjust the `backend_url` to the API URL of your VyHub
   instance.

4. Run `npm run serve` to start the development server. You can open VyHub in your browser by navigating to
   `http://localhost:5080`.

5. Adjust the frontend code to your needs.

6. Run `npm run build` to build the frontend. The build files will be located in the `dist` folder.

## Deploying the Frontend

### VyHub Cloud

1. You need a webserver and a custom domain to host the frontend.

2. Upload all files from the `dist` folder to the root directory of your webserver.

3. Make sure that `config.js` contains the correct backend URL.

4. On the instance overview at [vyhub.net](https://app.vyhub.net/dashboard), click on `Edit Instance`, set your custom
   domain and enable the `Self-Hosted Frontend` option.

5. Save the changes and open your custom domain in your browser.

### VyHub Self-Hosted

1. In `.env`, set `VYHUB_CUSTOM_FRONTEND` to `true`.

2. Recreate the containers with `docker-compose up -d`.

3. Delete all files from the `web` folder (located in the directory where your `docker-compose.yml` is located).

4. Upload all files from the `dist` folder to the `web` folder.

5. Run `docker-compose restart app`.
