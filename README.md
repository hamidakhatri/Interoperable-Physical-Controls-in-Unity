# Interoperable-Physical-Controls-in-Unity

## Overview
This project demonstrates the creation of interoperable controls within Unity, focusing on programming intuitive interactions for XR (Extended Reality) experiences. The project involves developing physical hand controls that enhance user experience by ensuring that interactions are intuitive and responsive.

The final product showcases a screencast that demonstrates the application correctly tracking hand movement input from XR controllers.

## Features
- Two hand avatars in the Unity scene.
- An interactable slider that responds to hand movements.
- XR controllers tracking hand movements and translating that movement to the on-screen avatars.
- On-screen avatar rotation and movements align with real-life hand movements.
- Hand avatars interacting with and manipulating the on-screen slider.

## What I Learned
1. Importance of Intuitive Interactions in XR
    - Intuitive interactions are critical in XR applications as they directly impact user satisfaction and immersion. Poorly designed controls can lead to frustration and disengagement.
    - Ensuring that interactions are consistent and predictable helps users understand how to interact with the virtual environment naturally.
2. Setting Up XR Components in Unity
    - I learned how to set up an XR Rig in Unity, which includes configuring XR controllers for tracking hand movements.
    - I gained experience in importing and setting up hand avatars and interactable objects, such as sliders, to create a cohesive XR experience.
3. Scripting for XR Interactions
    - Writing scripts to handle drag interactions and updating the position of interactable objects based on hand movements.
    - Using Unity Events to trigger actions based on interactions, such as starting and stopping drag interactions and updating UI elements.

## Troubleshooting and Solving Issues
Issue 1: The simulation would hang when attempting to grab the slider, indicating a potential infinite loop or excessive computational load.

Solution:
- I identified that the issue was likely caused by the CalculateDrag coroutine not yielding control properly, leading to an infinite loop.
- I ensured that the coroutine correctly yielded control using yield return null within the while loop to prevent hanging.

Issue 2: The hand avatars were not updating their positions and rotations correctly, causing misalignment with the real-life hand movements.

Solution:
- I double-checked the configuration of the XR Rig and ensured that the controllers were correctly set up to track hand movements.
- I ensured that the hand avatars were correctly parented to the XR Rig and that their transforms were being updated correctly in the script.

Issue 3: The slider did not move as expected when interacting with the hand avatars.

Solution:
- I reviewed the DragInteractable and Slider scripts to ensure that the drag percentage was being calculated and applied correctly.
- I verified that the onDragUpdate event in the DragInteractable script was correctly connected to the UpdateSlider method in the Slider script within the Unity Editor.
