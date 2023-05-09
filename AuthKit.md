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