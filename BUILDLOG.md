## 13 August 2026
- Created the GitHub repository.
- Set up the initial folder structure.
## 18 August 2026
- Understood the overall architecture and working of system
- Decided feeding mechanism: **rotational disc feeder + curved singulation guide + gravity chute**

 A rotating disc feeder with a curved singulation guide and gravity chute was selected for the initial prototype. The rotating disc provides controlled movement of the mixed objects, while the curved guide encourages single-item flow without requiring a tightly constrained escapement mechanism. Gravity is used for transport after singulation, eliminating the need for an additional conveyor motor.

- Made overall list of components needed ( did not check specifications yet)
  
## 19 August 2026
### Sorting mechanism
#### initial idea: 
-vertical stack (item free-falls straight down a shaft; each level has a trapdoor — closed by default drops it there, open lets it fall further)
- Would need 2 servos and a more coordination needed
#### better idea
- Rotating diverter: The item drops onto the trough, gravity slides it down the trough's slope, and it lands wherever the trough is currently pointed.

### JAM RECOVERY IDEA
-IR Break beam sensing: can fit an IR sensors near the feeder output  . If the IR beam is not broken for a long time , then the object is jammed in the feeder.
-Now the disc rotates in the opposite direction to recover from the jam.

### WHAT I DID?
- Finalised the overall working mechanism of the system
- Completed necessary block diagrams of circuit and connections.
- Analysed the required voltage/ current by each component
- Made detailed component list 
- Waiting for confirmation of the availability of components

  ### CHALLENGE
  - What if the items enter inspection area quicker than the sorting function, then multiple items will enter inspection area.
 
## 20 August 2026

### WHAT I DID?
- ML CV part: YOLOv8n object detection with three classes: Nut, Bolt, and Misc.
  #### WHY?
  - Multiple objects: YOLO can detect that 2+ objects arrived, whereas classical CV would need more hand-written rules.
  - Orientation: More robust when nuts/bolts are rotated
  - Lighting: Generally more robust to changes in lighting and appearance.
  - Misc: You can use a confidence threshold; low-confidence detections go to Misc.
  - Future-proof: If you later add more object types, you can retrain the model.

 - Analysed the communication and interfaces
  
