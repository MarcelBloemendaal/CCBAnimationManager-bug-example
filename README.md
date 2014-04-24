CCBAnimationManager-bug-example
===============================

Example for a crash related to CCBAnimationManager. 

Steps to reproduce:

1. Launch project
2. Press the 'TestScreen' button. This pushes the TestScene on the CCDirector
3. Within 8 seconds, press the 'Back' button. This pops the TestScene from the CCDirector again.
4. Wait. (8 seconds max) The app crashes.


Presumable cause:

The CCBAnimationManager related to the TestScene is not properly cleaned up, and keeps playing the Default Timeline of the scene, that no longer exists. When the timeline ends, it will try to call a function and crash.
