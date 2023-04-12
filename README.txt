MODEL
- In the model, we implemented the interfaces for the layer and project and chose appropriate
  data representation to be used throughout the code.

VIEW
- In the view we created a visual representation of a model of collaging and created a view Object
  for a command line based collaging project. We also added a JFrameView where we constructed a
  GUI using the Swing framework. This allowed us to create various buttons and drop-down menu
  for the users to interact with to upload, save, and create images.

CONTROLLER
- The controller is where we implemented all of our methods.
- These methods include loading the image, selecting the current commands, creating a new project,
  returning a project, loading a project, saving a project, saving a layer as a ppm file, adding
  a layer, placing an image on a layer, setting a filter, saving an image, quitting a project,
  and rendering the layer/filter type commands.

TESTS
- In the test file, we tested all our methods and various cases of it to ensure it is running.
  We also test each of the classes we made in the controller (layer, pixel, and project)

SCRIPT OF COMMANDS
1. to create a new project type --> new-project 800 600
2. to add a new layer type --> add-layer layerName
3. to add an image to a layer type --> add-image-to-layer layerName images/tako.ppm
4. to set a certain filter type with red-component --> set-filter layerName red-component
5. to save an image type --> save-image image.ppm
6. to save a project type --> save-project
7. to load a project type --> load-project image.Project
8. to quit type --> quit
9. to open the script file, execute it and then shut down --> java -jar Program.jar -file path-of-
script-file
10. to open the interactive text mode --> java -jar Program.jar -text
11. to open the graphical user interface --> java -jar Program.jar

DECOUPLING OF THE VIEW
1. Other than the unnecessary interface such as the ones for LayerInterface, PixelInterface,
   CommandPanelInterface, ImagePanelInterface, and JFrameViewInterface the rest of the remaining
   interfaces and classes are necessary for the code to compile and work accurately.
2. Model:
   - Removed all unnecessary interfaces, and kept the only veiled one for the Project class.
   - Added the method addLayersFromImage, lowestByte, and loadProjectFromImage.
   - Changed combineAllLayers method, so it does not have a set size.
   - Relocated the covertBufferImageToLayer from the view to the model.
   View:
   - Removed all unnecessary interfaces, and kept the only veiled one for the
     CollagingCommandView and Textui  class.
   - Create two separate files in the view for GUI’s and TextUI.
   - In the Textui class, re-located the readCommand method and the getCurrentCommand method
     from the imageController class.
   - Created Textui class and its interfaces TextuiIn.
   Controller:
   - Modified the runner, so it changes instances of readCommand in order for the code to call it
     from the view instead of the controller.
   - Added textui to the controller, so it reconizes the code in the view.
   - Removed readCommand method from imageController class.

Citation: we own the image, and we're authorized to use the image for the project