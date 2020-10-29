# Parkour Game Project
### Algorithm Design
I use algorithm of html5 and javascript to design this game. 

At first, I need to add a canvas in html and write the html framework. 

Secondly, I need to create some game scenarios by using ‘Phaser’ for this game. There are four main scenarios: boot, load, title, play.
Boot scene is used to prepare for some games. Load scene is about implementing the loading progress bar and loading some resources, such as images and audios, and then going to the next scene after loading. Tile scene is the menu of the game. And the play scene is the main game part.

### More Details of Design
At first, this is achieved by adding a canvas in html5 and instantiating a game object. However, the phaser dynamically adds this canvas by the ID of the parent element of the DOM.

For example, ‘Phaser.Game(width, height, renderer, parent, state, transparent, antialias, physicsConfig)’. In this function, width is the width of the canvas, height is the height of the canvas, Phaser.CANVAS uses the html5 canvas, Phaser.WEBGL uses the better performing WebGL for rendering, Phaser.AUTO is automatically detected, if the browser supports WebGL, then it would use WebGL, otherwise using Canvas. And parent specifies that the parent element of this canvas, it can be an id or the dom element itself and phaser will automatically create a canvas in this parent element. State is the scene. Transparent means whether to use a transparent canvas background and antialias means whether to enable antialiasing. PhysicsConfig means game physics system configuration parameters. Above all the parameters can be selected.

The next step is to create the scene, which can be a custom object or a constructor. The ‘load’ scene is about creating a sprite to display the progress of loading meanwhile loading some other resources, such as images and audios. And after this part has loaded, the player would enter the next scene ‘title’.

Thirdly, we would create the title scene. ‘Autoscroll’ means constantly moving, which makes the background and ground move at different speeds and then we need to create the tween animation for the title. ‘TitleGroup’ is a group concept that puts a small group together for operation.

For example, to(properties, duration, ease, autoStart, delay, repeat, yoyo). Properties contains a js property, which is what the object should become.

Duration means interval time with Milliseconds as units. Ease means whether need to beease and the default is uniform speed animation. Autostart means whether the game needs to start automatically. Delay means the delay time with milliseconds as units at which the animation starts. Repeat means the number of times the animation is repeated. If the animation needs to loop forever, set this value to Number.MAX_VALUE. Yoyo means if the value is true, the animation will automatically reverse. Finally added a btn plus click time and set anchor point.

In the last, the most important part in the game is the ‘play’ scene. It mainly contains two important parts. One is the create function. In the create function, players can jump the missing area by using the space bar in the keyboard. The other is update function. In this update function, it would calculate the scores the player obtained. And the last function is about ‘game over’.
