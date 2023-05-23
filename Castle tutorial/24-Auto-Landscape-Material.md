# Auto Landscape Material

First we need to migrate the assets downloaded from the tutorial into our project
It's at C:\Users\hotar\Downloads\0etq38Ro6eVZX7TK8pKQ_IntroUnreal5\IntroUnreal5\CastleAssets
We start by opening the CastleAssets.uproject and we can see the pieces of the castle, even with towers that have an empty interior ! (I checed with a light)
as well as mountains.

To migrate the assets, go into the uproject file, then in the content drawer
All > Content > CastleAssets
Right click on it and select migrate.
Make sure everything is selected in the new menu
then you have to select the destination
C:\Users\hotar\Documents\Unreal Projects\Immortal\Content
this is the destination
Upon importing the files, I have an error message for virtual shadow map and nanite assets.
This could be because nanite is a recent feature and the settings were not put in place when the video was released.
We can go to the project settings and set the Immortal level as the default level.
Edit > Project Settings > Maps and Modes > Default Maps > Editor Starter Map
select Immortal.
