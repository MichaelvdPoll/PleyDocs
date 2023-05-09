# PleyDocs


## Release On Web

>"Game Released! Congrats, your game is now running on Trail! You can play the game through either the Trail link or the embedding, both of which you can find on the Game Manager releases page!
Click here to learn how!"

"Game Released! Congrats, your game is now running on Pley! You can play the game through either the Pley link or the embedding, both of which you can find on the Game Manager releases page!
Click here to learn how!"


## Game Settings

>Here you'll add the images, links, & text your players will see on Trail! 

Here you'll add the images, links, & text your players will see on Pley!


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


## Overview | Integration

<figure>
    <img src="https://files.readme.io/5eee8f5-859ec3d-porting-process.png" width="400" height="200">
    <figcaption>Contains Trail in the screenshot</figcaption>
</figure>


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

Will the HTTP API move domain, as its currently on *beta.trail.gg*? if so, the cURL code snippet will also need to change 

