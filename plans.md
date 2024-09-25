# Platforms:

## Platforms
* iOS
* mac
* iPad?
Mac Universal or Mac catalyst? With swiftUI, both work. Catalyst is needed for linking into ARKit on mac possibly, but realitykit may be enough
# Modules:

The basic flow requires
1. **Foundation**: Defines the language between the modules
2. **Loader**: load 3D file for usage
3. **Angler**: Determines angle and position of the screen relative to the user's head
4. **Deformer**: Sets up transforms that positions the camera and accounts for screen warping
5. **Renderer**: generates the image to screen
6. Co-ordinator?
## Foundation:
Less functionality and more data types to be used between parts
* Maybe RealityKit will supply most of the data types?
## Loader:
Options:
* RealityKit might provide all
* Look into apple-supported 3d file formats, if the API can handle it
* Look into free/cheap rendering engines, which may support a file format like fbx
* Make own file parser
## Angler
Options:
* iOS/iPad: accelerometer/gyroscope to determine location of the head (assuming the viewer is directly above)
* iOS/iPad: arkit for tracking head
* Mac: Not sure if head tracking in arkit is available, but given other APIs, there might be one for recognizing faces
## Deformer
May need to delve into open source fishbox renderers, this is mostly math, maybe as simple as coming up with a matrix that does the work in rendering
## Renderer:
* Apple allows for realitykit for all OSes. That might be our renderer
* Maybe study Metal?

# Timeline:
1. Get realitykit sample source code
2. Learn to render on mac/ios/ipad
3. Create angler that is UI-based (IE, marking a point)
4. Research other tank engines and see if the deformer is already a solved instance
5. App should allow for deformation of a cube
6. iOS should support angler based on gyros?
7. See what Apple has for face and body tracking
8. Implement same to track angler
9. 

# Discoveries:
RealityKit and SwiftUI, both on all platforms, allow for our foundation
Look into the WebXR proposal to embed 3D objects into web pages


Start with rendering a solid object
Make it so that the object can be mutated

Looks like the only reliable starting point is metal, which uses more a UIKit layout. Putting it in SwiftUI requires UIKit handling

ARView also is a UIKit view

ARKit and RealityKit preseppose there's a captured camera scene source. Which won't work on mac.

May have to use non-arkit code to track head. Or keep to iphone?

https://modelviewer.dev might be a good start for sampling models

Look into making a safari plug-in

**Use Vision, not ARKit for MacOS, but RealityKit does**

https://en.wikipedia.org/wiki/Perspective_distortion?
https://www.mauriciopoppe.com/notes/computer-graphics/viewing/projection-transform/
https://www.scratchapixel.com/lessons/3d-basic-rendering/perspective-and-orthographic-projection-matrix/building-basic-perspective-projection-matrix.html

Don't forget that depth is important too, so use landmark in Vision.



Using VR goggles on mac maybe?
https://www.cgl.ucsf.edu/chimera/data/mac-vr-nov2018/mac-vr.html


Chording in ViewOS simulator?

https://openusd.org/release/index.html



988 Suicide and crisis lifeline
Crisis 741741 brave
1-800-273-8255
