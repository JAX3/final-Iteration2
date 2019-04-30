# final-Iteration2

##Week 1
During week one i mainly spent working on getting some new features that were requested in the testing phase of iteration 1 such as adding a hieght scaling system for the platforms as the game was only on a flat plain.
Below is the process of defining the bounds to where the platforms can spawn.
```js
   // a height range between rightmost platform and next platform to be spawned
    platformHeightRange: [-5, 5],

    // a scale to be multiplied by platformHeightRange
    platformHeighScale: 20,

    // platform max and min height, as screen height ratio
    platformVerticalLimit: [0.4, 0.8],
    
    
      // adding a platform to the game, the arguments are platform width, x position and y position
        this.addPlatform(game.config.width, game.config.width / 2, game.config.height * gameOptions.platformVerticalLimit[1]);
```
this allows me to adjust the height that each platform. Also during this week I added 
