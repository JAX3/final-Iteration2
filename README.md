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
 I used the example from when we were introduce to phaser 3 since i knew it worked and was simplest to implement into my game  
![Image of Yaktocat](https://imgur.com/a/nVPh3MK)

