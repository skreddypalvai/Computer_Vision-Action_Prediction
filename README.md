# MonReader
### Background:
Our company develops innovative Artificial Intelligence and Computer Vision solutions that revolutionize industries. Machines that can see: We pack our solutions in small yet intelligent devices that can be easily integrated to your existing data flow. Computer vision for everyone: Our devices can recognize faces, estimate age and gender, classify clothing types and colors, identify everyday objects and detect motion. Technical consultancy: We help you identify use cases of artificial intelligence and computer vision in your industry. Artificial intelligence is the technology of today, not the future.

MonReader is a new mobile document digitization experience for the blind, for researchers and for everyone else in need for fully automatic, highly fast and high-quality document scanning in bulk. It is composed of a mobile app and all the user needs to do is flip pages and everything is handled by MonReader: it detects page flips from low-resolution camera preview and takes a high-resolution picture of the document, recognizing its corners and crops it accordingly, and it dewarps the cropped document to obtain a bird's eye view, sharpens the contrast between the text and the background and finally recognizes the text with formatting kept intact, being further corrected by MonReader's ML powered redactor.

![image](https://github.com/skreddypalvai/PE9nyrOMEtPAhrwc/assets/137756791/5233561a-854f-4abe-b9bb-3fb97becfb52)


 ### Objective:
 *  The main goal is to predict whether the page is being flipped using a single image.
 *  The trained model should achieve a high F1 score.


### Data Description:
 Initially, page flipping videos were gathered from smartphones. Subsequently, these videos were trimmed into shorter clips, and each clip was labeled as either "flipping" or "not flipping". The frames extracted from these clips were then saved into their respective image files. These image files contain both training images (flipping and not flipping) and test images (flipping and not flipping).

