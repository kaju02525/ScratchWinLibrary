# Scratch-Win-Library Karun Kumar


# Usage
## Dependency:
 
 ```
 dependencies {
      implementation 'com.github.kaju02525:ScratchWinLibrary:0.1.0'
     }
 ```
 
 
 

## Features:

 - Scratch card effect to ANY view.
 - Just wrap your existing complex Layout with ScratchCardLayout.
 - CardView based library. So All styling of CardView is available.
 - Set scratch brush width.
 - Enable/Disable scratching effect
 - Set Drawable to be scratched (color / image).
 - Set the percentage of scratch when you should be revealing full layout.
 - Get callbacks when scratching starts, progresses (with a percentage) and when stops.
 
 
# Demonstration
|Demo scratchCardLayout|
|:---:|
|![](art/demoScratchCardLayout.gif)|
 
 ## XML Usage
 ```xml
  <com.winds.scratchcardlibrary.ui.ScratchCardLayout
         android:id="@+id/scratchCard"
         android:layout_width="250dp"
         android:layout_height="250dp"
         android:layout_centerInParent="true"
         app:scratchWidth="40dp"
         app:scratchEnabled="true"
         app:scratchDrawable="@drawable/your_drawable"
         app:scratchRevealFullAtPercent="100">
 
         <!--Your complex view here-->
  </com.winds.scratchcardlibrary.ui.ScratchCardLayout>     
 ```
 
 ## Java Usage
 ```java
        //Get view reference
        ScratchCardLayout scratchCardLayout = findViewById(R.id.scratchCard);
        
        //Set the drawable (programmatically)
        scratchCardLayout.setScratchDrawable(getResources().getDrawable(R.drawable.car));
        
        //Set scratch brush width
        scratchCardLayout.setScratchWidth(30f);
        
        //Reveal full layout when some percent of the view is scratched
        scratchCardLayout.setRevealFullAtPercent(40);
        
        //Scratching enable/disable
        scratchCardLayout.setScratchEnabled(true);
        
        //Remove all scratch made till now
        scratchCardLayout.resetScratch();
 ``` 
 
 ### Listeners available
          
Implement the given interface and override these stuff:

```java

          //Implement this to your class
          yourClass extends someBaseClass implements ScratchListener
          
          //Set the listener
          scratchCardLayout.setScratchListener(this);
            
          //You'll have three main callback methods as scratch listeners
          //Scratch started
          void onScratchStarted();
            
          //Scracth progress (NOTE: not guaranteed to be exact percent. consider it like atleast this much percent has been scratched)
          void onScratchProgress(ScratchCardLayout scratchCardLayout, int atLeastScratchedPercent);
            
          //Scratch completed
          void onScratchComplete();
  ``` 
