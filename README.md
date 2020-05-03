# Unity Workaround for KeepAnimatorControllerStateOnDisable

Workaround for Unknown Behaviour of KeepAnimatorControllerStateOnDisable

## What's happening?

In the following article, if you set `keepAnimatorControllerStateOnDisable` to `true` in the `Animator` GameObject, it will not work properly.

[Avatars - In-depth guide to animator inventory systems, logic, and syncing!](https://vrcat.club/threads/in-depth-guide-to-animator-inventory-systems-logic-and-syncing-w-unitypackage.2858/)

When the above property is enabled, the animation of the `Animator` GameObject is not played until the end of the game, and the animation stops playing at about half of the upper object's playback time.

## Workaround

In the higher GameObject, the playback time is set to about twice the animation playback time of the corresponding GameObject.  
For Example:

- Child GameObject has 0:30 + 0:01 animation, Parent GameObject set to 1:01 animation.
- Child GameObject has 0:05 animation, Parent GameObject set to 0:10 animation.

Alternatively, Enable animator component of the `Animator` GameObject from the beggining.
