Shuffle
=======

<a href="https://play.google.com/store/apps/details?id=com.github.florent37.florent.champigny">
  <img alt="Android app on Google Play" src="https://developer.android.com/images/brand/en_app_rgb_wo_45.png" />
</a>

[![API](https://img.shields.io/badge/API-10%2B-green.svg)][repo]
[![Build Status](https://travis-ci.org/Meetic/Shuffle.svg?branch=master)](https://travis-ci.org/Meetic/Shuffle)

An easy to use swiping-view for Android

[![intro](media/shuffle.gif)][repo]

# Usage

Just declare a Shuffle into your layout

```xml
<com.meetic.shuffle.Shuffle
      android:id="@+id/shuffle"
      android:layout_width="match_parent"
      android:layout_height="200dp"
      />
```

Then fill it with an Adapter
```java
Shuffle shuffle = (Shuffle)findViewById(R.id.shuffle);
shuffle.setShuffleAdapter(new Shuffle.Adapter(){
    @Override
    public Shuffle.ViewHolder onCreateViewHolder(ViewGroup viewGroup, int type) {

    }

    @Override
    public void onBindViewHolder(final Shuffle.ViewHolder viewHolder, int position) {

    }

    @Override
    public int getItemCount() {

    }
});
```

# Customisation
## Movements

### Free movements
[![intro](media/move.gif)][repo]

```xml
<com.meetic.shuffle.Shuffle
      android:id="@+id/shuffle"
      android:layout_width="match_parent"
      android:layout_height="200dp"
      app:shuffle_inlineMove="false"
      />
```

### Inline movements
[![intro](media/inline.gif)][repo]

```xml
<com.meetic.shuffle.Shuffle
      android:id="@+id/shuffle"
      android:layout_width="match_parent"
      android:layout_height="200dp"
      app:shuffle_inlineMove="true"
      />
```

## Orientation

If you want to set it vertical (by default Suffle is horizontal oriented)
```xml
<com.meetic.shuffle.Shuffle
     android:id="@+id/shuffle"
     android:layout_width="match_parent"
     android:layout_height="200dp"
     app:shuffle_orientation="horizontal / vertical"
     />
```

[![intro](media/vertical.gif)][repo]

## Rotation

Without rotation
```xml
<com.meetic.shuffle.Shuffle
     android:id="@+id/shuffle"
     android:layout_width="match_parent"
     android:layout_height="200dp"
     app:shuffle_rotationEnabled="false"
     />
```

[![intro](media/inline-rotation.gif)][repo]

With rotation

```xml
<com.meetic.shuffle.Shuffle
     android:id="@+id/shuffle"
     android:layout_width="match_parent"
     android:layout_height="200dp"
     app:shuffle_rotationEnabled="false"
     app:shuffle_rotation="10"
     />
```

[![intro](media/inline.gif)][repo]

## Restart

To restart the shuffling
```java
shuffle.restartShuffling();
```

[![intro](media/restart.gif)][repo]

## Revert

To undo a card exit
```java
shuffle.revert(duration);
```

[![intro](media/revert.gif)][repo]

## Infinite

```xml
<com.meetic.shuffle.Shuffle
     android:id="@+id/shuffle"
     android:layout_width="match_parent"
     android:layout_height="200dp"
     app:shuffle_infinite="true"
     />
```

[![intro](media/infinite.gif)][repo]

## Options

You can set the max number of cards displayed and adjust the space between cards

```xml
<com.meetic.shuffle.Shuffle
     android:id="@+id/shuffle"
     android:layout_width="match_parent"
     android:layout_height="200dp"
     app:shuffle_numberOfDisplayedCards="4"
     app:shuffle_differenceTranslationY="5dp"
     app:shuffle_differenceTranslationX="1dp"
     />
```

[![right](media/nbcards.png)][repo]

# Listeners

```java
shuffle.addListener(new Shuffle.Listener() {
            @Override
            public void onViewChanged(int position) {

            }

            @Override
            public void onScrollStarted() {

            }

            @Override
            public void onScrollFinished() {

            }

            @Override
            public void onViewExited(DraggableView draggableView, Direction direction) {

            }

            @Override
            public void onViewScrolled(DraggableView draggableView, float percentX, float percent) {

            }
        });
```

# CardDraggableView

```xml
<Shuffle
    ...
    //overlay color displayed while scrolling
    app:shuffle_colorRight="@color/blue"
    app:shuffle_colorLeft="@color/blue"

    //overlay content displayed while scrolling (ex: containing logo)
    app:shuffle_layoutLeft="@layout/bal_shuffle_cell_left"
    app:shuffle_layoutRight="@layout/bal_shuffle_cell_right"
    ...
    />
```

[![right](media/right.png)][repo]

# Animations

All Shuffle animations can be overriden
```java
shuffle.setViewAnimator(new ShuffleViewAnimator(){
            //override methods
});
```

Try `ShuffleViewAnimator` and `ShuffleViewAnimatorOnSecondCard

# ShuffleViewAnimator

You can easily set dismiss animations for `ShuffleViewAnimator` ( scaleUp / goBackBehind )

```java
shuffle.setViewAnimator(new ShuffleViewAnimator()
            .setPushLeftAnimateViewStackScaleUp(false)
            .setPushRightAnimateViewStackScaleUp(true)
            .setPushTopAnimateViewStackScaleUp(false)
            .setPushBottomAnimateViewStackScaleUp(false)
        );
```

# Enable

```java
shuffle.enable(true / false);
```

# Download

Add into your **build.gradle**

[ ![Download](https://api.bintray.com/packages/meetic-android/maven/Shuffle/images/download.svg) ](https://bintray.com/meetic-android/maven/Shuffle/_latestVersion)

```groovy
compile 'com.meetic.shuffle:shuffle:(last version)'
compile 'com.meetic.dragueur:dragueur:1.0.3'
```

Move your views with [Dragueur][Dragueur] !

#Log

1.0.8

- infinite

1.0.6

- revert

1.0.4

- Layer animations 

1.0.3

- ShuffleViewAnimator is now customisable

1.0.2

- added restart shuffling

# Credits

A project initiated by Meetic

This project was first developed by Meetic and has been open-sourced since. We will continue working on it.
We encourage the community to contribute to the project by opening tickets and/or pull requests.

[![logo meetic](media/meetic.jpg)][meetic]

Contributor: [Florent Champigny][florent]

<a href="https://play.google.com/store/apps/details?id=com.github.florent37.florent.champigny">
  <img alt="Android app on Google Play" src="https://developer.android.com/images/brand/en_app_rgb_wo_45.png" />
</a>

#License

    Copyright 2016 Meetic, Inc.

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.

[repo]: https://github.com/Meetic/Shuffle
[androidarsenal]: http://android-arsenal.com/details/--------
[meetic]: http://www.meetic.fr/
[dragueur]: https://github.com/Meetic/Dragueur
[florent]: https://github.com/florent37
