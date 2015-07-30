# ShopifySharp: A .NET library for Shopify.

ShopifySharp is a .NET library that enables you to authenticate and make API calls to Shopify. It's great for building custom Shopify Apps using C# and .NET. You can quickly and easily get up and running with Shopify using this library.

## How to contact me

**If you're looking for a Shopify consultant** to build your next app or integrate your shop with your own custom software, **I'm available for hire**. Send an email to [joshua@nozzlegear.com](mailto:joshua@nozzlegear.com) and we'll discuss your project. If you just want to get in touch with me, the best way to do that is by sending an email to [joshua@nozzlegear.com](mailto:joshua@nozzlegear.com), or by following me on Twitter at [@nozzlegear](https://twitter.com/nozzlegear).

## A work-in-progress

Currently, the only other .NET library for Shopify is [](), which hasn't been updated in over 3 years and only deals with authenticating with Shopify. It doesn't have the functionality for pulling in or manipulating Shops, Orders, Customers, and more. That's why I'm building ShopifySharp � .NET developers need a fully-featured library for interacting with Shopify and building Shopify apps.

With that said, this library is brand new. It currently only supports retrieving shop information, but more features will be added each week until it reachs full parity with Shopify's REST API.

![imgur](http://i.imgur.com/WJKJI9D.png)

Finally, we'll get a NuGet package set up for this library soon.

## Usage

### Retrieving shop information

```
//NOTE: shopAccessToken is NOT your Shopify API key. It's the token returned after authenticating with a user's shop.
ShopifyShopService service = new ShopifyShopService(myShopifyUrl, shopAccessToken);

ShopifyShop shop = await service.GetShopInformationAsync();
```

## Tests

The test suite relies on your own Shopify credentials, including your Shopify API key, a shop's *.myshopify.com URL, and an access token with full permissions for that shop. [This blog post](https://nozzlegear.com/blog/generating-shopify-authorization-credentials) will show you exactly what you need to do to get a shop access token with full permissions.

Once you have those credentials, place them inside of the `AppSettings.example.config` file and **rename that file** to `AppSettings.private.config`. That will ensure your private API key and access token don't accidentally get uploaded to public source control.