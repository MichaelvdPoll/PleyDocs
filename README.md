# PleyDocs


## Release On Web

>"Game Released! Congrats, your game is now running on Trail! You can play the game through either the Trail link or the embedding, both of which you can find on the Game Manager releases page!
Click here to learn how!"

"Game Released! Congrats, your game is now running on Pley! You can play the game through either the Pley link or the embedding, both of which you can find on the Game Manager releases page!
Click here to learn how!"

---

## Game Settings

>Here you'll add the images, links, & text your players will see on Trail!

Here you'll add the images, links, & text your players will see on Pley!

---

## Visual Assets

### Screenshots have Trail Logo

<figure>
    <img src="https://files.readme.io/33f186b-card_image.png" width="400" height="200">
    <figcaption>Card Image</figcaption>
</figure>

<figure>
    <img src="https://files.readme.io/5674564-unnamed.png" width="400" height="200">
    <figcaption>Spotlight Image</figcaption>
</figure>

<figure>
    <img src="https://files.readme.io/f75ae27-gameplay_video.png" width="400" height="200">
    <figcaption>Gameplay Video</figcaption>
</figure>

[Overview | Integration](https://docs.pley.com/docs/overview-capabilities) hyperlink links to an empty page
It should link to [https://docs.pley.com/docs/overview-integration]

---

## Overview | Integration

<figure>
    <img src="https://files.readme.io/5eee8f5-859ec3d-porting-process.png" width="400" height="200">
    <figcaption>Contains Trail in the screenshot</figcaption>
</figure>

---

## Authkit

<figure>
    <img src="https://files.readme.io/272ae49-AuthKit.png" width="400" height="200">
    <figcaption>Contains Trail SDK in the screenshot</figcaption>
</figure>


Incorrect namespace references in the code snippet:
```cs
// Remember to initialize the SDK first. 

// Request a Play Token ID from the SDK:
private string GetTrailPlayToken()
{
    return Trail.AuthKit.GetPlayToken();
}

// Now that we have the Play Token ID, we send it over to your backend so the backend can send a request to Trail's server.
private void SendTokenToBackend()
{
    // Your backend's server send request
  MyBackend.AuthenticateUsingTrail(GetTrailPlayToken());
}
```

Will the HTTP API move domain, as its currently on *beta.trail.gg*? if so, the cURL code snippet will also need to change to reflect the correct destination

---

## Monetization

<figure>
    <img src="https://files.readme.io/09ef03b-untitled2x.png" width="400" height="200">
    <figcaption>Contains Trail SDK in the screenshot</figcaption>
</figure>

---

## In-App Purchases

Link should be to [manage.pley.com](https://manage.pley.com)

>In this article, you'll learn how to implement payments using PaymentsKit. In no time players in your game will easily be able to make purchases of items, cosmetics, currencies, or anything else you want to offer them.
>1) Create a product in the Pley Game Manager (manage.trail.gg/).
>2) Display the product in your game by fetching the price & currency.
>3) Trigger the payment.
>4) Consume entitlements

### Creating a product

Link should be to [manage.pley.com](https://manage.pley.com)

>Creating a product
>First, let's navigate to the Game Manager. Select your project (game) and then click on In-game purchases

### Displaying a product

>API References
>You can find the methods for PaymentsKit in the references for the Unity SDK and for the C SDK.

Hyperlink doesnt work for the Unity SDK it currently links to: [Unity SDK](https://content.beta.trail.gg/references/v1/sdk-unity/latest/api/Trail.PaymentsKit.html)

Incorrect namespace in code snippets and Recipes:

```cs
// Remember to initialize the SDK first.
// using Trail;

private void RequestProductPriceFromTrail()
{
    // We tell Trail to send us the product ID
  Trail.PaymentsKit.GetProductPrice("ff148434-9d1c-11eb-b2d9-c7e44343d0cd", PriceRequestCallback);
}

// Callback that fires when the request is done
private void PriceRequestCallback(Result result, Price price)
{
    if(result.IsOk()) {
    // We then pass the price and the information to the game so it displays it for the player
    DisplayItem(itemName, itemDescription, price.ToString());
  }
  else {
    Debug.Log("Error occured when fetching price information: " + result);
  }
}
```

```cs
// Remember to initialize the SDK first.
// using Trail;

// Calling the method below will show the payment dialog to the user.
Trail.PaymentsKit.RequestPayment("ff148434-9d1c-11eb-b2d9-c7e44343d0cd",PaymentRequestCallback);
  
  
void PaymentRequestCallback (Result result, string orderId, string entitlementId)
  {
    // First, check that there was not unexpected error.
    if (result.IsOk()) {
    // The function below is just a placeholder.
    // You will have to replace it with whatever method you use
    // to send entitlements to your backend.
      MyGameBackend.ConsumeEntitlement(orderID, entitlementID);
    } 
    else 
    {
      Debug.LogError("Payment Error: " + result);
    }
}
```

### Resolving unconsumed entitlements

Incorrect namespace in code snippet:

```cs
// Call the following method as soon as the game has booted
// and the SDK initialized.
// using Trail;

Trail.PaymentsKit.GetEntitlements(
  (Result result, PaymentsKit.Entitlement[] entitlements) => 
    {
    // First, check that there was not unexpected error.
    if (result.IsOk()) {
      // The function below is just a placeholder.
      // You will have to replace it with whatever method you use
      // to send entitlements to your backend.
      MyGameBackend.ConsumeEntitlements(entitlements);
    }
    else
    {
      Debug.LogError("Something went wrong. " + result);
    }
  }
);
```

---

## Pley Connect

### (1) Connect through Code

>1) User clicks a menu button or pop-up in the mobile game.
>2) The Ui displays a Pley Connect code along with instructions.
>3) They go to connect.pley.com on their desktop and enter the code.
>4) They continue playing on web with their mobile progress connected.

point 3 references [connect.pley.com](https:connect.pley.com) which doesnt seem to exist

