#animate-functions.sass

##What is animate-functions.sass?##
It's a collection of configurable CSS animations using SASS mixins.

##Bower Package
```
$ bower install animate-functions.sass --save
```
##Why is useful?
#### Functions or Classes
You can Include the animations as part of a new CSS rule-set or use them by adding classes to the markup:
```sass
//Including animations as part of a CSS rule-set
.page-home.ng-enter{
    @include af-slideInDown();
    z-index: 2;
}

.page-home.ng-leave{
    @include af-slideOutUp();
    z-index: 1;
}

// Using animation by adding a class to the markup
<h1 class="af-flipInX">This is a title</h1>
```

#### Configurability
You can easily define the duration and delay of each animation:
```sass
.page-home.ng-enter{
// The first parameter defines the duration and the second one the delay
    @include af-slideInDown(1s, 3s);
    z-index: 2;
}
```
If you call the functions without any parameter, the default values will be used (1s duration, 0s delay).

In case you want to modify the default values you just need to override them by defining the **$animateDefaultDuration** and **$animateDefaultDelay**.

#### Modularization
Each animation is defined in an individual SASS file (they are grouped in folders by family type). This allows you to include only the animations that you are going to use, for example:

```sass
@import "yourSassFolder/animate-functions.sass/af-base";

@import "yourSassFolder/animate-functions.sass/functions/attention-seekers/af-bounce";
@import "yourSassFolder/animate-functions.sass/functions/attention-seekers/af-flash";
```
##How to use it?
It's very simple:
* Include af-base.scss
* Define $animateDefaultDuration and $animateDefaultDelay if you want to override the default duration and delay values (Optional)
* Include the animations that you want ex: functions/bouncing-exits/af-bounceOut.scss

```sass
@import "yourSassFolder/animate-functions.sass/af-base";

// Override Default Values
@animateDefaultDuration: 1s;
@animateDefaultDelay: 0;

@import "yourSassFolder/animate-functions.sass/functions/bouncing-exits/af-bounceOut.scss";
```

Done! Now you can Include the animations as part of a new CSS rule-set or use them by adding classes to the markup:
```sass
//Including animations as part of a CSS rule-set
.page-home.ng-enter{
    @include af-bounceOut();
}


// Using animation by adding a class to the markup
<h1 class="af-bounceOut">This is a title</h1>
```
