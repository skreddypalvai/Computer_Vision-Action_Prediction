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

### Project Overview:
* The main goal of this project is to use deep learning techniques, specifically Convolutional Neural Networks (CNNs), to accurately determine if a given image page is being flipped or not.
* I adjusted the image size to 120x120 and examined both the flipping and not flipping page images of the training set to determine whether image data augmentation is necessary.

Flipping Images: 

![download](https://github.com/skreddypalvai/s3Ho4t5iMRItcowM/assets/137756791/1b603ac2-63e8-46aa-b880-8365cc14957b)

Not Flipping Images:

![download](https://github.com/skreddypalvai/s3Ho4t5iMRItcowM/assets/137756791/f3c615a2-feb5-4e68-aaff-d059321be8c4)

* We can see that the pictures are taken one after another in the same setting, so it's clear that the natural differences in the data are already well-captured. Therefore, there's no need for extensive image data enhancement in this scenario.
* I used the `image_dataset_from_directory` function from TensorFlow to split the training data into 80% for training and 20% for validation. This function ensures that there is no overlap between the training and validation sets, preventing data leakage between the two sets.


![download](https://github.com/skreddypalvai/s3Ho4t5iMRItcowM/assets/137756791/751e0337-601a-46e3-bd93-bab87b4aace8)

### Key Results:

1. Convolution Neural Networks(CNN):
   *  After preparing the image data and training with 1,441,025 CNN model parameters, the CNN model achieved a good validation loss and accuracy.
      ![download](https://github.com/skreddypalvai/s3Ho4t5iMRItcowM/assets/137756791/289d1e09-55e6-4ec7-904d-d19ebe27514b)
      ![download](https://github.com/skreddypalvai/s3Ho4t5iMRItcowM/assets/137756791/41789fe5-5287-4ea7-8f54-02b96e5c6434)
   *  After testing the trained CNN model on the test set, the model achieved the highest accuracy and the lowest loss scores.
      ![download](https://github.com/skreddypalvai/s3Ho4t5iMRItcowM/assets/137756791/2fc65584-6cb2-4f53-9904-497d7cff6d3b)
   *  The confusion matrix shows that the model correctly classified 583 out of 597 images, achieving a high F1 score of 98%.
      ![download](https://github.com/skreddypalvai/s3Ho4t5iMRItcowM/assets/137756791/2022477e-d92d-44a3-9163-c2c18f4daf76)
      ![download](https://github.com/skreddypalvai/s3Ho4t5iMRItcowM/assets/137756791/73e46d6b-6754-4529-92ef-ae893d13f729)
   *  Randomly predicting five sets of test images showed that four were accurately identified as showing a flipping action, showcasing the model's commendable predictive capabilities.
     
   ![download](https://github.com/skreddypalvai/s3Ho4t5iMRItcowM/assets/137756791/dafc9ac6-f7e2-4049-bedf-f6e1a6d93f08) ![download](https://github.com/skreddypalvai/s3Ho4t5iMRItcowM/assets/137756791/a122741d-7421-41e3-a443-013639bbb6b8)
   ![download](https://github.com/skreddypalvai/s3Ho4t5iMRItcowM/assets/137756791/a6eaaf7f-955a-411a-bab2-25e70454b06c) ![download](https://github.com/skreddypalvai/s3Ho4t5iMRItcowM/assets/137756791/e7485159-c7d6-455d-ba2d-f1b52772be71)

2. CNN-Recurrent Neural Networks(sequence analysis):
   *  We're sure that the given images come from video frames, and analyzing the sequence is the best way to check if there's any flipping action in a given image.We can achieve this using a CNN-RNN model.I prepared the data with a sequence length of 3:
      ![download](https://github.com/skreddypalvai/s3Ho4t5iMRItcowM/assets/137756791/2a5de8a2-8632-4217-8c95-ccd91b2076eb)
   *  A CNN-RNN model with 1,470,209 parameters was trained on the sequence data, achieving an optimal validation loss and accuracy.
    ![download](https://github.com/skreddypalvai/s3Ho4t5iMRItcowM/assets/137756791/ed719e8b-5759-4076-9725-a2705b73b580)
    ![download](https://github.com/skreddypalvai/s3Ho4t5iMRItcowM/assets/137756791/0a0b3cdf-6215-4bb9-afb6-cf3b1b708ca3)

   *  After testing, the model achieved an impressive 99% accuracy and a maximum F1 score of 99% on the respective test set. It also accurately predicted the true label.
      ![image](https://github.com/skreddypalvai/s3Ho4t5iMRItcowM/assets/137756791/d2e3baa1-0248-4b67-ac57-c1038bbbcbfd)
      ![download](https://github.com/skreddypalvai/s3Ho4t5iMRItcowM/assets/137756791/71c2ff24-c2ef-45fb-8c05-b445cf022357)

 





