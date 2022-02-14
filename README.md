# **Opinew Headless Example**

This repository is usage example of Opinew headless widgets. It's based on Shopify Hydrogen example repository: [Hydrogen Examples](https://github.com/Shopify/hydrogen-examples).

## Opinew manual install

1. Make sure you have instaled [Opinew App](https://apps.shopify.com/photo-reviews) on your Shopify store. It's free.
2. Add the following code in page `<head>`

```
<link rel="preload" href="https://cdn.opinew.com/shop-widgets-components/v1/static/i18n/lang.json" as="fetch">
<link rel="stylesheet" href="https://cdn.opinew.com/shop-widgets-components/v1/static/css/index.css">
<script src="https://cdn.opinew.com/shop-widgets-components/v1/static/js/index.js" async ></script>
```

3. Insert widget tag in desired place in shop code

```
<opinew-plugin type="<WIDGET_TYPE>" product-id="<PRODUCT_ID>" domain="<SHOP_DOMAIN>.myshopify.com"></opinew-plugin>
```

_You will need to change <WIDGET_TYPE>, <PRODUCT_ID> and <SHOP_DOMAIN> to data specific for your shop. Please note that you need to use your myshopify.com shop domain and not your custom domain._

#### Properties

| Name       | Description                                                                                                                                                                                                                                                                            |
| ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| type       | Required value to choose desired widget type. Available options are: <br/>`product`, `floating`,`all`,`carousel`, `request`,`product-stars`, `collection-stars`                                                                                                                        |
| product-id | Shopify product id. Required for: `product, floating, product-stars, collection-stars`                                                                                                                                                                                                 |
| domain     | Shop domain – Optional. When not set, domain is read from browser window.location.host property. Recommended to set to make sure widgets work properly on dev environment. This needs to be your myshopify.com domain provided by Shopify and not your custom domain (if you use one). |

## Demo

To run this demo make sure you are using node 14 or later. Run below commands and open browser at http://localhost:3000/

```
nvm use # or nvm install to set node 14
yarn install
yarn dev
```

Plugins used in this example are:

- Carousel plugin on main page (`Index.server.jsx`)
- Badge plugin in footer (`Footer.jsx`)
- Stars plugin on product page below the price (`HiglightedProduct.client.jsx`)
- Product plugin (reviews) on product page (`ProductDetails.server.jsx`)

## Shopify notice

This repository contains examples and references of Hydrogen implementations. Hydrogen is a **React-based framework** for building dynamic, **Shopify-powered** [custom storefronts](https://shopify.dev/custom-storefronts).

In each directory you will find a self-contained example application that demonstrates using Hydrogen. These examples are built and maintained by partners and community members.

See the `README.md` in each example directory for more details on how to get started for each project.

To explore Hydrogen, you can get started locally using [yarn or npm](https://shopify.dev/beta/hydrogen/getting-started) or explore a preview experience of Hydrogen on Stackblitz at [hydrogen.new](https://hydrogen.new)

We are currently rebuilding Shopify Supply as a [Hydrogen](https://github.com/Shopify/hydrogen) reference example.

## Hydrogen

Hydrogen is a React framework and SDK that you can use to build fast and dynamic Shopify custom storefronts. To learn more head to:

- [Hydrogen Github Repo](https://github.com/Shopify/hydrogen)
- [Hydrogen Getting Started Docs](https://shopify.dev/custom-storefronts/hydrogen)

## What is Shopify Supply?

[Shopify Supply](https://shopify.supply/) is more than swag. It's your first stop for the highly-anticipated releases you've been asking for, and the surprise drops that'll delight you. If you're interested in unique products designed for entrepreneurs, you're in the right place.

## Getting started

**Requirements:**

- Node v14+
- Yarn

```bash
yarn
yarn dev
```

## Testing

This application is tested with [Cypress](https://docs.cypress.io/).

Cypress is currently configured to run against a local dev server. See instructions for starting a dev server in the `Getting started` section.

### Running headless cypress

```bash
yarn cypress:run
```

### Running headed cypress

```bash
yarn cypress:open
```

## Building for production

```bash
yarn build
```

Then, you can run a local `server.js` using the production build with:

```bash
yarn serve
```

## Code of Conduct

All developers who wish to contribute through code or issues, please take a look at the [Code of Conduct](https://github.com/Shopify/hydrogen-examples/blob/master/code_of_conduct.md).

## License

MIT, see [LICENSE](https://github.com/Shopify/hydrogen-examples/blob/master/LICENSE.md) for details.
