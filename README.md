# Computer Vision: Final-Semester Study Guide

**Six lecture files combined into one exam-focused reference**

These notes use simple language and give enough detail to build full answers for short-answer and long-answer questions. They follow the six supplied PDFs: Unit 1, Unit 2, Unit 3, Image Segmentation, Unit 5, and Unit 6. The guide explains the idea first, then gives the working steps, advantages, limitations, applications, and exam points.

## Contents

1. [Unit 1: Computer Vision Foundations](#unit-1-computer-vision-foundations)
2. [Unit 2: Image Processing Fundamentals](#unit-2-image-processing-fundamentals)
3. [Unit 3: Feature Detection and Extraction](#unit-3-feature-detection-and-extraction)
4. [Additional Lecture: Image Segmentation and Related Methods](#additional-lecture-image-segmentation-and-related-methods)
5. [Unit 5: Deep Learning in Computer Vision](#unit-5-deep-learning-in-computer-vision)
6. [Unit 6: Motion Analysis and Applications](#unit-6-motion-analysis-and-applications)
7. [Comparison Tables for Fast Revision](#comparison-tables-for-fast-revision)
8. [Important Formulas and Terms](#important-formulas-and-terms)
9. [Final-Exam Practice Questions](#final-exam-practice-questions)
10. [Quick Revision Sheet](#quick-revision-sheet)

## How to study from this guide

For a **2-mark answer**, write a clear definition and one important point or example. For a **5-mark answer**, explain the definition, principle, steps, and one or two advantages or applications. For a **long answer**, add a labelled flowchart or kernel where relevant, explain each step in order, compare the method with alternatives, and finish with applications and limitations.

When a question asks you to *differentiate* two topics, use a table. When it asks you to *explain an algorithm*, write the steps in order. When it asks you to *discuss applications*, connect each application to what the method actually does. Memorising only the one-line definitions will not prepare you for long-answer questions.

---

# Unit 1: Computer Vision Foundations

## 1.1 What is Computer Vision?

**Computer Vision (CV)** is a field of Artificial Intelligence that helps computers interpret and understand images, video frames, and other visual data. It converts pixel values into useful information, such as object labels, locations, movement, or decisions.

A computer does not understand an image merely because it can store or display it. Computer Vision applies algorithms to work out what the image contains and what that information means.

**Example:** A camera captures an image of a road. A Computer Vision system can identify cars, pedestrians, lane markings, and traffic signs. A vehicle can then use these results to make driving decisions.

### Why is Computer Vision important?

- It automates tasks that normally require visual inspection.
- It can process large numbers of images and video frames.
- It supports robotics, healthcare, surveillance, autonomous vehicles, manufacturing, agriculture, retail, and augmented reality.
- It can recognize patterns that are difficult to describe with simple hand-written rules.

## 1.2 Computer Vision, Image Processing, and Artificial Intelligence

**Image Processing** changes or improves an image. **Computer Vision** uses visual information to understand what is present. Image Processing often prepares an image before a Computer Vision model analyzes it. Both are commonly parts of one system.

| Point | Image Processing | Computer Vision |
|---|---|---|
| Main purpose | Improve, transform, restore, or prepare an image | Interpret visual content and produce meaningful information |
| Typical input | An image | An image, video, or other visual data |
| Typical output | Another image | Labels, coordinates, masks, motion estimates, or decisions |
| Common techniques | Filtering, sharpening, denoising, thresholding, enhancement | Detection, classification, feature analysis, tracking, machine learning, deep learning |
| Example | Make a dark CCTV frame clearer | Detect a person in that frame |

**Example of both working together:** First, software removes noise from a night-time camera image and improves its contrast. A vision model then detects a person near a door. The first stage improves the pixels; the second interprets them.

Computer Vision is related to several other fields:

- **Machine Learning and Deep Learning:** provide models that learn patterns from data.
- **Pattern Recognition:** studies how to classify patterns and assign categories.
- **Computer Graphics:** creates images from models, while Computer Vision studies images to infer information about the scene.
- **Robotics:** uses vision to perceive the environment, navigate, and manipulate objects.

## 1.3 Human Vision versus Computer Vision

| Aspect | Human Vision | Computer Vision |
|---|---|---|
| Input | Light sensed by the eyes and retina | Pixel data from a camera or image file |
| Processing | Biological neural pathways and the brain | Algorithms running on a CPU, GPU, or specialised hardware |
| Learning | Develops through experience and context | Uses programmed rules and models trained on data |
| Handling changes | Often handles lighting, partial obstruction, and unfamiliar scenes well | Can fail when lighting, viewpoint, or data differs from training conditions |
| Scale | A person usually attends to a limited scene at a time | A system can process many images automatically and in parallel |

Human vision is not identical to Computer Vision. A computer may process a very large number of images quickly, but it can still misunderstand an unfamiliar scene or an image with poor lighting.

## 1.4 Evolution of Computer Vision

| Period | Main development described in the lecture notes |
|---|---|
| 1960s | Early research tried to describe scenes symbolically as part of Artificial Intelligence. |
| 1970s to 1980s | Researchers developed edge detectors, basic feature extraction, and early stereo-vision methods. |
| 1990s | Statistical methods, Eigenfaces for face detection/recognition research, and feature descriptors became important. |
| 2000s | Hand-crafted features such as SIFT and HOG were combined with classifiers such as SVMs. |
| 2012 onward | Deep learning became a major turning point after AlexNet achieved strong results on ImageNet. |
| 2015 to 2020 | Region-based object detectors, segmentation networks, and real-time detectors such as YOLO and SSD became prominent. |
| 2020 onward | Vision Transformers, self-supervised learning, and multimodal vision-language models expanded the field. |

**Main idea to remember:** Earlier systems relied heavily on features that people designed manually. Modern deep-learning systems can learn useful visual representations from training data.

## 1.5 Core Tasks in Computer Vision

### Image classification
Classification assigns a label to an entire image. For example, a model may classify an image as *cat*, *dog*, or *car*. It does not necessarily say where the object appears.

### Object detection
Detection identifies objects and estimates their locations. It typically returns a class label, a confidence score, and a bounding box for every detected object.

### Semantic segmentation
Semantic segmentation assigns a class label to every pixel. For example, it may label pixels as road, sky, tree, or pedestrian. It does not necessarily distinguish two separate objects that belong to the same class.

### Instance segmentation
Instance segmentation labels object pixels and separates individual objects. For example, it can label Person 1 and Person 2 as separate instances.

### Object tracking
Tracking follows an object across multiple video frames and tries to maintain its identity as it moves.

### Other tasks

- **Pose estimation:** estimates the position or orientation of an object, or the locations of human body joints.
- **Action recognition:** identifies an action or activity from visual data over time.
- **3D vision and depth estimation:** estimates depth or reconstructs three-dimensional structure from visual observations.
- **Image registration:** aligns two or more images, such as medical images captured at different times.
- **Image generation and synthesis:** creates or modifies visual content, including inpainting, style transfer, and super-resolution.

## 1.6 Scope of Computer Vision

The technical scope can be grouped into four levels:

1. **Low-level vision:** improves or describes raw image information. Examples include filtering, denoising, enhancement, edge detection, and feature extraction.
2. **Mid-level vision:** groups image information and estimates structure or movement. Examples include segmentation, motion estimation, and geometric reconstruction.
3. **High-level vision:** interprets objects and scenes. Examples include object recognition, scene understanding, and semantic interpretation.
4. **Cross-modal vision:** combines visual information with text, audio, or other sensor data.

## 1.7 Applications of Computer Vision

- **Healthcare:** analyze X-rays, MRI, CT, ultrasound, retinal images, and pathology slides; support tumour detection, screening, surgical guidance, and patient monitoring.
- **Autonomous vehicles:** detect lanes, traffic signs, pedestrians, vehicles, and obstacles.
- **Robotics:** recognize objects, navigate, estimate position, and guide robotic arms.
- **Security and surveillance:** detect people, monitor restricted areas, track vehicles, and identify unusual activity.
- **Retail:** support visual search, automated checkout, inventory monitoring, and virtual try-on.
- **Manufacturing:** inspect products, identify defects, check component alignment, and guide robot picking.
- **Agriculture:** monitor crop health and identify possible weeds, pests, or disease patterns.
- **AR/VR:** track features and camera motion so virtual objects stay aligned with the real environment.
- **Remote sensing:** analyze satellite images for land-cover classification and change detection.

### Computer Vision in healthcare

Computer Vision can assist healthcare professionals by extracting useful patterns from medical images. Examples from the lecture notes include:

- **Radiology:** detect suspicious patterns in X-rays and other scans, such as possible tumours, fractures, or pneumonia.
- **Retinal screening:** analyze retinal photographs for signs of eye disease.
- **Digital pathology:** inspect digitized microscope slides and support the analysis of tissue samples.
- **Surgical assistance:** track surgical instruments or support image-guided procedures.
- **Patient monitoring:** analyze movement, posture, or falls.
- **Research:** analyze biological images and experimental results.

Healthcare models need careful validation, representative data, privacy protection, and suitable human oversight. The model should support qualified professionals, not automatically replace clinical judgement.

## 1.8 Computer Vision in Surveillance

A surveillance system uses cameras to observe a place. A smart surveillance system adds Computer Vision so software can analyze the video and detect events without requiring a person to watch every frame.

### Main stages of a smart-surveillance system

1. **Image acquisition:** capture video using CCTV, IP, thermal, infrared, or drone cameras, depending on the environment.
2. **Image preprocessing:** reduce noise, adjust contrast, resize frames, and convert color spaces when useful.
3. **Motion detection:** identify changes with frame differencing, background subtraction, or optical flow.
4. **Object detection:** locate people, vehicles, or other target objects and draw bounding boxes around them.
5. **Object tracking:** connect detections across frames so the system can follow the same person or vehicle.
6. **Face detection:** find face regions in images or video frames.
7. **Face recognition:** extract facial features and compare them with stored data when the system has an authorized identification task.
8. **Human activity recognition:** analyze movement over time to classify activities or predefined actions.
9. **Crowd analysis:** estimate crowd size, density, flow, or unusual crowding.
10. **Automatic number-plate recognition (ANPR):** locate a vehicle, find its number plate, separate or read the plate characters using OCR, and optionally compare the result with a database.
11. **Decision and output:** create an alert, event log, report, or control signal when the system detects a defined event.

### Example: restricted-area intrusion detection

A camera captures a video frame. Preprocessing improves the image if necessary. Motion detection identifies a change, an object detector locates the person, and a tracker follows the person across frames. If the tracked person enters a restricted region, the system generates an alert. The alert depends on multiple stages, so an error in detection or tracking can affect the final decision.

### Applications and challenges

Surveillance supports intrusion detection, traffic monitoring, vehicle tracking, abandoned-object detection, crowd monitoring, and industrial safety. Common challenges include poor lighting, shadows, weather, occlusion, camera motion, compute requirements, privacy, and bias. Automated results should be evaluated carefully, especially when they affect people.

## 1.9 Key Challenges in Computer Vision

- **Variation in appearance:** the same object can look different because of scale, viewpoint, lighting, or deformation.
- **Occlusion:** another object may hide part of the target.
- **Data requirements:** many deep-learning methods need large, accurately labelled datasets.
- **Generalization and domain shift:** a model trained in one setting may perform poorly in a different environment.
- **Computational cost:** high-accuracy systems may require substantial processing power.
- **Adversarial vulnerability:** small changes to an image may mislead a model.
- **Ethical concerns:** privacy, surveillance misuse, unfair bias, and unequal error rates require attention.

## 1.10 Components of a Computer Vision System

A vision system uses hardware and software to capture an image, prepare it, interpret it, and act on the result.

| Component | Purpose | Example |
|---|---|---|
| Camera or image-acquisition device | Captures the scene | A camera records fruit on a conveyor belt. |
| Lighting system | Makes important details visible | Backlighting makes cracks in a glass bottle easier to see. |
| Lens | Focuses light onto the sensor | A magnifying lens helps inspect small electronic parts. |
| Image sensor | Converts incoming light into a signal and image data | CCD or CMOS sensor |
| Frame grabber / capture hardware | Transfers, buffers, or synchronizes image data | High-speed industrial image capture |
| Processing unit | Runs the algorithms | CPU, GPU, FPGA, or embedded processor |
| Image-processing software | Improves or prepares the image | Denoising, resizing, contrast enhancement, thresholding |
| Feature extraction / image analysis | Measures useful image properties | Shape, size, color, texture, edges, and corners |
| Pattern-recognition module | Classifies or recognizes what appears | Template matching, machine learning, or deep learning |
| Communication interface | Sends information to other devices | Ethernet, USB, Wi-Fi, or industrial interfaces |
| Output / control system | Acts on the result | Alarm, robot control, or product rejection |
| Database and storage | Keeps images, results, and logs | Quality-control records and model-training data |

### Block diagram to practise

```text
Object / Scene
      ↓
Lighting System
      ↓
Lens
      ↓
Camera + Image Sensor
      ↓
Frame Grabber / Image Capture
      ↓
Processing Unit
      ↓
Image Processing
      ↓
Feature Extraction
      ↓
Pattern Recognition
      ↓
Decision Making
      ↓
Output / Control System
```

**Example: automatic fruit sorting**

1. Fruit moves along a conveyor belt.
2. A camera captures its image under suitable lighting.
3. Software cleans or prepares the image.
4. The system extracts color, shape, and size.
5. A recognition module identifies the fruit type.
6. A control system directs the fruit into the correct container.

## 1.11 Digital Image Fundamentals

A digital image represents a scene using numerical values. A common mathematical notation is `I(x, y)`, where `x` is the horizontal position, `y` is the vertical position, and the value stores brightness or color.

### Pixel
A **pixel** is the smallest picture element in a digital image. A digital image arranges pixels in rows and columns.

In a common 8-bit grayscale image, pixel values range from 0 to 255:

- `0` means black.
- `255` means white.
- Values between them represent shades of gray.

### Types of digital images

- **Binary image:** uses two values, usually 0 and 1. Applications include document processing and barcode recognition.
- **Grayscale image:** stores brightness rather than separate color channels.
- **Color image:** commonly stores red, green, and blue channel values for each pixel.

### Resolution
Image resolution describes the number of pixels in the image, usually written as width × height. For example, an image with dimensions 1920 × 1080 contains 1920 columns and 1080 rows of pixels. More pixels can preserve more spatial detail, but they also increase storage and processing requirements.

**DPI** means dots per inch and describes a print or output density. Do not confuse physical print density with the pixel dimensions of an image file.

### Color models

| Model | Meaning | Typical use |
|---|---|---|
| RGB | Red, Green, Blue channels | Digital cameras, monitors, phones, and displays |
| Grayscale | One brightness value per pixel | Medical images and many inspection tasks |
| HSV | Hue, Saturation, Value | Color-based analysis where separating color from brightness can help |
| CMYK | Cyan, Magenta, Yellow, Black | Printing and publishing |
| YCbCr | Luma/brightness plus blue- and red-difference chroma information | Image and video compression and broadcasting |

Common RGB examples for 8-bit channels are `(255, 0, 0)` for red, `(0, 255, 0)` for green, `(0, 0, 255)` for blue, `(255, 255, 255)` for white, and `(0, 0, 0)` for black. RGB combines light, while CMYK combines printer inks.

## 1.12 Pinhole Camera Model: Source Coverage Note

The Unit 1 topic list mentions **image formation and the pinhole camera model**, but the supplied PDF text does not provide a full explanation, diagram, or equations for that topic. These consolidated notes therefore do not invent a detailed derivation. Review the corresponding classroom slides or textbook pages if your syllabus expects a detailed pinhole-camera answer.

---

# Unit 2: Image Processing Fundamentals

## 2.1 What is Image Processing?

Image Processing applies operations to an image to improve its appearance or prepare it for further analysis. It can reduce noise, adjust contrast, sharpen details, transform geometry, detect edges, or separate regions.

A common pipeline is:

```text
Input Image → Preprocessing / Enhancement → Filtering or Transformation → Analysis or Output
```

## 2.2 Image Representation, Sampling, and Quantization

### Image representation
A digital image stores pixel intensity or color values in a two-dimensional grid. A grayscale pixel stores brightness; a color pixel often stores separate RGB channel values.

### Sampling
**Sampling** converts a continuous visual scene into a discrete grid of pixel locations. It mainly determines the spatial resolution.

- Too few samples can remove fine details and distort shapes.
- More samples generally preserve more detail, but require more storage and processing.

### Quantization
**Quantization** assigns a finite set of intensity values to each sampled pixel. It determines how finely the system represents brightness or color intensity.

If a pixel channel uses `b` bits, the number of possible levels is `2^b`. For example, 8-bit grayscale has 256 possible levels, numbered 0 through 255. With fewer levels, smooth brightness changes may appear as visible bands. The difference caused by mapping an actual value to an allowed level is called **quantization error**.

| Point | Sampling | Quantization |
|---|---|---|
| Main question | Where should the image measure values? | Which values can each pixel store? |
| Controls | Spatial resolution | Intensity resolution |
| Common unit | Pixel dimensions | Bits or intensity levels |
| Too little | Loss of spatial detail | Coarse brightness levels and banding |

**Example:** `1920 × 1080` describes the sampled pixel grid. `8-bit grayscale` describes the available brightness levels for each pixel.

## 2.3 Image Enhancement

Image enhancement makes important image information easier to see or use. Different methods solve different problems.

### Contrast enhancement
Contrast enhancement increases the difference between darker and brighter image regions. It can make hidden details easier to distinguish.

### Histogram equalization
An image histogram shows how many pixels have each intensity. Histogram equalization redistributes intensities to make better use of the available range. It can improve global contrast, especially when many pixels occupy a narrow intensity range.

### Noise reduction
Noise reduction removes unwanted pixel variations introduced by sensors, low light, or transmission. Gaussian smoothing and median filtering are common examples.

### Sharpening
Sharpening emphasizes edges and fine details. It can improve clarity, but it may also make noise more visible.

## 2.4 Image Transformations

Geometric transformations change the positions or dimensions of image content.

| Transformation | Simple meaning | Example use |
|---|---|---|
| Scaling | Increase or decrease image size | Resize an image before analysis |
| Rotation | Turn an image around a selected point | Correct a tilted document |
| Translation | Shift an image horizontally or vertically | Align two images |
| Affine transformation | Combine rotation, scaling, translation, and shearing | Correct certain geometric changes while preserving parallel lines |
| Perspective / projective transformation | Change the apparent viewpoint or perspective | Straighten a photographed page or planar object |

Resizing and rotation often need **interpolation**, which estimates pixel values at locations that do not coincide with original pixels. The notes name nearest-neighbor and bilinear interpolation as examples.

## 2.5 Pixel-Based Transformations

A pixel transformation changes pixel values directly. In a point transformation, each output pixel depends on the corresponding input pixel, rather than on a whole neighborhood.

### Linear transformation
A common form is:

`g(x, y) = a f(x, y) + b`

- `f(x, y)` is the original pixel value.
- `g(x, y)` is the output pixel value.
- `a` controls contrast scaling.
- `b` shifts brightness.

**Worked example:** if the original pixel is 100, `a = 2`, and `b = 20`, then the new value is `(100 × 2) + 20 = 220`. Real systems must keep values within the allowed intensity range.

### Non-linear transformations

- **Image negative:** reverses light and dark intensity levels.
- **Log transformation:** expands details in darker intensity regions and compresses higher values.
- **Gamma / power-law correction:** changes the intensity mapping non-linearly; the gamma parameter controls how strongly the mapping changes dark and bright values.
- **Histogram equalization:** uses the intensity distribution of the image to improve contrast.
- **Thresholding:** assigns pixels to different groups based on intensity.

## 2.6 Spatial-Domain Filtering

The **spatial domain** is the ordinary image grid. A spatial filter operates directly on pixel values. The general idea can be written as:

`g(x, y) = T[f(x, y)]`

Here, `f` is the input image, `g` is the output image, and `T` is the operation applied at or around pixel `(x, y)`.

### Point processing versus neighborhood processing

- **Point processing:** uses only the current pixel. Examples include negative, gamma correction, and thresholding.
- **Neighborhood processing:** uses a small area around the current pixel. Examples include mean, Gaussian, median, and edge-detection filters.

### What is a kernel or mask?

A **kernel** is a small matrix of numbers that moves over the image. At each location, the algorithm combines the kernel values with the underlying pixel values. This produces the output for that location.

A 3 × 3 kernel covers nine pixels. A smoothing kernel may average them, while an edge kernel responds to intensity differences.

### Correlation and convolution

- **Correlation:** slides the kernel over the image without rotating the kernel first.
- **Convolution:** rotates the kernel by 180 degrees before applying it.

Symmetric kernels, such as many smoothing kernels, can produce the same result in both operations. In image-processing explanations, always state which convention you use if the exact kernel signs matter.

### Padding at image boundaries

A kernel can extend beyond an image edge. Padding defines what the algorithm should assume outside the image.

- **Zero padding:** treats outside pixels as zero. It can create dark borders.
- **Replicate padding:** copies the nearest border pixel.
- **Mirror/reflect padding:** reflects the image content across the border.
- **Cropping:** calculates only where the full kernel fits, so the output becomes smaller.

### Main classes of spatial filters

Filters can be classified in two ways:

1. **By operation:** linear filters combine weighted pixel values; non-linear filters use other rules such as sorting neighborhood values.
2. **By effect:** smoothing filters reduce local variation; sharpening filters emphasize rapid changes and details.

## 2.7 Smoothing Filters

Smoothing reduces noise and small variations. It can also blur edges and remove fine detail, so the choice of filter matters.

### Mean or box filter
The mean filter replaces the center pixel with the average of the pixels in its neighborhood. For a 3 × 3 box filter, all nine pixels receive equal weight, usually `1/9` each.

**Advantages:** simple and fast; useful for general smoothing.

**Limitations:** blurs edges and fine detail because it averages unlike values together.

### Weighted-average filter
A weighted-average filter gives different importance to different pixels. The source shows this 3 × 3 kernel, scaled by `1/16`:

```text
1  2  1
2  4  2
1  2  1
```

The center receives the greatest weight. This can smooth the image while reducing some of the excessive blurring associated with a uniform box filter.

### Gaussian filter
The Gaussian filter assigns weights according to a Gaussian distribution. Pixels near the center receive larger weights; distant pixels receive smaller weights. The standard deviation, often written as `σ`, controls the amount of smoothing. Larger `σ` generally produces stronger blur.

Gaussian smoothing often serves as a preprocessing step before edge detection because noise can otherwise create false edges.

### Median filter
The median filter sorts the neighborhood's pixel values and replaces the center with the middle value. It does not compute a weighted average.

It works particularly well for **salt-and-pepper noise**, where some pixels suddenly become very bright or very dark. Because it rejects extreme outlier values instead of averaging them, it often preserves edges better than a mean filter.

### Maximum and minimum filters

- **Maximum filter:** replaces the center with the largest neighborhood value. It can suppress dark impulse noise and emphasize bright points.
- **Minimum filter:** replaces the center with the smallest neighborhood value. It can suppress bright impulse noise and emphasize dark points.

### Smoothing-filter comparison

| Filter | How it works | Best-known use | Main limitation |
|---|---|---|---|
| Mean | Average of neighborhood | Simple general smoothing | Strong edge blur |
| Weighted average | Weighted sum, with greater weight near the center | Smoother result than a uniform average of similar size | Still blurs edges |
| Gaussian | Gaussian-shaped weighted average | Smooth preprocessing and Gaussian-like noise | Can remove fine detail |
| Median | Middle value after sorting | Salt-and-pepper noise | May remove small details when the neighborhood or noise level is too large |
| Maximum | Largest neighborhood value | Reduce dark specks, emphasize bright features | Expands bright regions or details |
| Minimum | Smallest neighborhood value | Reduce bright specks, emphasize dark features | Shrinks bright regions or details |

## 2.8 Sharpening Filters

Sharpening makes edges and fine detail more visible. It works by emphasizing rapid intensity changes. The same process can also strengthen noise because noise also creates rapid changes.

### First and second derivatives

- **First-order derivatives** respond to changes in intensity and often produce broader edge responses.
- **Second-order derivatives** respond strongly to fine detail, thin lines, isolated points, and noise. They can create two responses around a sharp step edge, with a zero-crossing near the edge location.

### Laplacian operator
The Laplacian is a second-order derivative operator. It emphasizes locations where intensity changes quickly. The source gives two common digital masks.

**4-neighbour Laplacian:**

```text
 0   1   0
 1  -4   1
 0   1   0
```

**8-neighbour Laplacian:**

```text
 1   1   1
 1  -8   1
 1   1   1
```

The 4-neighbour mask considers pixels above, below, left, and right of the center. The 8-neighbour version also includes diagonal neighbors. The Laplacian response can be combined with the original image to sharpen it. Whether the response is added or subtracted depends on the mask's sign convention.

### Unsharp masking
The name can be confusing: unsharp masking sharpens an image by first creating a blurred version.

Steps:
1. Blur the original image.
2. Subtract the blurred image from the original to obtain a detail mask.
3. Add the detail mask back to the original image.

The mask contains high-frequency detail such as edges and fine structures.

### High-boost filtering
High-boost filtering adds a stronger amount of the detail mask back to the original. In the lecture notes, `k = 1` corresponds to standard unsharp masking, `k > 1` increases sharpening, and `0 < k < 1` reduces the sharpening effect.

### Gradient-based sharpening
Gradient operators estimate the rate of intensity change in horizontal and vertical directions. Combining those responses highlights places where the image changes rapidly.

### Smoothing versus sharpening

| Smoothing | Sharpening |
|---|---|
| Reduces rapid local changes | Emphasizes rapid local changes |
| Can reduce some noise | Can amplify noise |
| Often softens edges | Often makes edges look clearer |
| Uses mean, weighted-average, Gaussian, and median filters | Uses Laplacian, unsharp masking, high-boost, and gradient methods |

## 2.9 Frequency-Domain Filtering

Spatial filters work directly on pixel values. Frequency-domain methods first describe the image in terms of its spatial frequencies, meaning how quickly intensity changes across the image.

- **Low frequencies:** represent slowly changing areas, smooth backgrounds, and broad brightness variation.
- **High frequencies:** represent rapid changes, fine details, edges, and some kinds of noise.

### Fourier Transform
The Fourier Transform converts the image from the spatial domain into a frequency representation. The Inverse Fourier Transform converts the processed frequency data back into an ordinary image.

### Frequency-domain filtering workflow

1. Apply the Fast Fourier Transform (FFT) to the image.
2. Shift the zero-frequency component to the center if needed for convenient viewing or filtering.
3. Multiply the frequency representation by a selected filter mask `H(u, v)`.
4. Shift the spectrum back if it was shifted.
5. Apply the Inverse FFT to return to the spatial domain.
6. Use the real part or magnitude of the result as appropriate to form the output image.

### Types of frequency filters

| Filter | What it passes or removes | Main use |
|---|---|---|
| Low-pass filter | Keeps low frequencies and reduces high frequencies | Smoothing or reducing high-frequency noise |
| High-pass filter | Keeps high frequencies and reduces low frequencies | Emphasizing edges and fine detail |
| Band-pass filter | Keeps a selected range of frequencies | Isolating a frequency range or texture pattern |
| Notch filter | Removes selected narrow frequency components | Removing particular periodic interference |
| Band-reject filter | Rejects a chosen frequency band | Suppressing unwanted frequency ranges |

**Exam point:** A sharp edge contains high-frequency information. Excessive low-pass filtering can blur that edge. High-pass filtering can make edges clearer but may also emphasize noise.

## 2.10 Image Noise and Noise Reduction

**Image noise** means unwanted changes in pixel values that do not represent the true scene. Noise can enter during image capture or transmission.

| Noise type | Appearance or cause | Method mentioned in the notes |
|---|---|---|
| Gaussian noise | Fine random variation associated with sensor/electronic noise | Gaussian or mean smoothing can reduce it |
| Salt-and-pepper noise | Scattered black and white pixels | Median filtering; minimum/maximum filters can target particular impulses |
| Poisson or shot noise | Signal-dependent variation linked to photon counting | The source names the noise but does not give one universal filter for it |
| Speckle noise | Grainy, often multiplicative pattern in systems such as ultrasound or radar | Requires a method suited to the imaging model; the source does not prescribe one universal solution |
| Periodic noise | Repeating interference pattern | Notch or band-reject filtering in the frequency domain |

Other methods named in the source include:

- **Bilateral filter:** reduces noise while trying to preserve edges. It generally costs more computation than simple smoothing.
- **Wiener filter:** uses information about signal and noise to address noise and blur; it works best when those characteristics can be estimated.
- **Low-pass frequency filtering:** reduces high-frequency content, including some noise, but can remove fine details too.

### How to choose a denoising method

1. Identify the noise pattern.
2. Decide whether a spatial or frequency method suits it.
3. Choose a filter that reduces that noise while preserving the details needed for the next task.
4. Check the output because stronger filtering does not always mean a better image.

## 2.11 Edge Detection

An **edge** is a location where image intensity changes sharply. Edges often indicate the boundary between objects or regions. Edge detection helps locate shapes, lines, boundaries, and other structures.

The horizontal and vertical intensity changes are commonly represented as `Gx` and `Gy`. Together they describe the strength and orientation of the intensity change.

### Roberts Cross operator
Roberts Cross uses small 2 × 2 diagonal-difference masks. It is fast and simple, but very sensitive to noise because the small kernel provides little smoothing.

### Prewitt operator
Prewitt uses 3 × 3 masks. The masks apply uniform weights to estimate horizontal and vertical changes.

```text
Gx:                 Gy:
-1   0   1         -1  -1  -1
-1   0   1          0   0   0
-1   0   1          1   1   1
```

### Sobel operator
Sobel also uses 3 × 3 masks, but it gives extra weight to the center row or column. That weighting adds some smoothing during gradient estimation and usually makes Sobel less sensitive to noise than Prewitt.

```text
Gx:                 Gy:
-1   0   1         -1  -2  -1
-2   0   2          0   0   0
-1   0   1          1   2   1
```

### Canny edge detector
Canny is a multi-stage method designed to find edges accurately, place them close to true boundaries, and avoid multiple responses for one edge.

1. **Noise reduction:** smooth the image with a Gaussian filter.
2. **Gradient calculation:** calculate intensity-change strength and direction, often using Sobel operators.
3. **Non-maximum suppression:** keep only local maxima along the gradient direction. This makes wide responses thinner.
4. **Double thresholding:** use a high and a low threshold to classify pixels as strong edges, weak edges, or non-edges.
5. **Edge tracking by hysteresis:** keep weak edge pixels when they connect to strong edges; discard isolated weak responses.

### Edge-operator comparison

| Method | Kernel | Main strength | Main limitation |
|---|---|---|---|
| Roberts | 2 × 2 | Very fast | Highly sensitive to noise |
| Prewitt | 3 × 3, uniform weights | Simple gradient estimate | More noise-sensitive than Sobel |
| Sobel | 3 × 3, center-weighted | Adds some smoothing while estimating gradients | Can still return noisy or thick edges |
| Canny | Multi-stage pipeline | Produces thin, comparatively clean, connected edges | More steps and computation |

Applications include lane-line detection, PCB inspection, medical-image boundary analysis, and document cropping or perspective correction.

## 2.12 Morphological Operations

**Morphological operations** change the shape or structure of objects in an image. They commonly operate on binary images and use a small pattern called a **structuring element**.

- **Erosion:** shrinks the foreground, often shown as white pixels. It can remove small isolated white details and narrow object boundaries.
- **Dilation:** expands the foreground. It can fill small gaps and connect nearby regions, but can also enlarge noise.

The two operations can be combined to clean images before segmentation or shape analysis. Remember the direction of the change: erosion shrinks; dilation grows.

---

# Unit 3: Feature Detection and Extraction

## 3.1 What is a Feature?

A **feature** is a useful part of an image that helps a computer identify, compare, track, or understand a scene. Examples include edges, corners, blobs, distinctive points, textures, or object boundaries.

A flat region such as a clear sky usually gives few distinctive clues. A sharp corner or a distinctive texture is more useful because the system may recognize it again in another image.

### Properties of a good feature

| Property | Simple explanation | Why it matters |
|---|---|---|
| Repeatability | The system finds the same physical feature in different images of the same scene | Matching requires the same feature to be detected more than once |
| Distinctiveness | The feature looks different from other features | Reduces ambiguous or incorrect matches |
| Locality | The feature describes a small part of the image | Can survive when another part of the scene is hidden |
| Quantity | The image contains enough useful features | More reliable estimation often needs enough points |
| Accuracy | The system locates each feature precisely | Poor location estimates can cause downstream geometry errors |
| Efficiency | Detection and description finish fast enough | Important for real-time use and limited hardware |

## 3.2 Feature-Based Vision Pipeline

Classical feature-based vision generally follows four stages:

1. **Detection:** locate candidate interest points or regions. Harris is an example for corner detection.
2. **Description / extraction:** convert the neighborhood around each point into a numerical descriptor.
3. **Matching:** compare descriptors from different images using a distance or similarity measure.
4. **Geometric verification and application:** remove inconsistent matches, often with RANSAC, then use the valid matches for tasks such as image alignment, panorama stitching, tracking, or 3D reconstruction.

**Key distinction:** A detector answers **where is the interesting point?** A descriptor answers **what does the local pattern look like?** A matcher answers **which point in the other image is most likely the same feature?**

## 3.3 Edge Detection as Feature Extraction

Edges mark sharp intensity changes and provide clues about object boundaries. Roberts, Prewitt, and Sobel approximate image gradients using kernels. Canny adds smoothing, non-maximum suppression, double thresholding, and edge tracking to obtain cleaner edge maps.

The main use of edge detection in a feature pipeline is to identify boundaries and structural changes. It does not by itself identify an object such as a car or a face.

## 3.4 Harris Corner Detector

### What is a corner?

A corner is a point where two edges or directions of intensity change meet. It can be located more precisely than an arbitrary point along a straight edge.

Imagine moving a small image window:

- **Flat region:** moving the window in any direction changes its contents very little.
- **Edge:** moving across the edge changes the contents a lot, but moving along the edge changes them little.
- **Corner:** moving in almost any direction changes the contents significantly.

This window-shift test is the basic idea behind Harris corner detection.

### Main mathematical idea

Harris uses local intensity gradients to measure how much the image changes when a window moves. It calculates a local structure matrix, often called the second-moment matrix or structure tensor. The matrix summarizes horizontal changes, vertical changes, and their relationship.

The Harris response is commonly expressed as:

`R = det(M) - k(trace(M))^2`

Here `M` is the local structure matrix and `k` is a sensitivity constant. A large positive response indicates a likely corner; a small response suggests a flat area; a negative response commonly indicates an edge-like area.

### Steps of the Harris detector

1. Calculate horizontal and vertical image derivatives, often using Sobel.
2. Calculate the local products `Ix²`, `Iy²`, and `IxIy`.
3. Sum or smooth those products over a small window to form the structure matrix `M`.
4. Calculate the response `R` for each position.
5. Keep responses above a selected threshold.
6. Apply non-maximum suppression so nearby responses do not mark the same corner repeatedly.

### Advantages and limitations

- Harris finds well-localized corners and works well for tracking, camera calibration, and matching.
- It is computationally practical for many classical-vision tasks.
- It is not naturally scale-invariant, so a corner can be harder to match if the image size changes greatly.

### Related detectors

- **Harris-Laplace:** adds scale selection to Harris-style corner detection.
- **FAST:** checks a circle of surrounding pixels for a contiguous group that is sufficiently brighter or darker than the candidate pixel. It is very fast and is used inside ORB.

Applications include camera calibration, video stabilization, motion capture, visual SLAM, and structure-from-motion.

## 3.5 Feature Descriptors

A feature descriptor stores a numerical summary of the appearance around a detected keypoint. A good descriptor should be distinctive but should also remain useful when the image changes in scale, rotation, brightness, or viewpoint.

The three descriptors in the lecture are **SIFT, SURF, and ORB**.

### SIFT: Scale-Invariant Feature Transform

SIFT aims to detect and describe keypoints that remain recognizable across scale and rotation changes.

**Stage 1: Detect scale-space extrema**

- Blur the image at different scales.
- Compute Difference-of-Gaussians (DoG) images.
- Find candidate points that are local maxima or minima compared with nearby points across the current and neighboring scales.

**Stage 2: Localize keypoints**

- Refine the candidate position and scale.
- Reject weak low-contrast points.
- Reject unstable edge-like points that are poorly localized along the edge.

**Stage 3: Assign orientation**

- Examine gradients around the keypoint.
- Build an orientation histogram.
- Use the dominant orientation to give the keypoint a consistent direction.

**Stage 4: Build the descriptor**

- Rotate the local region to align with the selected orientation.
- Divide the region into a 4 × 4 grid of subregions.
- Build an 8-bin gradient-orientation histogram in each subregion.
- Combine the histograms into `4 × 4 × 8 = 128` values.
- Normalize the descriptor to reduce the effect of some illumination changes.

**Strengths:** strong scale and rotation robustness, distinctive descriptors, useful for image matching and 3D reconstruction.

**Limitations:** more computationally expensive than ORB and some other alternatives.

**Common use cases:** panorama stitching, matching a product across images, and matching features across photographs for structure-from-motion.

### SURF: Speeded-Up Robust Features

SURF was designed to provide robust feature detection and description with less computation than SIFT.

- It detects blob-like features using an approximation to the Hessian-matrix response.
- It uses box filters and integral images to make computation faster.
- It estimates a dominant orientation using local responses.
- It divides a descriptor region into a 4 × 4 grid and summarizes responses in each cell.
- The standard descriptor in the source has `4 × 4 × 4 = 64` values; an extended 128-dimensional version also exists.

**Strengths:** balances speed and robustness and offers scale/rotation handling.

**Limitations:** historically had patent and licensing restrictions; it is not as lightweight as ORB in the lecture's comparison.

**Common use cases:** robotic and embedded vision that needs a balance between matching quality and speed.

### ORB: Oriented FAST and Rotated BRIEF

ORB combines fast keypoint detection with a binary descriptor and adds orientation handling.

**Detection: FAST**

- Examine a circle of 16 surrounding pixels around a candidate point.
- Check whether a sufficiently long contiguous arc is brighter or darker than the candidate by a threshold.
- Rank candidates using a corner score and keep the most useful points.

**Orientation**

- Estimate the keypoint's orientation from the intensity distribution around it.

**Description: rotated BRIEF (rBRIEF)**

- Compare the intensity of selected pixel pairs in a local patch.
- Store the comparison results as a binary string.
- Rotate the comparison pattern according to the keypoint orientation.
- The source describes a typical descriptor as 256 bits.

**Strengths:** very fast, free/open, suitable for real-time applications, and efficient to match with Hamming distance.

**Limitations:** scale handling is more limited than SIFT in the source's comparison, even though image pyramids can help.

**Common use cases:** mobile vision, real-time matching, robotics, and ORB-SLAM.

**Memory aid:** FAST finds the point. BRIEF describes the point. ORB combines fast point detection and a rotation-aware binary descriptor.

### SIFT, SURF, and ORB compared

| Criterion | SIFT | SURF | ORB |
|---|---|---|---|
| Detector | Difference-of-Gaussians scale-space extrema | Hessian approximation using box filters | Oriented FAST |
| Descriptor | Floating-point gradient histograms | Floating-point Haar-wavelet response summary | Binary string from rotated BRIEF |
| Descriptor size in the notes | 128 dimensions | 64 dimensions, or 128 extended | Commonly 256 bits |
| Match distance | Euclidean | Euclidean | Hamming |
| Rotation handling | Yes | Yes | Yes |
| Scale handling | Strong | Approximate | More limited; pyramid can help |
| Speed | Slower | Faster than SIFT | Very fast in the comparison |
| Best fit | Robust matching and offline reconstruction | Balanced speed and robustness | Real-time, mobile, embedded, SLAM |

## 3.6 Texture Analysis

**Texture** describes the visual pattern of a surface: how image intensities or structures repeat, vary, or form local patterns. Texture can distinguish objects that have similar colors but different surface patterns.

Examples:

- Smooth texture: painted wall, white paper, or calm water.
- Rough texture: sand, stone, or brick.
- Regular texture: floor tiles, a chessboard, or window grills.
- Random texture: clouds, smoke, or foliage.

### Why texture matters

Texture helps distinguish road from footpath, healthy-looking from diseased tissue, or one fabric type from another. It also supports fingerprint recognition, surface inspection, agricultural analysis, and satellite-image classification.

### Important texture properties

- **Contrast:** how different neighboring pixel values are.
- **Homogeneity:** how similar neighboring pixel values are. Similar neighboring values indicate high homogeneity.
- **Energy:** a measure related to repetition or order. Repeated patterns often produce higher energy.
- **Entropy:** a measure of randomness. Highly irregular patterns tend to have higher entropy.

### Texture-analysis methods

**1. Statistical methods**

These calculate statistics from pixel values or relationships between neighboring pixels. They are useful when the texture can be described numerically rather than by a clear object shape.

**2. Structural methods**

These describe texture using repeated basic elements and the arrangement of those elements. They are suitable for patterns such as tiles, grids, and fabrics.

**3. Transform-based methods**

These transform image information into a different representation to reveal patterns at particular frequencies or scales. The source mentions Fourier and Wavelet transforms. Wavelets can indicate both the type of pattern and where it appears in the image.

**4. Gray-Level Co-occurrence Matrix (GLCM)**

GLCM records how often pairs of gray levels occur at a chosen distance and direction. From the matrix, a system can derive measures such as contrast, homogeneity, energy, entropy, and correlation. The chosen pixel distance and direction affect the result.

**5. Local Binary Pattern (LBP)**

LBP describes the local relationship between a center pixel and its neighbors.

Steps:
1. Select a center pixel.
2. Compare each neighboring pixel with the center.
3. Write `1` if the neighbor is greater than or equal to the center; otherwise write `0`.
4. Read the binary pattern in the specified order, such as clockwise.
5. Convert the binary pattern into a number for use as a texture descriptor.

LBP is simple and fast, and the source highlights its use in face and texture recognition. It can be sensitive to changes in illumination and scale.

**6. Gabor filter**

A Gabor filter responds to patterns at particular orientations and frequencies. A collection of Gabor filters can help describe directional textures, such as stripes, fibers, or repeated surface patterns. The source notes its usefulness but also identifies it as slower than simpler methods.

### Texture-method comparison

| Method | Basic idea | Typical strength / use |
|---|---|---|
| Statistical | Calculate numerical properties of pixel values | Fast general texture description |
| Structural | Describe repeating patterns and their arrangement | Tiles, fabrics, and regular surfaces |
| GLCM | Count gray-level pairs at a chosen offset | Medical imaging and remote sensing |
| LBP | Encode neighbor-versus-center intensity patterns | Fast face and texture recognition |
| Gabor | Analyze selected orientations and frequencies | Directional or repeated texture patterns; more computation |

## 3.7 Shape Representation

**Shape representation** describes an object's outline or internal structure so that the system can compare, classify, or measure it.

### Common techniques

- **Contour representation:** stores the object's outer boundary. Useful for object counting and boundary comparison.
- **Chain code:** represents the boundary as a sequence of directions. It is useful in document processing, OCR, and shape analysis.
- **Polygon approximation:** replaces a detailed boundary with a smaller number of straight-line segments. It simplifies shapes and reduces the amount of data to process.
- **Convex hull:** forms the tightest convex boundary that encloses the object. It can help describe overall shape and support gesture recognition.
- **Skeleton representation:** reduces an object to a thinner centerline while preserving its basic structure. Useful for fingerprints, branching patterns, and structural analysis.
- **Moments:** numerical measurements of a shape or region, such as area, centroid, and orientation. Useful for tracking and comparing objects.
- **Fourier descriptors:** describe a boundary using its frequency components. Useful for shape matching, signature comparison, and logo recognition.

| Technique | What it stores | Example use |
|---|---|---|
| Contour | Outer boundary | Object counting |
| Chain code | Sequence of boundary directions | OCR and navigation |
| Polygon approximation | A simplified polygon | Shape simplification |
| Convex hull | Convex enclosing boundary | Gesture recognition |
| Skeleton | Thin centerline / structure | Fingerprint analysis |
| Moments | Numerical shape properties | Tracking and medical analysis |
| Fourier descriptors | Frequency representation of boundary | Signature and shape matching |

## 3.8 Feature Matching and Similarity Measures

Feature matching identifies points in different images that probably correspond to the same physical location or object detail.

### Feature-matching workflow

1. Detect keypoints in Image A.
2. Describe the neighborhood around each keypoint.
3. Detect keypoints in Image B.
4. Describe those keypoints.
5. Compare descriptors with a distance or similarity measure.
6. Select likely matches.
7. Reject ambiguous or geometrically inconsistent matches where necessary.

### Similarity measures

**Euclidean distance** measures straight-line distance between numerical vectors. A smaller distance generally indicates more similar descriptors. SIFT and SURF use floating-point descriptors and commonly use Euclidean distance.

**Hamming distance** counts the bit positions that differ between two binary descriptors. Fewer differing bits means a closer match. ORB and BRIEF commonly use Hamming distance.

**Cosine similarity** compares the direction of two vectors. A value closer to 1 indicates that the vectors point in similar directions; values near 0 indicate weak directional similarity. The source associates this with deep feature vectors and image retrieval.

### Matchers

**Brute-force matcher (BFMatcher)** compares a descriptor with every candidate descriptor in the other image. It is straightforward and exhaustive, but becomes slow when the descriptor collection is large.

**FLANN** means Fast Library for Approximate Nearest Neighbors. It searches for nearby descriptors using faster approximate methods. It is useful for larger collections and can be quicker than exhaustive matching, though the search is approximate.

| BFMatcher | FLANN |
|---|---|
| Compares all candidate descriptors | Uses approximate nearest-neighbor search |
| Simple and exhaustive | Often faster on large collections |
| Suitable for smaller problems | Useful for larger feature sets and speed-sensitive tasks |

### Lowe's ratio test
The ratio test helps reject ambiguous matches. It compares the distance to the best candidate with the distance to the second-best candidate. If the best match is not clearly better than the second-best, the match may be ambiguous and should be rejected. The threshold controls how selective the test is. For example, distances of 12 and 13 are almost equal, so the best match is ambiguous; distances of 10 and 40 show a much clearer best match and are more likely to pass the test.

### RANSAC and geometric verification
A descriptor match can be wrong even when the descriptors look similar. **RANSAC** estimates a geometric relationship from candidate matches and separates matches that agree with that relationship from outliers that do not. This makes image alignment and reconstruction more reliable.

**Good match:** a distinctive descriptor match that also agrees with the scene's geometry.

**Bad match:** a visually similar but incorrect descriptor match, or a match that contradicts the geometric relationship shared by the other matches.

---

# Additional Lecture: Image Segmentation and Related Methods

The supplied segmentation lecture also includes template matching, KNN, SVM, Haar Cascade face detection, and model-evaluation metrics. This section keeps those topics together as they appear in the source file.

## 4.1 What is Image Segmentation?

**Image segmentation** divides an image into meaningful regions or objects so that each region can be analyzed separately. It groups pixels that share properties such as brightness, color, texture, or local similarity.

**Example:** In an image of an apple on a table, segmentation separates the apple from the table and background.

### Why segmentation is useful

- It focuses later processing on the object or region of interest.
- It makes object measurement and shape analysis easier.
- It supports medical-image analysis, road understanding, face-region analysis, satellite mapping, agriculture, and object counting.

## 4.2 Thresholding

Thresholding separates pixels based on intensity. Choose a threshold `T`, then compare each pixel with it. In the source's example, values greater than 128 become white (255), while values at or below 128 become black (0).

For a threshold of 128:

| Pixel value | Output |
|---:|---|
| 50 | Black |
| 90 | Black |
| 110 | Black |
| 130 | White |
| 170 | White |
| 250 | White |

Thresholding often turns a grayscale image into a binary image, making it easier to separate a foreground object from the background.

### Global thresholding
Global thresholding uses one threshold for the entire image.

**Advantages:** simple, fast, and easy to implement.

**Limitation:** a single threshold may fail when lighting varies across the image. For example, part of a photographed page may be bright while another part lies in shadow.

### Adaptive thresholding
Adaptive thresholding chooses a threshold separately for local regions. It handles uneven lighting better because each region can use a different threshold.

**Advantages:** more suitable for shadows and non-uniform lighting.

**Limitation:** requires more computation than a single global threshold.

| Global thresholding | Adaptive thresholding |
|---|---|
| One threshold for the whole image | Different thresholds for different local areas |
| Simple and fast | Better under uneven lighting |
| Works well with reasonably uniform lighting | Useful for shadows and changing brightness |

## 4.3 Region-Based Segmentation and Region Growing

Region-based segmentation groups neighboring pixels that have similar properties, such as intensity, color, or texture.

### Region-growing algorithm

1. Choose a **seed pixel** inside the region to extract.
2. Examine its neighboring pixels.
3. Compare each neighbor with the region's similarity rule.
4. Add pixels that meet the rule.
5. Repeat the process using newly added pixels as part of the region.
6. Stop when no neighboring pixel qualifies.

**Example:** A seed pixel inside a tumor region may start a growing process. The method adds neighboring pixels with similar image values until the region boundary is reached.

**Advantages:** creates connected regions and can give useful object boundaries.

**Limitations:** the result depends on the seed location and the similarity criterion. A poor seed can produce the wrong region, and noisy images can make the boundary difficult to determine.

## 4.4 K-Means Clustering for Segmentation

**Clustering** groups similar data points without requiring a predefined class label for each point. **K-means** groups image pixels into `K` clusters based on similarity, often using intensity or color.

- `K = 2` might separate an object from its background.
- `K = 3` might divide an image into regions such as sky, trees, and road, depending on the pixel data.

### K-means steps

1. Choose the number of clusters, `K`.
2. Initialize `K` cluster centers, called **centroids**.
3. Assign each pixel to the nearest centroid.
4. Calculate a new centroid for each cluster from the pixels assigned to it.
5. Repeat assignment and centroid update until the centers stop changing or the stopping rule is met.

**Advantages:** simple, reasonably fast, and useful for color-based segmentation and image compression.

**Limitations:** the user must choose `K`; different initial centroids can produce different results; and K-means may not separate objects with irregular shapes when color or intensity alone does not distinguish them.

## 4.5 Watershed Algorithm

Watershed is used to separate objects that touch or overlap, such as touching cells or coins.

### Basic idea
Imagine an image as a landscape containing hills and valleys. Water begins filling the low areas. When water from two regions would meet, the algorithm builds a boundary between them. This boundary is the **watershed line**.

### Workflow described in the lecture

1. Convert the image into a binary representation.
2. Identify the foreground or object region.
3. Identify the background.
4. Apply the watershed procedure.
5. Use the resulting boundaries to separate objects.

**Applications:** counting touching cells, separating overlapping coins, medical-image segmentation, and object counting.

**Advantages:** helps separate touching objects and can produce clear boundaries.

**Limitations:** noise may create unwanted regions, so preprocessing often improves results.

## 4.6 Template Matching

Template matching searches for a small reference image, called a **template**, inside a larger image.

### Steps

1. Select the larger image.
2. Select the template patch.
3. Slide the template across possible positions in the larger image.
4. Calculate a similarity score at each position.
5. Choose the position with the best score.

Applications include finding logos, symbols, and known visual patterns in larger images, as well as some document or inspection tasks.

**Advantages:** simple and useful when the target looks similar to the template.

**Limitations:** it may fail when the object rotates, changes scale, becomes partially hidden, or changes appearance significantly.

## 4.7 K-Nearest Neighbors (KNN)

KNN classifies a new example by finding the `K` closest examples in the stored training data and using their labels to make a prediction. In a typical classification task, the class that receives the majority vote becomes the predicted class.

### Working steps

1. Store labelled training examples.
2. Choose a value of `K`.
3. Calculate the distance from the new example to known examples.
4. Select the `K` nearest examples.
5. Use their labels to determine the prediction.

**Advantages:** easy to understand and requires little explicit model training.

**Limitations:** prediction can be slow with a large dataset, the choice of `K` affects results, and features must be represented in a meaningful way for distance comparisons to work.

Applications in the supplied notes include handwriting recognition, face recognition, medical classification, and recommendation systems.

## 4.8 Support Vector Machine (SVM)

A **Support Vector Machine** is a supervised learning method that classifies data by finding a decision boundary, called a **hyperplane**, that separates classes. Its central idea is to find a boundary with a large margin between the classes.

**Advantages described in the notes:** can work well with high-dimensional features, can provide strong classification performance, and is useful when the dataset is not extremely large.

**Limitations described in the notes:** it can be more complex than KNN, and training or scaling to very large datasets can become expensive.

### KNN versus SVM

| Point | KNN | SVM |
|---|---|---|
| Main idea | Predict from nearby labelled examples | Learn a decision boundary between classes |
| Training | Little explicit training | Fits a model during training |
| Prediction | Searches for neighbors | Uses the learned boundary/model |
| Main consideration | Choosing `K` and a useful distance | Selecting a suitable boundary/model and handling training cost |

## 4.9 Haar Cascade Face Detection

**Face detection** locates faces in an image. It does not by itself identify the person.

A Haar Cascade uses learned light-and-dark image patterns and a cascade of tests to scan windows across an image. It returns likely face regions, often drawn as rectangular boxes.

### Basic workflow

1. Read an image or video frame.
2. Scan it at different positions and sizes.
3. Apply the trained cascade to candidate windows.
4. Reject windows that fail early tests.
5. Return windows that pass the cascade as likely face locations.

**Advantages:** relatively fast and suitable for some real-time applications.

**Limitations described in the source:** performance can drop when faces turn sideways, lighting is poor, or faces are partly hidden.

### Face detection versus face recognition

- **Face detection:** “Where is a face?”
- **Face recognition:** “Whose face is it?” or “Does this face match a claimed identity?”

Recognition generally extracts facial features and compares them with stored data; detection first locates the face.

## 4.10 Evaluation Metrics: Accuracy, Precision, and Recall

Evaluation metrics describe different aspects of a classifier's performance. Learn the definitions as well as the formulas.

- **True Positive (TP):** the model predicts positive and the example is actually positive.
- **True Negative (TN):** the model predicts negative and the example is actually negative.
- **False Positive (FP):** the model predicts positive, but the example is actually negative.
- **False Negative (FN):** the model predicts negative, but the example is actually positive.

### Accuracy
Accuracy measures the share of all predictions that the model gets right.

`Accuracy = (TP + TN) / (TP + TN + FP + FN)`

### Precision
Precision asks: **Of all the examples the model predicted as positive, how many were actually positive?**

`Precision = TP / (TP + FP)`

### Recall
Recall asks: **Of all the examples that were actually positive, how many did the model find?**

`Recall = TP / (TP + FN)`

### Simple examples from the lecture

- If a model predicts 100 examples and gets 90 correct, its accuracy is 90%.
- If it labels 20 emails as spam and 18 really are spam, its precision is 18/20 = 90%.
- If 25 emails are actually spam and the model detects 20 of them, its recall is 20/25 = 80%.

**Exam distinction:** high precision means few false alarms among the positive predictions. High recall means the model misses fewer actual positive cases. Accuracy summarizes all correct predictions but can hide poor performance on a rare class.

---

# Unit 5: Deep Learning in Computer Vision

## 5.1 What is Deep Learning?

**Deep Learning** is a part of Machine Learning that uses neural networks with multiple layers to learn patterns from data. In Computer Vision, it allows a model to learn visual features from images rather than requiring a person to design every feature manually.

**Example:** Instead of manually writing rules for cat ears, eyes, and face shape, a model trains on many labelled cat and dog images and learns patterns that help distinguish the classes.

## 5.2 Neural-Network Basics

A neural network usually contains an input layer, one or more hidden layers, and an output layer.

- **Input layer:** receives the input values, such as an image's pixel values.
- **Hidden layers:** transform the input and learn patterns.
- **Output layer:** produces the final prediction, such as class scores or probabilities.

### Neuron
A neuron receives input values, multiplies them by weights, adds a bias, and applies an activation function.

`Output = Activation(weighted sum + bias)`

- **Weight:** controls how strongly an input contributes.
- **Bias:** shifts the calculated value.
- **Activation function:** transforms the result and helps the network learn non-linear patterns.

A neural network learns by adjusting its parameters during training so that its predictions better fit the training examples.

## 5.3 Why use a Convolutional Neural Network (CNN)?

A **Convolutional Neural Network (CNN)** is a neural network designed especially for images and other spatial data. Images contain local patterns: nearby pixels often form edges, corners, textures, and object parts. CNNs use filters to learn these patterns.

A normal fully connected network can treat every image pixel as an individual input and may need a very large number of parameters. A CNN uses local filters and reuses the same filter across different image locations. This helps it detect patterns without learning a separate weight for every pixel position.

CNNs are useful for image classification, face recognition, object detection, medical-image analysis, self-driving systems, handwritten-character recognition, and facial-expression analysis.

## 5.4 Main CNN Components

### Convolution layer
A convolution layer moves small learnable filters, also called kernels, over the image or previous feature maps. Each filter responds to particular local patterns. Early layers may respond to simple edges or lines, while deeper layers can respond to more complex patterns.

### Feature map
A **feature map** is the output produced when a filter is applied to an image or an earlier feature map. Different filters produce different feature maps because each filter learns or responds to a different type of pattern.

For example, one filter may respond strongly to vertical edges while another responds to horizontal edges or textures.

### Activation function: ReLU
ReLU means **Rectified Linear Unit**. It replaces negative values with zero and keeps positive values unchanged.

`ReLU(x) = max(0, x)`

Examples:

| Input | Output after ReLU |
|---:|---:|
| -5 | 0 |
| 2 | 2 |
| -3 | 0 |
| 7 | 7 |

ReLU adds non-linearity, which helps the network learn more complex patterns.

### Pooling layer
Pooling reduces the spatial size of feature maps, making later computations smaller. It aims to retain useful information while reducing the amount of data.

**Max pooling** selects the largest value within a small region. For example:

```text
Input region       Max-pooling output
2  5               5
1  3
```

For the source's larger example, a 2 × 2 max-pooling window applied without overlap produces the largest value from each 2 × 2 region. Pooling reduces the feature-map dimensions.

**Worked 2 × 2 max-pooling example:** the lecture uses this 4 × 4 feature map and a non-overlapping 2 × 2 window.

```text
Input:                 Output after max pooling:
1  3  2  4             6  4
5  6  1  2             7  8
7  2  8  3
4  1  5  6
```

The four windows have maximum values 6, 4, 7, and 8. The operation reduces a 4 × 4 feature map to a 2 × 2 feature map.

**Why pooling helps:** the network may not need the exact location of every pixel-level response. It often needs to know that a useful feature appears within a region. Reducing spatial size also lowers computation.

### Flatten layer
Flatten converts multi-dimensional feature maps into a one-dimensional vector. That vector can then enter a fully connected layer.

### Fully connected layer
A fully connected (FC) layer connects each neuron to all outputs from the previous layer. It uses the extracted features to produce a classification or prediction.

### Output layer
The output layer returns the model's final result, such as cat versus dog probabilities or scores.

## 5.5 Standard CNN Classification Pipeline

A simple CNN for image classification follows this structure:

```text
Input Image
    ↓
Convolution
    ↓
ReLU
    ↓
Pooling
    ↓
Convolution
    ↓
ReLU
    ↓
Pooling
    ↓
Flatten
    ↓
Fully Connected Layer
    ↓
Output Classes
```

### Example: cat-versus-dog classification

1. **Input:** the model receives a cat or dog image.
2. **First convolution:** filters respond to simple patterns such as edges, lines, and corners.
3. **Deeper convolution:** later filters combine simpler patterns into shapes and object parts, such as eyes, ears, or noses.
4. **Pooling:** the feature maps become smaller while retaining strong responses.
5. **Flattening:** the remaining feature maps become a vector.
6. **Fully connected layer:** the network uses the learned features for classification.
7. **Output:** the model produces scores or probabilities for the classes. The highest prediction may be cat, for example.

The hierarchical process is important: simple visual patterns can combine into more complex patterns in deeper layers.

## 5.6 What each CNN layer does

| Layer | Main purpose | Simple interpretation |
|---|---|---|
| Input | Receive image data | Take in the pixels |
| Convolution | Detect learned patterns | Find edges, curves, textures, and shapes |
| ReLU | Add non-linearity | Set negative activations to zero |
| Pooling | Reduce spatial size | Keep strong local responses while shrinking the feature map |
| Flatten | Change data shape | Turn feature maps into a vector |
| Fully connected | Combine learned features | Make the class decision |
| Output | Return prediction | Give class scores or probabilities |

## 5.7 Automatic Feature Learning

Traditional computer vision often requires a person to design features such as edge measures, textures, or shape descriptors. A CNN learns many of its useful features from training data.

This does not mean a CNN needs no preparation or supervision. It still needs an appropriate dataset, training procedure, model design, and evaluation. The difference is that it learns internal image representations instead of relying entirely on manually specified features.

## 5.8 Object Detection

**Object detection** answers two questions:

1. What objects appear in the image?
2. Where does each object appear?

Object detection combines classification with localization. A detector typically outputs a **class label**, a **bounding box**, and a **confidence score** for each detection.

### Bounding boxes
A bounding box is a rectangle around a detected object. It may be represented as `(x, y, width, height)` or by two corners `(x1, y1, x2, y2)`.

### Classification versus detection

- **Classification:** labels the whole image, such as “contains people.”
- **Detection:** returns each detected object, its class, and its location. In a classroom image, it may return a separate box for every person.

### General detection pipeline

```text
Input Image
    ↓
Feature Extraction
    ↓
Object / Region Prediction
    ↓
Predict Bounding Boxes and Classes
    ↓
Remove Duplicate Boxes
    ↓
Final Detections
```

## 5.9 The R-CNN Family

R-CNN stands for **Regions with Convolutional Neural Network features**. The family uses candidate image regions to locate objects, but later versions improve the speed by reducing repeated computation.

### Original R-CNN

1. Receive an input image.
2. Generate region proposals, approximately 2,000 per image in the lecture's example.
3. Extract each proposed region.
4. Run CNN feature extraction separately for each region.
5. Classify the region.
6. Refine the bounding box.
7. Return the final detections.

**Why original R-CNN is slow:** it runs the CNN separately on many region proposals. If the image produces around 2,000 proposals, the system may perform roughly 2,000 CNN passes for that image.

### Fast R-CNN
Fast R-CNN runs the CNN once on the full image and reuses the resulting feature map for the proposed regions. This removes much of the repeated CNN computation found in original R-CNN.

### Faster R-CNN
Faster R-CNN adds a learned **Region Proposal Network (RPN)** to generate candidate regions. This replaces the slower separate Selective Search proposal stage with a learned proposal mechanism.

### R-CNN family summary

| Method | Main idea | Main improvement or limitation |
|---|---|---|
| R-CNN | Generate proposals and run CNN features for each region | Accurate in the original design but slow because it repeats feature extraction |
| Fast R-CNN | Run CNN once over the full image and reuse its feature map | Reduces repeated CNN work |
| Faster R-CNN | Use a learned Region Proposal Network | Makes region-proposal generation faster |

The lecture describes the R-CNN family as useful when detection quality matters, while noting that Faster R-CNN is not usually the first choice when very high real-time speed is the main requirement.

## 5.10 YOLO: You Only Look Once

YOLO is a single-stage object detector. It predicts object locations and classes directly from the image in one model pipeline rather than using a separate region-proposal stage.

### Original grid idea
In the original YOLO design, the image is divided into a grid. Each cell is responsible for predicting objects whose centers fall within it. Modern versions use more advanced designs, but the central idea remains direct prediction from one model pipeline.

### What YOLO predicts

- **Bounding box:** where the object is.
- **Class:** what the object is, such as person, car, or dog.
- **Confidence:** how strongly the model supports that detection.

### Non-Maximum Suppression (NMS)
A detector may predict several overlapping boxes around the same object. NMS compares those boxes and keeps a high-confidence result while removing redundant overlapping detections.

### Advantages of YOLO

- Fast enough for many real-time applications.
- Detects multiple objects in one model pass.
- Uses a direct detection pipeline.
- Supports traffic monitoring, robotics, CCTV, vehicle and pedestrian detection, industrial inspection, and sports analysis.

### Limitations noted in the source

- Small objects can be harder to detect.
- Crowded scenes can be challenging.
- Speed and accuracy depend on model size and hardware.
- Custom tasks require a suitable labelled dataset.

## 5.11 R-CNN versus YOLO

| Feature | R-CNN family, especially original R-CNN | YOLO |
|---|---|---|
| Main approach | Region proposals followed by region classification | Directly predicts object boxes and classes |
| Processing | Multi-stage, with original R-CNN repeating CNN work per region | Single-stage model pipeline |
| Speed | Original R-CNN is slow; later versions improve efficiency | Designed for speed and real-time use |
| Region proposals | Uses proposals; Faster R-CNN learns them with an RPN | No separate region-proposal stage in the same sense |
| Good fit | Detection pipelines where region-level processing is appropriate | Real-time detection such as traffic and surveillance |

**Memory aid:** R-CNN first proposes regions, then classifies them. YOLO predicts object locations and classes directly in one pass.

## 5.12 Transfer Learning and Fine-Tuning

### Transfer learning
**Transfer learning** reuses knowledge learned by a model on one task to help with a related task. A pretrained image model may already recognize general features such as edges, shapes, textures, and object parts. Those features can help it learn a new task, such as helmet versus no helmet.

### Fine-tuning
**Fine-tuning** starts with a pretrained model and continues training some or all of its weights on a new dataset. It adapts the model's learned features to the new task.

### Example: cat-versus-dog classifier

1. Load a pretrained image model.
2. Replace or adapt its final classification layer for cat and dog classes.
3. Train the new classifier on the cat/dog dataset.
4. Optionally unfreeze selected earlier layers and continue training if task-specific adaptation is needed.

### Feature extraction versus fine-tuning

| Criterion | Feature extraction | Fine-tuning |
|---|---|---|
| Pretrained model | Used | Used |
| Existing layers | Mostly frozen | Some layers are unfrozen and updated |
| What trains? | Mainly the new task-specific layers | New layers plus selected existing layers |
| Training time | Usually lower | Usually higher |
| Flexibility | Lower, since pretrained features change less | Higher, since more of the model can adapt |
| Data and compute | Often suitable when data or compute is limited | May benefit from more data and compute |

### Benefits of transfer learning

- Reduces training time.
- Reduces the amount of labelled data often needed.
- Can improve results on smaller datasets.
- Lowers compute requirements compared with training from scratch.
- Makes experimentation faster.

**Important distinction:** Transfer learning is the overall idea of reusing previous knowledge. Fine-tuning is one way to adapt a pretrained model by continuing its training.

---

# Unit 6: Motion Analysis and Applications

## 6.1 What is Motion Analysis?

**Motion Analysis** studies how objects move through a sequence of images or video frames. A single image shows what appears in a scene at one moment. A video adds information about what changes over time.

**Example:** a road camera records a car at position A in the first frame, position B in the second, and position C in the third. Comparing the frames reveals movement.

Motion analysis can help answer:

- Is something moving?
- Where is it moving?
- In which direction is it moving?
- How quickly is it moving?
- Which object is moving?
- Does the movement appear unusual?

Applications include security, autonomous vehicles, traffic monitoring, sports analysis, medical imaging, human activity recognition, robotics, augmented reality, and industrial automation.

## 6.2 Video and Video Processing

A **video** is a sequence of images shown rapidly. Each individual image is a **frame**.

**Frame rate**, measured in frames per second (FPS), states how many frames appear each second. Common examples in the lecture are 24 FPS, 30 FPS, and 60 FPS. A higher frame rate generally gives smoother motion, although it also means more frames to store or process.

### Video-processing pipeline

```text
Video
  ↓
Read / Extract Frames
  ↓
Preprocessing
  ↓
Motion or Object Detection
  ↓
Tracking
  ↓
Motion / Behavior Analysis
  ↓
Output, Report, or Alert
```

Typical operations include reading video, extracting frames, resizing, removing noise, converting color spaces, detecting motion, detecting objects, tracking objects, classifying video, and saving or displaying the results.

## 6.3 Motion Detection

**Motion detection** identifies changes or movement between frames. It is commonly used by CCTV systems, automatic doors, traffic monitors, smart homes, and industrial monitoring systems.

A simple motion-detection method compares consecutive frames. If some areas change enough, the system flags them as possible motion.

### Frame differencing

Let `Frame_t` be the current frame and `Frame_(t-1)` be the previous frame. The source expresses the difference as:

`Difference = |Frame_t - Frame_(t-1)|`

A large difference in a region suggests that something changed there. A threshold may be used to decide which differences count as motion.

**Strength:** simple and fast.

**Limitation:** lighting changes, shadows, camera movement, or other scene changes can look like object motion. A moving object may also be missed if its appearance barely changes from one frame to the next.

## 6.4 Optical Flow

**Optical Flow** estimates the apparent movement of image pixels or visual features between consecutive frames. It represents how image points appear to move from one frame to another.

An **optical-flow vector** describes movement using direction and magnitude. A longer vector represents a larger estimated displacement between the frames, for the same time interval.

### Sparse optical flow

Sparse optical flow estimates motion only for selected points, usually distinctive features such as corners. It uses fewer points and therefore often requires less computation.

### Dense optical flow

Dense optical flow estimates movement for nearly every pixel. It provides a fuller picture of motion but usually needs more computation and may be more expensive to run.

| Sparse optical flow | Dense optical flow |
|---|---|
| Tracks selected important points | Estimates motion across almost all pixels |
| Lower computational load in many uses | More detailed motion field |
| Useful for point tracking and camera-motion estimation | Useful when a dense motion description matters |

## 6.5 Lucas-Kanade Optical Flow

Lucas-Kanade is a popular local optical-flow method. It estimates how selected feature points move between frames by examining a small neighborhood around each point.

### Main assumptions

1. **Brightness constancy:** the brightness of a tracked point remains approximately the same between adjacent frames.
2. **Small motion:** the point moves only a small distance between the frames being compared.
3. **Similar motion nearby:** pixels in a small neighborhood are assumed to have approximately similar movement.

### Workflow

1. Read the video frames.
2. Select feature points, such as corners.
3. Compare a small neighborhood around each point across consecutive frames.
4. Estimate how the point moved.
5. Produce motion vectors.
6. Continue tracking the points in later frames.

### Applications

- Tracking feature points on an object.
- Estimating camera motion.
- Video stabilization.
- Gesture recognition.
- Augmented reality.
- Robot vision.

**Limitations:** large movements, changing brightness, motion blur, and occlusion can violate its assumptions or make a point hard to track.

## 6.6 Object Detection versus Object Tracking

Detection and tracking are related, but they answer different questions.

| Object detection | Object tracking |
|---|---|
| Finds and locates objects in a frame | Follows an object across a sequence of frames |
| Answers “What is present, and where?” | Answers “Where did this object move?” |
| Can work on each frame independently | Uses information from previous frames to maintain continuity |
| Example: detect a car in a frame | Example: keep following the same car as it moves |

A detector may find a car in each frame. A tracker associates those detections over time so the system can maintain the car's identity and estimate its path.

## 6.7 Object-Tracking Techniques

### Point tracking
Tracks selected points or visual features on an object. Lucas-Kanade optical flow can estimate how these points move. Useful when distinctive points remain visible.

### Kernel-based tracking
Tracks a region or shape using its appearance. The lecture names **Mean Shift** and **CamShift**. They can work well when the object's appearance remains reasonably stable.

### Bounding-box tracking
Represents an object with a rectangle. The algorithm updates the box's position and often its size as the object moves.

### Detection-based tracking
A detector finds objects in each frame, and a tracking algorithm associates detections from one frame with detections in the next. The notes list **SORT**, **Deep SORT**, and **ByteTrack** as common examples for multi-object tracking.

## 6.8 Background Subtraction

**Background subtraction** separates moving foreground objects from a relatively stationary background. The system builds or stores a background model and compares each current frame against it.

```text
Current Frame
      ↓
Compare with Background Model
      ↓
Calculate Difference / Foreground Mask
      ↓
Identify Moving Foreground Objects
```

**Example:** in a parking-lot video, the road and buildings may form the background, while a moving person or vehicle becomes part of the foreground.

### Background-subtraction methods in the lecture

- **Simple background subtraction:** compares the current frame with one reference background image. It is easy to understand but can struggle if the background or lighting changes.
- **MOG (Mixture of Gaussians):** models the background using multiple Gaussian distributions, which can represent variation at a pixel over time.
- **MOG2:** an improved version that can adapt to changing backgrounds.
- **KNN background subtraction:** uses a K-Nearest Neighbors idea to classify pixels as foreground or background.

The source names OpenCV methods `createBackgroundSubtractorMOG2()` and `createBackgroundSubtractorKNN()` as examples of how these methods appear in a software library.

### Limitations
Shadows, moving leaves, changing illumination, rain, camera movement, and objects that remain stationary for a long time can confuse a background model.

## 6.9 Video Analytics

**Video analytics** automatically extracts useful information from video. Rather than relying on a person to watch every camera continuously, the system analyzes video and produces events, statistics, or alerts.

It may detect people, vehicles, crowds, entry and exit events, unusual movement, objects left behind, or movement into restricted areas.

### Video-analytics pipeline

```text
Video Camera
     ↓
Video Frames
     ↓
Preprocessing
     ↓
Object Detection
     ↓
Object Tracking
     ↓
Motion / Behavior Analysis
     ↓
Decision
     ↓
Alert or Report
```

## 6.10 Face Detection and Face Recognition

- **Face detection** finds the location of a face in an image or video.
- **Face recognition** identifies or verifies a person by using facial features.

A simplified recognition workflow is:

```text
Camera Frame
     ↓
Face Detection
     ↓
Extract Facial Features
     ↓
Create Feature Representation
     ↓
Compare with Stored Data
     ↓
Identity / Verification Result
```

Applications include smartphone unlocking, attendance, access control, and security. Real deployments need careful attention to privacy, consent, error rates, and bias.

## 6.11 Applications of Motion Analysis

### Medical imaging
Video and image sequences can show movement inside the body. Motion analysis can support heart-motion studies, blood-flow analysis, ultrasound video analysis, patient-movement monitoring, and rehabilitation tracking.

**Example:** an ultrasound sequence shows the heart expanding and contracting across frames. Motion analysis helps quantify or study that repeated movement.

### Autonomous vehicles
Cameras and other sensors help a vehicle understand its surroundings. Motion analysis tracks cars and pedestrians, estimates direction, studies traffic flow, and can support prediction of possible paths or collisions.

### Augmented reality
An AR application needs to estimate camera and scene movement so that virtual objects remain in the correct place. Feature tracking and optical flow can help estimate motion.

### Industrial surveillance
Factories can monitor workers, vehicles, machines, safety zones, and production lines. The system can detect abnormal movement or a possible safety violation and generate an alert.

### Smart surveillance
Computer Vision can identify intrusions, unusual crowd sizes, abandoned objects, vehicle movements, and predefined suspicious activity. These systems reduce the need for continuous manual monitoring, but they still need appropriate design, testing, and oversight.

## 6.12 Complete Motion-Analysis Pipeline

```text
Video
  ↓
Frame Extraction
  ↓
Preprocessing
  ↓
Motion Detection ─────── Object Detection
  ↓                            ↓
Background Subtraction      Object Tracking
  └──────────────┬─────────────┘
                 ↓
          Motion Analysis
                 ↓
           Video Analytics
                 ↓
       Decision / Prediction
                 ↓
          Alert / Application
```

### Example: smart parking system

1. A camera records the parking area.
2. The system extracts video frames.
3. Background subtraction separates likely moving objects from the static scene.
4. Object detection identifies cars.
5. Object tracking follows each car as it moves.
6. Motion analysis estimates direction and movement pattern.
7. Video analytics determines which parking spaces are occupied, as well as vehicle entry and exit.
8. The system displays the results in a smart-parking application.

## 6.13 Advantages and Challenges

### Advantages

- Automates repeated video monitoring.
- Supports real-time analysis.
- Follows objects across frames.
- Helps identify unusual events and improve security monitoring.
- Supports traffic analysis, healthcare, robotics, AR, and industrial automation.

### Challenges

- **Lighting changes:** brightness changes may look like motion.
- **Camera movement:** moving the camera can make much of the scene appear to move.
- **Occlusion:** another object may hide the target.
- **Fast motion:** movement between frames may be too large to estimate reliably.
- **Similar objects:** the tracker may confuse objects with similar appearance.
- **Weather:** rain, snow, fog, and shadows can reduce performance.
- **Computational cost:** dense flow and advanced tracking may require more processing power.

---

# Comparison Tables for Fast Revision

## 1. Classification, detection, segmentation, and tracking

| Task | Unit of analysis | Main question | Typical output |
|---|---|---|---|
| Image classification | Whole image | What is in this image? | One label or class scores |
| Object detection | Objects in a frame | What objects are present, and where? | Class, bounding box, confidence |
| Semantic segmentation | Each pixel | Which class does each pixel belong to? | Per-pixel class map |
| Instance segmentation | Individual object pixels | Which pixels belong to each separate object? | Separate object masks |
| Object tracking | Objects over time | Where did this object move? | Locations and identities across frames |

## 2. Thresholding and clustering

| Method | How it groups pixels | Best-known benefit | Main limitation |
|---|---|---|---|
| Global thresholding | One intensity threshold for the whole image | Fast and simple | Sensitive to uneven lighting |
| Adaptive thresholding | Local thresholds | Handles shadows and changing brightness | More computation |
| Region growing | Adds similar neighbors from a seed | Creates connected regions | Sensitive to seed and similarity rule |
| K-means | Assigns pixels to the nearest of K centroids | Simple clustering of color/intensity | Must choose K; initialization affects results |
| Watershed | Builds boundaries between connected catchment regions | Separates touching objects | Noise may create false boundaries |
| Template matching | Slides a fixed template and scores similarity | Simple when appearance is stable | Sensitive to scale, rotation, and occlusion |

## 3. Important feature algorithms

| Algorithm | Main job | Important concept to remember |
|---|---|---|
| Roberts | Edge detection | Fast 2 × 2 diagonal kernels; noise-sensitive |
| Prewitt | Edge detection | 3 × 3 uniform gradient kernels |
| Sobel | Edge detection | 3 × 3 kernels with extra center weighting |
| Canny | Edge detection | Gaussian smoothing, gradients, thinning, double threshold, hysteresis |
| Harris | Corner detection | Studies intensity change when a window shifts |
| SIFT | Keypoint detection and description | Scale-space, orientation assignment, 128-D descriptor |
| SURF | Keypoint detection and description | Hessian approximation, box filters, integral images |
| ORB | Keypoint detection and description | FAST + rotated BRIEF; binary descriptor and Hamming distance |
| GLCM | Texture analysis | Counts gray-level pairs at a distance and direction |
| LBP | Texture analysis | Encodes local neighbor comparisons as a binary pattern |
| Gabor | Texture analysis | Responds to selected orientations and frequencies |

## 4. Smoothing versus sharpening

| Smoothing | Sharpening |
|---|---|
| Reduces local intensity variation | Emphasizes rapid intensity change |
| Often reduces noise | Can amplify noise |
| Can blur fine edges | Can make edges and details stand out |
| Mean, weighted average, Gaussian, median | Laplacian, unsharp masking, high-boost, gradients |

## 5. SIFT versus SURF versus ORB

| Point | SIFT | SURF | ORB |
|---|---|---|---|
| Main goal | Robust matching across scale and rotation | Robust features with improved speed | Very fast free feature extraction and matching |
| Detection idea | Difference-of-Gaussians scale space | Hessian approximation with box filters | FAST corners |
| Descriptor | 128-D floating point | 64-D or 128-D floating point | Binary, commonly 256 bits |
| Distance | Euclidean | Euclidean | Hamming |
| Typical fit | High-quality matching and reconstruction | Speed/robustness balance | Real-time, mobile, embedded, SLAM |

## 6. KNN versus SVM

| Point | KNN | SVM |
|---|---|---|
| Principle | Uses the labels of nearby examples | Learns a separating hyperplane with a large margin |
| Training | Little explicit model fitting | Model fitting is required |
| Prediction | Finds nearest stored examples | Applies the learned decision boundary |
| Key issue | Choice of K and distance measure | Training and model selection can be more complex |

## 7. CNN components

| Component | Role |
|---|---|
| Convolution | Finds local learned patterns |
| Feature map | Stores the response from a filter |
| ReLU | Replaces negative values with zero |
| Pooling | Reduces spatial size and computation |
| Flatten | Converts feature maps to a vector |
| Fully connected | Uses extracted features for the final decision |

## 8. R-CNN versus YOLO

| Point | R-CNN family | YOLO |
|---|---|---|
| Core approach | Region proposals and region processing | Direct prediction in one model pipeline |
| Original speed | Original R-CNN is slow | Designed for fast detection |
| Later change | Fast R-CNN shares image features; Faster R-CNN learns proposals | Modern versions improve multi-scale detection while retaining the direct approach |
| Typical use | Region-based detection pipelines | Real-time detection |

## 9. Motion methods

| Technique | Main purpose | Main limitation or consideration |
|---|---|---|
| Frame differencing | Detect changes between consecutive frames | Sensitive to lighting or camera movement |
| Sparse optical flow | Estimate motion of selected feature points | Tracks only selected points |
| Dense optical flow | Estimate motion across nearly all pixels | More computation |
| Lucas-Kanade | Estimate local motion of selected feature points | Assumes brightness constancy, small movement, and similar local motion |
| Background subtraction | Separate foreground from background | Background changes and shadows cause errors |
| Object detection | Locate objects in a frame | Does not by itself maintain identity over time |
| Object tracking | Follow object locations and identities across frames | Occlusion and similar-looking objects cause difficulties |
| Video analytics | Extract useful events and measurements from video | Depends on detection, tracking, data, and computing resources |

---

# Important Formulas and Terms

| Topic | Formula or rule | Meaning |
|---|---|---|
| Pixel transformation | `g(x, y) = a f(x, y) + b` | `a` changes contrast scaling; `b` shifts brightness |
| Quantization levels | `2^b` | Number of representable levels with `b` bits |
| Frame differencing | `D = |Frame_t - Frame_(t-1)|` | Measures pixel-wise change between consecutive frames |
| ReLU | `ReLU(x) = max(0, x)` | Negative inputs become zero; positive inputs remain unchanged |
| Harris response | `R = det(M) - k(trace(M))^2` | Corner response from the local structure matrix |
| Accuracy | `(TP + TN) / (TP + TN + FP + FN)` | Share of all predictions that are correct |
| Precision | `TP / (TP + FP)` | Share of positive predictions that are correct |
| Recall | `TP / (TP + FN)` | Share of actual positives the model finds |
| SIFT descriptor | `4 × 4 × 8 = 128` | Number of descriptor values |
| SURF descriptor | `4 × 4 × 4 = 64` | Standard descriptor size in the lecture; an extended 128-D version exists |
| Original R-CNN | About 2,000 region proposals per image | Illustrates why repeated CNN processing is expensive |

## Important terms in plain language

- **Pixel:** one picture element in a digital image.
- **Resolution:** the image's pixel dimensions.
- **Sampling:** selecting the discrete pixel positions.
- **Quantization:** mapping pixel intensity to allowed discrete values.
- **Kernel / mask:** a small matrix used to process a neighborhood.
- **Feature map:** the output produced by applying a filter.
- **Feature descriptor:** a numerical summary of a local image feature.
- **Keypoint:** an important image location, often a corner or distinctive point.
- **Bounding box:** a rectangle around a detected object.
- **Centroid:** the center of a cluster or region, depending on the context.
- **Foreground:** the objects or regions of interest.
- **Background:** the surrounding or relatively stationary scene.
- **Optical flow:** apparent movement of image points between frames.
- **FPS:** frames per second.
- **Fine-tuning:** continuing to train a pretrained model on a new task.
- **Transfer learning:** reusing knowledge from a model trained on another task.

---

# How to Write Strong Exam Answers

Use these structures when a question asks you to explain a method. They help you write a complete answer without making the language complicated.

## For an algorithm question

1. **Definition:** state what the algorithm does in one or two sentences.
2. **Principle:** explain the central idea in simple words.
3. **Steps:** list the operations in the correct order.
4. **Diagram, flowchart, or formula:** include one when the source provides it or the question asks for it.
5. **Advantages and limitations:** explain what the method does well and where it struggles.
6. **Applications:** connect it to one or two real tasks.

For example, a Canny answer should name all five stages in order. A Lucas-Kanade answer should state all three assumptions and then explain how the algorithm tracks selected points.

## For a comparison question

Use a table with direct criteria such as purpose, input, working principle, output, advantages, limitations, and applications. Do not write two unrelated paragraphs and expect the difference to be clear.

## For a diagram question

Draw the main stages from top to bottom, label every box, and explain what happens at each stage. A correct flowchart plus a brief explanation is usually clearer than a large paragraph.

## For a numerical or formula question

Write the formula, define each symbol, substitute the given values, show the calculation, and state the result with a short interpretation. For accuracy, precision, and recall, first identify TP, TN, FP, and FN before using a formula.

## For an applications question

Avoid listing application names alone. Explain the link between the task and the technique. For example, background subtraction separates moving foreground objects from a relatively stationary background, which makes it useful in CCTV monitoring.

---

# Final-Exam Practice Questions

These questions follow the concepts and question styles in the supplied lecture notes. Practise writing complete answers without looking at the guide.

## Unit 1: Computer Vision Foundations

1. Define Computer Vision. Explain why it is important and give suitable applications.
2. Differentiate Image Processing and Computer Vision with examples.
3. Compare human vision and Computer Vision.
4. Explain the evolution of Computer Vision from hand-crafted features to deep learning.
5. Explain image classification, object detection, semantic segmentation, instance segmentation, and object tracking.
6. Describe low-level, mid-level, high-level, and cross-modal vision.
7. Explain the main challenges in Computer Vision.
8. Describe Computer Vision applications in healthcare and explain why validation and human oversight matter.
9. Draw and explain a Computer Vision system's components.
10. Explain the fruit-sorting example using the full vision-system pipeline.
11. Define pixel, intensity, resolution, spatial resolution, and DPI.
12. Compare RGB, grayscale, HSV, CMYK, and YCbCr color models.
13. Describe a Computer Vision pipeline for a surveillance system.
14. The lecture topic list names the pinhole camera model, but the supplied unit text provides no full derivation. Review the instructor's material if this is included in your exam.

## Unit 2: Image Processing Fundamentals

1. Define image representation, sampling, and quantization.
2. Differentiate sampling and quantization with examples.
3. Explain image enhancement and describe contrast enhancement, histogram equalization, denoising, and sharpening.
4. Explain scaling, rotation, translation, affine transformation, and perspective transformation.
5. Explain linear and non-linear pixel transformations.
6. Define spatial-domain filtering and distinguish point processing from neighborhood processing.
7. Explain how a kernel processes an image. Differentiate correlation and convolution.
8. Explain zero, replicate, mirror, and crop handling at image borders.
9. Compare mean, weighted-average, Gaussian, median, maximum, and minimum filters.
10. Explain the Laplacian operator with the 4-neighbour and 8-neighbour masks.
11. Explain unsharp masking and high-boost filtering step by step.
12. Differentiate smoothing and sharpening filters.
13. Explain the Fourier Transform and describe the frequency-domain filtering workflow.
14. Compare low-pass, high-pass, band-pass, notch, and band-reject filters.
15. Describe common image-noise types and suitable reduction methods.
16. Compare Roberts, Prewitt, and Sobel edge detectors.
17. Explain the five stages of the Canny edge detector.
18. Define erosion and dilation. Explain their effects on foreground shapes.

## Unit 3: Feature Detection and Extraction

1. Define a feature and explain the properties of a good feature.
2. Draw and explain the feature-based vision pipeline.
3. Explain edge detection and its role in feature extraction.
4. Explain the Harris corner detector, including flat, edge, and corner regions.
5. Write the Harris response expression and explain its terms.
6. Explain SIFT step by step.
7. Explain SURF and how integral images and box filters support faster computation.
8. Explain ORB and the roles of FAST and rotated BRIEF.
9. Compare SIFT, SURF, and ORB.
10. Define texture. Explain contrast, homogeneity, energy, and entropy.
11. Explain GLCM and list texture properties derived from it.
12. Explain the Local Binary Pattern (LBP) algorithm.
13. Describe Gabor filters and their role in texture analysis.
14. Explain contour, chain code, polygon approximation, convex hull, skeleton, moments, and Fourier descriptors.
15. Define feature matching and explain its stages.
16. Differentiate Euclidean distance, Hamming distance, and cosine similarity.
17. Compare BFMatcher and FLANN.
18. Explain Lowe's ratio test and RANSAC's role in rejecting incorrect matches.

## Image Segmentation and Related Methods

1. Define image segmentation and explain its applications.
2. Explain thresholding and distinguish global from adaptive thresholding.
3. Explain region growing step by step, including the role of seed selection.
4. Explain K-means clustering for image segmentation.
5. Describe the watershed algorithm and explain how it separates touching objects.
6. Explain template matching and discuss its limitations.
7. Explain the KNN classification algorithm.
8. Explain SVM and the meaning of a separating hyperplane and margin.
9. Describe Haar Cascade face detection.
10. Differentiate face detection from face recognition.
11. Define TP, TN, FP, and FN.
12. Explain accuracy, precision, and recall with their formulas and simple examples.

## Unit 5: Deep Learning in Computer Vision

1. Define Deep Learning and explain the layers of a neural network.
2. Define a neuron, weight, bias, and activation function.
3. Explain why CNNs are suitable for image processing and classification.
4. Explain convolution, feature maps, ReLU, pooling, flattening, fully connected layers, and output layers.
5. Draw and explain a complete CNN for cat-versus-dog classification.
6. Explain automatic feature learning in CNNs.
7. Differentiate image classification and object detection.
8. Define bounding boxes and confidence scores.
9. Explain original R-CNN and why it is slow.
10. Explain the changes from R-CNN to Fast R-CNN and Faster R-CNN.
11. Explain YOLO, the original grid idea, and Non-Maximum Suppression.
12. Compare R-CNN and YOLO.
13. Define transfer learning and fine-tuning.
14. Compare feature extraction and fine-tuning.
15. List advantages, applications, and limitations of YOLO.

## Unit 6: Motion Analysis and Applications

1. Define motion analysis, video, frame, and frame rate.
2. Draw and explain a video-processing pipeline.
3. Explain motion detection and frame differencing.
4. Define optical flow and explain its vector representation.
5. Compare sparse and dense optical flow.
6. Explain Lucas-Kanade optical flow and its three assumptions.
7. Differentiate object detection and object tracking.
8. Explain point, kernel-based, bounding-box, and detection-based tracking.
9. Define background subtraction and explain simple subtraction, MOG, MOG2, and KNN background subtraction.
10. Explain video analytics and draw its pipeline.
11. Differentiate face detection and face recognition.
12. Explain motion analysis applications in medical imaging, autonomous vehicles, augmented reality, industrial surveillance, and smart surveillance.
13. Draw and explain the complete motion-analysis pipeline.
14. List the advantages and challenges of motion analysis.
15. Explain a smart-parking system using motion detection, background subtraction, object detection, tracking, and video analytics.

---

# Quick Revision Sheet

- **Computer Vision:** interprets visual data and returns meaningful information or decisions.
- **Image Processing:** transforms or improves pixel data.
- **Sampling:** chooses pixel locations; controls spatial resolution.
- **Quantization:** chooses allowed pixel-intensity levels; controls intensity resolution.
- **Smoothing:** reduces local variation and some noise, but may blur edges.
- **Sharpening:** emphasizes boundaries and fine details, but may amplify noise.
- **Canny:** Gaussian smoothing → gradients → non-maximum suppression → double threshold → hysteresis.
- **Feature pipeline:** detect → describe → match → verify geometry → apply.
- **Harris:** detects corners by checking intensity change when a window shifts.
- **SIFT:** scale-space extrema, keypoint localization, orientation, 128-value descriptor.
- **SURF:** Hessian approximation and fast box filters; standard descriptor has 64 values.
- **ORB:** FAST detection + rotated BRIEF binary descriptor; Hamming distance.
- **GLCM:** gray-level pair counts; **LBP:** local binary neighbor pattern; **Gabor:** orientation/frequency-sensitive texture filter.
- **Global thresholding:** one threshold. **Adaptive thresholding:** local thresholds.
- **Region growing:** seed plus similar neighboring pixels.
- **K-means:** assign pixels to the nearest centroid and update centroids.
- **Watershed:** uses boundaries between regions to separate touching objects.
- **KNN:** predicts from nearby labelled examples. **SVM:** learns a separating hyperplane.
- **Accuracy:** overall correctness. **Precision:** trustworthiness of positive predictions. **Recall:** fraction of actual positives found.
- **CNN:** convolution → ReLU → pooling, repeated → flatten → fully connected → output.
- **R-CNN:** region proposals and region processing. **YOLO:** direct, fast object detection in one model pipeline.
- **Transfer learning:** reuse previously learned features. **Fine-tuning:** continue training some or all model weights for the new task.
- **Motion detection:** identifies changes. **Optical flow:** estimates apparent point movement. **Tracking:** follows objects across frames.
- **Lucas-Kanade:** local feature-point tracking under brightness-constancy, small-motion, and similar-local-motion assumptions.
- **Background subtraction:** compares the current frame with a background model.
- **Frame differencing:** compares consecutive frames.
