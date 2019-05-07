# final-Iteration2
## Week 1
For the first week  i mainly spent adding feature from iteration 1 
parts from [Iteration1](https://github.com/JAX3/Runner-game-Iteration1) Which includes 
- varying height of platforms
- scoring system
- obstacles (fire)
and adjusting the platform speed due to it being a bit difficult  since the plays jump would land just before the platform.
During the week i also spent trying to fix the timer system as the previous one was hacked together and was a bit clunky in the way it operated  but towards the end of the week i gave up with trying to fix it or find a copy on the phaser 3 labs though i didn't manage to find a suitable fix. In the end i replaced it with a simple scoring system.
```javascript
 timedEvent = this.time.addEvent({ delay: 10000, callback: counter, repeat: 10, startAt: 8000 });
 ```
 ```javascript
 scoreText = this.add.text(16, 16, 'score: 0', { fontSize: '32px', fill: '#000' });
 
 // setting collisions between the player and the coin group
        this.physics.add.overlap(this.player, this.coinGroup, function (player, coin) {
            coin.disableBody(true);

            this.tweens.add({
                targets: coin,
                y: coin.y - 100,
                alpha: 0,
                duration: 800,
                ease: "Cubic.easeOut",
                callbackScope: this,
                onComplete: function () {
                    this.coinGroup.killAndHide(coin);
                    this.coinGroup.remove(coin);

                    score += 10;
                    console.log("Hi");
                    scoreText.setText('Score: ' + score);
                }
            });

}, null, this);
 ```
 I used the example from when we were introduce to phaser 3 since i knew it worked and was simplest to implement into my game.
 
 ## Week 2 
 
 During week i mainly spent rewriting alot of my code by spliting alot of  platform,fire, and coin animations into a preload class to help smooth out loading and adding a pause of start feature to add a start button which was mentioned in my iteration 1 testing  phase.
  Once i managed to  sort out my classes i went through and added sprites to each element of my game including the player,platfroms,fire,coins and background mountains which the player,coins,mountain and fire have custom animations to make the game look more finished and polished then the original grey boxes in iteration 1.
  
  
  
The main problem i had during this week was fixing my scoring system  due to the coins adding 50-100 points over the 10 since the player hitbox was colliding while animation was playing this took a few hours to fix by setting the coin body to be disabled during the animation frames.
```javascript
  coin.disableBody(true);
  ```   
  below is the feedback 
  
  ## feedBack
I got a decent amount of feedback from the people testing.
* Differant types of obstacles such spikes and walls 
* music/sound effects
* speed of the platforms to ramp up as the game goes on.


### Test data
Tester       |  score                        
------------ | -------------
Tester 1     | 50,50,30
Tester 2     | 20,40,10
Tester 3     | 80,70,60
Tester 4     | 20,10,60
Tester 5     | 30,40,10
 From my test data  i can see the average score is 40  from all of my tester with each of them averaging  around 50 points. But i could improve this by adjusting the probablity  that the coins can spawn  to 30% or higher to make the game easier for players to gain points and with the feedback its mainly small things that could be adjusted and added such and the ramping platform speed as the game goes on or when linked to how many points they have.
 ```javascript
  // % of probability a coin appears on the platform
    coinPercent: 25
```


