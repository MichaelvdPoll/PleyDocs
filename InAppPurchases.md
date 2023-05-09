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