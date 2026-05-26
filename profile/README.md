_Ecdysis Foundation is all about grower-focused research to transform agriculture with regenerative principles._

Learn more about our organization at [ecdysis.bio](https://www.ecdysis.bio/)

![A bee from the Ecdysis Foundation Arthropod collection](/bee.jpeg)

Our open source applications primarily relate to the study of arthropod biodiversity using computer vision. A public collection of arthropods is avialble at [bugbox.ecdysis.bio](https://bugbox.ecdysis.bio/about/). This application's code, [bugbox_open](https://github.com/EcdysisFoundation/bugbox_open), is setup for hybrid deployment where computationally intensive methods, or integrations with computationally intensive services, happen on a local network using edge servers, while cloud/public access is also available through a Heroku instance.

![automated photography of field collected samples using a robotically controlled 35mm camera](/camera.png)

The process starts with automated photography of field collected samples in a lab setting. The repo [shimsy_open](https://github.com/EcdysisFoundation/shimsy_open) provides a user interface to manage the process of taking a grid of images of the samples. Next, the image grids are stitcher together using a FastAPI implementation of opencv's stithing module [stitcher](https://github.com/EcdysisFoundation/stitcher). We then perform instance segmentation using Ultralytics YOLO and Slicing Aided Hyper Inference for large images, see [ultralytics](https://github.com/EcdysisFoundation/ultralytics). After review of segmentation using cvat.ai, we crop and save the individual specimens to [bugbox_open](https://github.com/EcdysisFoundation/bugbox_open) and perform classificataion inference using our [inference-fastapi](https://github.com/EcdysisFoundation/inference-fastapi) deployment of our [metaformer_ecdysis](https://github.com/EcdysisFoundation/metaformer_ecdysis) model.

![A panorama image of insects in a tray, labeled with segmentation polygons](/PanoInsects.png)
