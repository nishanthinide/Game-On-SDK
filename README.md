![Game-On](https://res.cloudinary.com/dy3h28fqw/image/upload/v1585113432/game-on/Logos/Logo-square_zq6mq3.png)

## About Game-On
* [Game-On](https://www.game-on.ai) is a Native In-Game Advertising Platform powering high engagement branding solutions.

## Requirements
1. Unity version 5.3.0 or above
2. Build target set to Android

## Quick Integration Guide


__1. GETTING THE SDK__
  + Go to the [releases page](https://github.com/nishanthinide/game-on-sdk/releases/latest). Download the latest Game-On Unity SDK unitypackage file from the downloads section.  
  + Import the unitypackage.

__2. SETTING UP IN-GAME ADS IN YOUR GAME__
  + Add the InGameAdsManager Object in to your game scene by dragging and dropping the InGameAdsManager prefab from the Assets > Game-On > Prefabs folder into the Scene's Hierarchy window.
  + Go to [our developer page](https://developers.game-on.ai). Sign up if you haven't and then sign in. Follow the instructions to register you game and obtain the "Game ID" for your game.
  + Select the InGameAdsManager Object in the Hierarchy window and in the Inspector window you can see the "Game ID" variable on the InGameAdsManager Script Component of the Object. Enter the "Game ID" which you've obtained in the previous step.

__4. SETTING UP AD-PLACEMENTS__
  + From the Assets > Game-On > Prefabs folder you can find the InGameAdObjects namely InGameAdImage (for UI), InGameAdSprite (for Sprite) and InGameAdMesh (for 3D Objects). You can use these objects in your game or set up existing GameObjects (Image, Sprite, 3D Objects). Contact us if you need assistance to set up existing GameObjects as InGameAdObjects. 
  + Go to [our developer page](https://developers.game-on.ai). Register the ad-placements for the game you have registered. The width and height for the ad placements are the dimensions of the Texture needed on the ad-placement (InGameAdObject) in the Unity3D game. Copy the "Placement Id".
  + Select the newly added InGameAdObject in the Hierarchy window and in the Inspector window, paste the "Placement Id" into the "Placement Id" scripting variable avaliable on the InGameAdObject Script component.


__5. ENDING THE GAMEPLAY SESSION__
+ Ending the Session

  + Reference the InGameAdsManager in your Game Code:
  ~~~~
    private InGameAdsManager inGameAdsManager;
  ~~~~
  + Getting the Instance of the InGameAdsManager Object which you've added to the game in step 2.
  ~~~~
    void Awake()
    {
        if(inGameAdsManager == null)
        {
            inGameAdsManager = FindObjectOfType<InGameAdsManager>();
        }

        // Your game code
    }
  ~~~~
  + when redirecting away from the Gameplay session, use the following line of code to send the end of session signal to the InGameAdsManager :
  ~~~~
    if(inGameAdsManager != null) { inGameAdsManager.SessionEnd(); }    
  ~~~~


__6. SHOW INTERACTABLE AD__
  + Reference the InGameAdsManager in your Game Code:
  ~~~~
    private InGameAdsManager inGameAdsManager;
  ~~~~
  + Getting the Instance of the InGameAdsManager Object which you've added to the game in step 2.
  ~~~~
    void Awake()
    {
        if(inGameAdsManager == null)
        {
            inGameAdsManager = FindObjectOfType<InGameAdsManager>();
        }

        // Your game code
    }
  ~~~~
  + Showing the interactable ad:
  ~~~~
   if (inGameAdsManager != null) { inGameAdsManager.showInteractableAd(); }
  ~~~~
  + If interactable ads are avaliable for the ad campaign currently served to your game, then an interstitial ad is loaded.

__7. BUILDING YOUR GAME__
  + Publish your game as you would any normal unity project using the Build Settings window. Make sure to have the Unity Build Platform set to Android as we support Android only. 

## Contact ##
* Visit [game-on.ai](https://www.game-on.ai) for more information
* Email us at info@game-on.ai for any queries