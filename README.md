# Computer Vision: Consolidated Study Notes

These notes merge the six supplied lecture-note PDFs into one study document. They retain the source material's major definitions, workflows, algorithms, comparisons, examples, and applications while consolidating repeated explanations.

## Source units

1. **Unit 1:** Computer Vision: Overview, Scope, Applications, Vision Systems, and Digital Image Fundamentals
2. **Unit 2:** Image Processing Fundamentals
3. **Unit 3:** Feature Detection and Extraction
4. **Additional lecture:** Image Segmentation and Related Classification Topics
5. **Unit 5:** Deep Learning in Computer Vision, CNNs, Object Detection, and Transfer Learning
6. **Unit 6:** Motion Analysis and Applications

## How the units fit together

A practical computer-vision system usually follows this broad flow:

`Scene -> Image acquisition -> Preprocessing -> Feature extraction / learned representation -> Detection, classification, segmentation, or tracking -> Decision / action`

- **Image processing** prepares or transforms pixels.
- **Feature detection and extraction** finds useful structures and represents them numerically.
- **Segmentation** groups pixels into meaningful regions.
- **Deep learning** can learn image features and map them to classes or locations.
- **Motion analysis** studies changes across frames and helps systems track objects over time.

---

# Unit 1: Computer Vision Foundations

## 1. What is Computer Vision?

**Computer Vision (CV)** is a field of Artificial Intelligence that enables machines to interpret and analyze images, video frames, and other visual data, then produce meaningful information or decisions. The goal is not merely to store or display pixels. A vision system turns pixel data into labels, coordinates, motion estimates, scene descriptions, or actions.

### Why study it?

- Visual data appears in photographs, video, satellite imagery, and medical scans.
- CV automates work that traditionally required visual inspection.
- It supports autonomous vehicles, robotics, healthcare, retail, surveillance, agriculture, manufacturing, and augmented reality.
- Modern deep-learning systems learn many useful visual representations directly from data.

## 2. Human vision versus computer vision

| Aspect | Human vision | Computer vision |
|---|---|---|
| Input | Continuous light sensed by the retina | Pixel grids from images or video, and sometimes depth/sensor data |
| Processing | Biological neural pathways | Algorithms running on CPUs, GPUs, or specialized hardware |
| Learning | Lifelong and strongly contextual | Training on labeled or unlabeled data and programmed procedures |
| Robustness | Often handles occlusion, lighting, and noise well | Can fail under distribution shift, unusual lighting, or occlusion |
| Scale | A person usually attends to a limited scene at a time | Systems can process large collections and parallel workloads |

## 3. Image processing versus computer vision

**Image processing** applies operations to pixels to improve, restore, transform, or prepare an image. Its output is usually another image. Examples include denoising, sharpening, resizing, contrast enhancement, compression, and thresholding.

**Computer vision** interprets visual content. Its output may be a class label, bounding box, segmentation mask, identity, motion estimate, or decision. Examples include identifying a cat, finding a pedestrian, tracking a car, or detecting a tumour region.

| Criterion | Image processing | Computer vision |
|---|---|---|
| Main goal | Change or improve image data | Infer meaning from visual data |
| Typical output | Processed image | Labels, coordinates, predictions, or actions |
| Common methods | Filters, histogram operations, morphology, transforms | Pattern recognition, machine learning, CNNs, vision transformers |
| Typical role | Often a preprocessing stage | Often the interpretation stage |

**Example:** A security camera image may first undergo brightness adjustment and denoising. A vision model then detects a person near a door. The first step improves the image; the second interprets it.

A common combined pipeline is:

1. Acquire an image or video.
2. Preprocess it: denoise, resize, normalize, or enhance contrast.
3. Extract visual features or compute learned representations.
4. Classify, detect, segment, or recognize objects.
5. Use the result to label data, trigger an alert, or control a device.

## 4. Brief evolution of computer vision

| Period | Milestone in the lecture notes |
|---|---|
| 1960s | Early AI-related attempts to describe scenes symbolically, including the 1966 MIT Summer Vision Project |
| 1970s-1980s | Edge detection, low-level features, and early stereo vision |
| 1990s | Statistical methods, Eigenfaces, and feature descriptors |
| 2000s | Hand-crafted features such as SIFT and HOG combined with classifiers such as SVMs |
| 2012 onward | Deep-learning shift after AlexNet's ImageNet result |
| 2015-2020 | Region-based detectors, segmentation networks, and real-time detectors such as YOLO and SSD |
| 2020 onward | Vision Transformers, self-supervised learning, and vision-language models such as CLIP |

The main historical shift is from manually engineered image features toward representations learned from data.

## 5. Core tasks in computer vision

| Task | What it answers | Typical output |
|---|---|---|
| Image classification | What is in the image? | One class or class probabilities |
| Object detection | What objects are present, and where? | Class labels, confidence scores, bounding boxes |
| Semantic segmentation | What class does each pixel belong to? | Per-pixel class map; it does not separate same-class instances |
| Instance segmentation | Which pixels belong to each individual object? | Separate masks for each instance |
| Object tracking | Where does the same object go over time? | Object locations and identities across frames |
| Pose estimation | Where are body joints or object orientation? | Keypoints or pose parameters |
| Action recognition | What action occurs across a sequence? | Activity or gesture label |
| 3D vision / depth estimation | What is the scene's three-dimensional structure? | Depth map or 3D reconstruction |
| Image generation / synthesis | What new visual content can be produced? | Generated, restored, or modified image |
| Image registration | How should two or more images align? | Geometric alignment or transform |

## 6. Technical scope and challenges

- **Low-level vision:** filtering, image enhancement, edge detection, and feature extraction.
- **Mid-level vision:** segmentation, grouping, motion estimation, and geometric reconstruction.
- **High-level vision:** object recognition, scene understanding, reasoning, and semantic interpretation.
- **Cross-modal vision:** combining visual data with text, audio, or other sensor measurements.

Major challenges include viewpoint and scale changes, illumination changes, occlusion, deformation, demand for labeled data, domain shift, computational cost, adversarial perturbations, privacy, surveillance misuse, and model bias.

## 7. Applications in AI and healthcare

### General applications

- **Autonomous vehicles and robotics:** lane and traffic-sign detection, pedestrian detection, obstacle avoidance, SLAM, grasping, and manipulation.
- **Security and surveillance:** face detection and recognition, intrusion detection, anomaly detection, crowd monitoring, and vehicle tracking.
- **Retail and manufacturing:** visual search, inventory monitoring, automated checkout, quality control, defect detection, and robotic assembly.
- **AR/VR:** gesture recognition, environment mapping, and stable placement of virtual objects.
- **Agriculture:** crop-health monitoring, weed/pest detection, and yield estimation.
- **Media:** video summarization, content moderation, and deepfake detection.

### Healthcare examples

- **Radiology:** detect patterns such as tumours, fractures, or pneumonia in X-rays and other scans.
- **Ophthalmology:** screen retinal images for diseases such as diabetic retinopathy or glaucoma.
- **Pathology:** analyze digitized microscope slides and support cancer grading.
- **Dermatology:** classify visible skin lesions from images.
- **Surgery:** support instrument tracking, image guidance, and robotic assistance.
- **Patient monitoring:** estimate posture, movement, falls, or activity.
- **Drug discovery and research:** analyze visual data from experiments and biological imagery.

Clinical systems require careful validation, representative data, privacy protection, bias checks, and appropriate human oversight. A model's output should not automatically replace clinical judgment.

## 8. Computer-vision surveillance pipeline

A typical surveillance system works through these stages:

1. **Image acquisition:** CCTV, IP, thermal, infrared, drone, or other cameras capture the scene.
2. **Preprocessing:** denoising, contrast enhancement, histogram equalization, resizing, and color-space conversion.
3. **Motion detection:** frame differencing, background subtraction, or optical flow reveals changes.
4. **Object detection:** models such as YOLO, SSD, or Faster R-CNN locate objects using bounding boxes.
5. **Object tracking:** methods such as Kalman filtering, SORT, Deep SORT, or optical flow follow objects and may maintain IDs.
6. **Face detection:** finds face locations, using methods such as Haar Cascades, HOG, MTCNN, or RetinaFace.
7. **Face recognition:** extracts features, compares them against stored records, and performs identification or verification.
8. **Activity and crowd analysis:** identifies actions, estimates crowd density, detects overcrowding, and studies flow.
9. **Automatic number-plate recognition (ANPR):** detect vehicle -> locate plate -> segment characters -> apply OCR -> optionally verify against a database.
10. **Decision and output:** produce an alert, report, record, or automated response.

Applications include traffic monitoring, airport and building security, patient monitoring, warehouse management, agricultural monitoring, industrial safety, and smart-city systems. Challenges include lighting changes, weather, shadows, occlusion, storage and compute requirements, dataset bias, privacy, and cybersecurity.

## 9. Components of a vision system

A vision system combines hardware and software to acquire an image, process it, infer information, and take action.

| Component | Purpose / examples |
|---|---|
| Camera / image-acquisition device | Captures 2D, 3D, line-scan, color, or monochrome images |
| Lighting / illumination | Makes useful features visible; examples include backlighting, ring lighting, diffuse lighting, LED, and structured lighting |
| Lens | Focuses light; parameters include focal length, field of view, aperture, and magnification |
| Image sensor | Converts incoming light to electrical/digital image data; common types include CCD and CMOS |
| Frame grabber / capture hardware | Transfers, buffers, and synchronizes image data |
| Processing unit | CPU, GPU, FPGA, or embedded processor executes algorithms |
| Image-processing software | Denoises, resizes, enhances contrast, filters, and thresholds images |
| Feature extraction / image analysis | Measures shape, size, color, texture, edges, or corners |
| Pattern-recognition / decision module | Uses template matching, machine learning, or deep learning to classify or recognize objects |
| Communication interface | Sends data and results to other systems |
| Output / control system | Issues alerts or controls actuators and downstream equipment |
| Database and storage | Stores images, features, models, and results |

**System flow:** `Object/scene -> Lighting -> Lens -> Camera/sensor -> Frame grabber -> Processing unit -> Image processing -> Feature extraction -> Pattern recognition -> Decision -> Output/control`.

**Fruit-sorting example:** a conveyor moves fruit under a camera; lighting and optics create a clear image; software extracts color and shape; a recognition module identifies the fruit; an actuator directs it into the correct bin.

## 10. Digital image fundamentals

A digital image can be represented as a two-dimensional function or matrix, often written as `I(x, y)` or `f(x, y)`, where `x` is the horizontal coordinate, `y` is the vertical coordinate, and the value stores brightness or color.

- **Pixel:** the smallest addressable picture element.
- **Binary image:** two values, typically 0 for black and 1 for white; used in OCR, documents, and barcodes.
- **Grayscale image:** intensity values; in a common 8-bit representation, 0 is black and 255 is white.
- **Color image:** often stores red, green, and blue values per pixel.
- **Resolution:** width x height in pixels; higher pixel counts typically preserve more detail but require more storage and processing.
- **Spatial resolution:** the amount of scene detail the image can distinguish.
- **DPI:** dots per inch, a physical printing/display density measure, not simply another name for pixel dimensions.

Common resolutions from the notes include 640x480 (VGA), 1280x720 (HD), 1920x1080 (Full HD), 2560x1440 (2K), 3840x2160 (4K), and 7680x4320 (8K).

### Color models

| Model | Representation / typical use |
|---|---|
| RGB | Red, Green, Blue channels; displays, cameras, and digital imagery. With 8 bits per channel, each channel ranges from 0 to 255. |
| Grayscale | Brightness only; useful in many inspection and analysis tasks. |
| HSV | Hue, Saturation, Value; useful for color-based analysis because it separates color characteristics from brightness more naturally than RGB. |
| CMYK | Cyan, Magenta, Yellow, Black; printing and publishing. RGB adds light; CMYK combines ink. |
| YCbCr | Y represents brightness/luma; Cb and Cr represent blue- and red-difference chroma. Used in image/video compression and broadcasting. |

The source notes use an RGB example where `(255, 0, 0)` is red, `(0, 255, 0)` is green, `(0, 0, 255)` is blue, `(255, 255, 255)` is white, and `(0, 0, 0)` is black.

---

# Unit 2: Image Processing Fundamentals

## 1. Image representation, sampling, and quantization

### Image representation
A digital image stores intensity or color values at pixel positions in a matrix. The representation determines how software accesses, stores, and processes the image.

### Sampling
**Sampling** converts a continuous scene into discrete pixel locations and determines spatial resolution. Too few samples lose detail and distort shapes. More samples can preserve more detail but increase memory use and processing time.

### Quantization
**Quantization** assigns a finite set of intensity or color values to sampled pixels. It determines intensity resolution, while sampling determines spatial resolution.

For `b` bits per pixel, the number of representable levels is `2^b`. An 8-bit grayscale channel has `2^8 = 256` levels (0 through 255). Lower quantization can create visible intensity bands and quantization error.

| Concept | Determines | Common measure | What goes wrong when too low? |
|---|---|---|---|
| Sampling | Pixel locations / spatial resolution | Pixel dimensions | Detail loss, blur, shape distortion |
| Quantization | Available intensity levels | Bits / levels | Visible bands and coarse brightness transitions |

## 2. Image enhancement

Image enhancement makes an image more suitable for visual inspection or later processing.

- **Contrast enhancement:** increases separability between light and dark regions.
- **Histogram equalization:** redistributes intensity values to improve contrast.
- **Noise reduction:** removes unwanted intensity variation using filters such as Gaussian or median filters.
- **Sharpening:** emphasizes edges and fine detail, often through high-pass or derivative-based operations.

## 3. Geometric image transformations

- **Scaling:** changes image size; interpolation may use nearest-neighbor or bilinear methods.
- **Rotation:** rotates an image around a chosen point and generally needs interpolation.
- **Translation:** shifts pixels along horizontal and vertical axes.
- **Affine transformation:** combines operations such as scaling, rotation, translation, and shearing; parallel lines remain parallel.
- **Perspective / projective transformation:** changes the apparent perspective; useful for rectifying planar objects photographed from an angle.

## 4. Pixel-based transformations

A general linear intensity transformation can be written as:

`g(x, y) = a f(x, y) + b`

Here `f(x, y)` is the original pixel value, `g(x, y)` is the output, `a` adjusts contrast, and `b` adjusts brightness. Real implementations must handle the valid intensity range, for example by clipping values to the supported range.

Common nonlinear transformations:

- **Image negative:** reverses intensity levels, making dark areas bright and bright areas dark.
- **Log transformation:** expands detail in low-intensity regions and compresses high intensities.
- **Gamma / power-law correction:** remaps intensity nonlinearly; the gamma parameter controls the mapping and helps adjust image brightness/response.
- **Histogram equalization:** uses the image's intensity distribution to improve global contrast.
- **Thresholding:** converts intensity values into regions based on a threshold.

## 5. Spatial-domain filtering

The **spatial domain** is the image's normal pixel-coordinate space. Filtering operates directly on pixel values and often uses a small neighborhood or **kernel/mask**.

General form:

`g(x, y) = T[f(x, y)]`

- **Point processing:** the output depends only on the current pixel (1x1 neighborhood). Examples include negative, gamma, thresholding, and some contrast transforms.
- **Neighborhood processing:** the output depends on nearby pixels (such as a 3x3 window).

### How spatial filtering works

Move a kernel across the image. At each location, combine the kernel coefficients with the corresponding pixel values, commonly through a sum of products.

- **Correlation:** applies the kernel as written.
- **Convolution:** rotates the kernel by 180 degrees before applying it. Symmetric kernels commonly produce the same result under both operations.
- **Padding:** handles kernel positions near image boundaries.
  - Zero padding fills outside pixels with 0 and may darken borders.
  - Replicate padding repeats the nearest edge pixel.
  - Mirror/reflect padding reflects image content across the border.
  - Cropping computes only where the complete kernel fits and therefore reduces output dimensions.

Spatial filters can be classified by linearity (linear or nonlinear) and effect (smoothing or sharpening).

### Smoothing filters

Smoothing filters blur local variations and reduce some noise. They can also erase small details and soften edges.

| Filter | Core operation | Best-known property / limitation |
|---|---|---|
| Mean / box filter | Replaces a pixel with the neighborhood average; the 3x3 version uses nine equal weights, each scaled by 1/9 | Simple; blurs edges and fine detail |
| Weighted average | Gives nearby center pixels higher weights; example 3x3 kernel uses rows `[1,2,1]`, `[2,4,2]`, `[1,2,1]`, scaled by 1/16 | Less blur than a uniform average of the same size |
| Gaussian | Uses weights sampled from a Gaussian function; standard deviation `sigma` controls smoothing strength | Smooth, natural blur; larger `sigma` gives stronger smoothing |
| Median | Replaces the pixel by the median of neighborhood values | Effective for salt-and-pepper noise and preserves edges better than averaging |
| Max | Replaces a pixel with the maximum neighborhood value | Can reduce dark/pepper noise or highlight bright points |
| Min | Replaces a pixel with the minimum neighborhood value | Can reduce bright/salt noise or highlight dark points |

Larger averaging kernels blur more strongly and discard more detail. The median filter is a nonlinear order-statistics filter, not a weighted sum.

### Sharpening filters

Sharpening emphasizes edges, fine structures, and rapid intensity changes. It also amplifies noise.

- **First derivatives / gradient:** respond to intensity changes and often produce thicker edge responses.
- **Second derivatives:** respond strongly to thin details and noise; can produce double responses around step edges and zero-crossings near edge locations.
- **Laplacian:** an isotropic second-order derivative operator. Common discrete kernels in the notes are:

4-neighbor form:

```text
 0   1   0
 1  -4   1
 0   1   0
```

8-neighbor form:

```text
 1   1   1
 1  -8   1
 1   1   1
```

The Laplacian highlights intensity discontinuities. To sharpen an image, combine the Laplacian result with the original, using addition or subtraction according to the kernel's sign convention.

- **Unsharp masking:** blur the image, subtract the blurred image from the original to obtain a detail mask, then add the mask back to the original.
- **High-boost filtering:** increases the amount of detail added back; the notes describe `k = 1` as standard unsharp masking, `k > 1` as high-boost, and `0 < k < 1` as reduced sharpening.
- **Gradient-based sharpening:** uses horizontal and vertical gradient components to emphasize rapid intensity changes.

| Smoothing | Sharpening |
|---|---|
| Low-pass effect; attenuates high frequencies | High-pass effect; attenuates low frequencies relative to detail |
| Reduces noise and blurs small variation | Emphasizes boundaries and fine detail |
| May soften edges | May amplify noise |
| Mean, weighted average, Gaussian, median | Laplacian, unsharp mask, high-boost, gradient operators |

## 6. Frequency-domain filtering

The **frequency domain** represents an image in terms of how quickly intensity values change, rather than only where pixels occur.

- **Low frequencies:** slowly changing areas, broad illumination variations, and smooth backgrounds.
- **High frequencies:** rapid changes, edges, fine details, and some noise.

The **Fourier Transform** decomposes an image into frequency components. The inverse transform converts a filtered frequency representation back into a spatial image.

### Frequency-domain workflow

1. Apply FFT to the input image to obtain its frequency representation `F(u, v)`.
2. Shift the zero-frequency component to the center if needed for filtering/visualization.
3. Multiply the spectrum by a filter mask `H(u, v)`.
4. Undo the shift and apply inverse FFT.
5. Use the real part or magnitude as appropriate to obtain the output image.

| Filter | Effect | Typical use |
|---|---|---|
| Low-pass | Keeps low frequencies and attenuates high frequencies | Smooth images or reduce high-frequency noise |
| High-pass | Keeps high frequencies and attenuates low frequencies | Sharpen edges and fine details |
| Band-pass | Keeps a selected frequency interval | Isolate selected textures or patterns |
| Notch / band-reject | Removes a narrow frequency or band | Suppress periodic interference |

## 7. Image noise and denoising

Image noise is unwanted variation in pixel intensity introduced during capture, low-light imaging, electronics, transmission, or compression.

| Noise type | Typical appearance / cause | Suitable method from the notes |
|---|---|---|
| Gaussian | Fine random grain, often associated with sensor/electronic noise | Gaussian smoothing; mean filtering may also smooth it |
| Salt-and-pepper | Scattered black and white pixels | Median filter; min/max filters target dark/bright impulses respectively |
| Poisson / shot | Signal-dependent noise from photon-counting statistics | Depends on the imaging setup; the notes describe the noise type but do not prescribe one universal filter |
| Speckle | Granular multiplicative pattern in ultrasound, radar, or SAR | Choose a filter suitable for the imaging model; no single method is specified in the notes |
| Periodic | Repeating patterns from electrical or mechanical interference | Notch or band-reject frequency filtering |

Other methods in the source include **bilateral filtering**, which attempts to denoise while preserving edges, and **Wiener filtering**, which uses signal/noise statistics and can address blur plus noise. Bilateral filtering costs more computation; Wiener filtering depends on useful noise/signal statistics.

## 8. Edge detection

An **edge** marks a sharp change in image intensity and often corresponds to an object boundary. Gradient operators estimate the change in horizontal and vertical directions.

- Gradient components are often denoted `Gx` and `Gy`.
- Gradient magnitude indicates edge strength; gradient direction indicates orientation.

### Classical operators

**Roberts Cross:** uses 2x2 diagonal-difference kernels. It is fast but sensitive to noise.

**Prewitt:** uses 3x3 kernels with uniform weights. It is straightforward but generally more noise-sensitive than Sobel.

Prewitt kernels shown in the notes:

```text
Gx:                 Gy:
-1  0  1           -1 -1 -1
-1  0  1            0  0  0
-1  0  1            1  1  1
```

**Sobel:** also uses 3x3 kernels but weights the central row/column by 2, adding some smoothing during gradient estimation.

```text
Gx:                 Gy:
-1  0  1           -1 -2 -1
-2  0  2            0  0  0
-1  0  1            1  2  1
```

### Canny edge detector

Canny aims for good detection, accurate localization, and a single response per edge. Its stages are:

1. **Gaussian smoothing:** reduce noise before differentiation.
2. **Gradient calculation:** calculate magnitude and direction, commonly with Sobel.
3. **Non-maximum suppression:** retain local maxima along the gradient direction to thin the edges.
4. **Double thresholding:** classify pixels as strong, weak, or non-edges using high and low thresholds.
5. **Edge tracking by hysteresis:** retain weak edges only when connected to strong edges.

Canny generally produces thinner, cleaner, more connected edges than a simple gradient threshold, but involves more steps and computation.

## 9. Morphological operations

Morphological operations use a **structuring element** to change shapes and structures, commonly in binary images.

- **Erosion:** shrinks foreground/white regions and can remove small isolated white noise.
- **Dilation:** expands foreground/white regions and can fill small gaps or grow objects.

They support noise cleanup, boundary processing, shape analysis, and preparation for segmentation. The source notes emphasize erosion and dilation as the two basic operations.

---

# Unit 3: Feature Detection and Extraction

## 1. What is a feature?

A **feature** is a distinctive image structure that helps solve a task. Examples include corners, edges, blobs, textured patches, contours, and regions. Feature-based systems try to find meaningful locations, describe their local appearance numerically, and match them between images.

### Properties of a good feature

| Property | Meaning |
|---|---|
| Repeatability | Detect the same physical point across images despite expected changes |
| Distinctiveness / informativeness | Make it possible to distinguish a feature from other features |
| Locality | Describe a local region, helping with clutter and partial occlusion |
| Quantity | Supply enough features for robust matching or estimation |
| Accuracy | Localize the keypoint precisely in position, scale, and/or shape |
| Efficiency | Compute fast enough for the intended application |

A flat region such as a clear sky contains little distinguishing information. A corner on a building is easier to localize and match.

## 2. Feature-based vision pipeline

1. **Detection:** find candidate keypoints or regions, such as Harris corners.
2. **Description / extraction:** encode each detected neighborhood as a descriptor vector.
3. **Matching:** compare descriptors across images using a distance or similarity metric.
4. **Geometric verification / application:** reject unreliable correspondences, often with RANSAC, then estimate geometry or solve the task.

Applications include panorama stitching, image registration, object recognition, face/fingerprint comparison, camera calibration, AR, visual odometry, SLAM, medical scan alignment, and 3D reconstruction.

## 3. Edge detection: gradient operators and Canny

Edges correspond to regions of high spatial derivatives. Common classical operators include Roberts Cross, Prewitt, and Sobel. Canny first smooths with a Gaussian, computes gradients, thins responses with non-maximum suppression, applies two thresholds, and uses hysteresis to connect weak edges to strong ones. Edge maps support lane detection, PCB inspection, paper-boundary detection, and medical boundary preprocessing.

## 4. Corner detection: Harris detector

Corners localize a point in both image directions. Along a straight edge, a point can be ambiguous in the direction of the edge; this is often described as the **aperture problem**. A corner produces a strong intensity change when a window shifts in any direction.

### Window-shift intuition

- **Flat region:** little change for a shift in any direction.
- **Edge:** large change across the edge, small change along it.
- **Corner:** large change in both directions.

### Harris corner detector workflow

1. Compute image derivatives `Ix` and `Iy`, for example with Sobel.
2. Calculate `Ix^2`, `Iy^2`, and `IxIy` at each pixel.
3. Apply a local Gaussian window to aggregate the values into the **second-moment matrix / structure tensor** `M`.
4. Calculate a corner response `R`; the standard Harris response is `R = det(M) - k(trace(M))^2`.
5. Threshold `R` to retain strong candidate corners.
6. Apply non-maximum suppression so one local peak represents each corner.

The eigenvalues of `M` indicate how the window intensity changes along the two principal directions: two small eigenvalues suggest a flat region; one large and one small suggest an edge; two large eigenvalues suggest a corner.

**Extensions in the notes:**

- **Harris-Laplace:** adds scale selection by looking for a characteristic scale in the Laplacian-of-Gaussian response.
- **FAST (Features from Accelerated Segment Test):** tests a circle of 16 pixels around a candidate; a sufficiently long contiguous arc of brighter or darker pixels indicates a corner. It avoids the more expensive structure-tensor calculation and is used by ORB.

Corner applications include checkerboard-based camera calibration, video stabilization, motion capture, structure-from-motion, and SLAM.

## 5. Feature descriptors: SIFT, SURF, and ORB

A detector answers **where** a feature lies. A descriptor describes **what the local feature looks like**, allowing the computer to match it between images.

### SIFT: Scale-Invariant Feature Transform

SIFT provides strong scale and rotation invariance. The source notes outline four stages:

1. **Scale-space extrema detection:** blur the image at multiple scales and compute Difference of Gaussians (DoG); candidate extrema are compared across neighboring positions and scales.
2. **Keypoint localization:** refine candidate location and scale; discard low-contrast points and poorly localized edge responses.
3. **Orientation assignment:** create a gradient-orientation histogram around each keypoint; the dominant orientation anchors the descriptor.
4. **Descriptor generation:** rotate a local neighborhood to the keypoint orientation, divide it into 4x4 subregions, and compute 8-bin orientation histograms, yielding a `4 x 4 x 8 = 128`-dimensional descriptor. Normalize it to reduce sensitivity to illumination changes.

Strengths: strong scale/rotation robustness and useful for demanding matching and 3D reconstruction. Limitation: slower than ORB and heavier than a binary descriptor.

### SURF: Speeded-Up Robust Features

SURF aims to retain useful robustness while reducing computation. It uses box-filter approximations of Gaussian derivatives and integral images. It detects blobs with an approximate Hessian determinant and estimates orientation from Haar-wavelet responses.

Its usual descriptor divides a window into a 4x4 grid and records four summary values per cell, resulting in a 64-dimensional descriptor; an extended 128-dimensional variant also exists. The notes characterize SURF as faster than SIFT, with a balance between accuracy and speed.

### ORB: Oriented FAST and Rotated BRIEF

ORB combines:

- **FAST** for rapid corner/keypoint detection.
- A corner measure to rank candidates.
- An intensity-centroid method to estimate orientation.
- **BRIEF / rotated BRIEF (rBRIEF)** for a binary descriptor based on intensity comparisons between pixel pairs.

The notes describe a typical 256-bit descriptor. Rotation steering helps ORB handle image rotation. Binary descriptors use Hamming distance and are economical for real-time, mobile, embedded, and SLAM applications.

### SIFT versus SURF versus ORB

| Criterion | SIFT | SURF | ORB |
|---|---|---|---|
| Detector | DoG scale-space extrema | Hessian approximation with box filters | Oriented FAST |
| Descriptor | Floating point, 128-D gradient histograms | Floating point, commonly 64-D; extended 128-D | Binary, commonly 256 bits |
| Matching distance | Euclidean | Euclidean | Hamming |
| Rotation invariance | Yes | Yes | Yes |
| Scale invariance | Strong | Approximate / robust across scales | More limited; scale pyramid can help |
| Speed in source notes | Slowest of the three | About 3-5x faster than SIFT | About 10-100x faster than SIFT |
| Best fit | Offline high-accuracy matching and 3D reconstruction | Robustness with improved speed | Real-time systems, mobile vision, embedded use, SLAM |

The notes describe ORB as free/open-source and identify SIFT's original patent as expired in 2020. SURF historically had patent/licensing restrictions.

Memory aid: **FAST detects; BRIEF describes; ORB combines them and adds orientation handling; ORB-SLAM uses ORB features for camera localization and mapping.**

## 6. Texture analysis

**Texture** describes local patterns of intensity or color. The notes distinguish:

- **Smooth texture:** little local variation, e.g. white paper or a painted wall.
- **Rough texture:** frequent changes, e.g. sand, stone, or brick.
- **Regular texture:** repeating patterns, e.g. tiles or window grills.
- **Random texture:** no clear repeating pattern, e.g. clouds, smoke, forest, or hair.

Important texture statistics:

- **Contrast:** difference between neighboring pixel values.
- **Homogeneity:** similarity among nearby pixels.
- **Energy:** repetitiveness / uniformity of a texture pattern.
- **Entropy:** randomness or unpredictability.

### Texture methods

| Method | Main idea | Best use / limitation from the notes |
|---|---|---|
| Statistical methods | Compute mean, variance, standard deviation, contrast, and related pixel statistics | Fast and broadly useful; smooth regions tend to have low variance |
| Structural methods | Find repeating texture primitives and their arrangement | Works well for tiles/fabrics; less useful for random textures |
| Transform-based methods | Transform image into frequency/scale representations | Helps identify texture scale and orientation |
| GLCM (Gray Level Co-occurrence Matrix) | Count how often gray-level pairs occur at a chosen spatial relationship | Derive contrast, homogeneity, energy, entropy, and correlation; used in medical images, leaves, fabrics, and remote sensing |
| LBP (Local Binary Pattern) | Compare neighbors with a center pixel, write 1 if neighbor >= center and 0 otherwise, then encode the pattern | Fast, useful for face recognition and texture classification; sensitive to image noise |
| Gabor filter | Direction- and frequency-tuned filter | Good for oriented texture such as fingerprint ridges; multiple filters can be slower |
| Fourier transform | Analyze frequency content | Useful for repeated or periodic texture patterns |
| Wavelet transform | Analyze frequency and location/scale together | Helps identify what pattern occurs and where it occurs |

### LBP procedure

1. Select a center pixel.
2. Compare each neighbor to the center.
3. Write 1 when neighbor >= center; otherwise write 0.
4. Read the binary pattern in a defined order.
5. Convert the binary pattern to a numeric code.

## 7. Shape representation

Shape descriptors convert an object's boundary or region into numerical form so systems can recognize and compare objects.

| Technique | What it represents | Typical application from the notes |
|---|---|---|
| Contour | Outer boundary points | Object counting, fingerprint or leaf analysis, industrial inspection |
| Chain code | Boundary as a sequence of direction steps | OCR, character recognition, robot navigation |
| Polygon approximation | Simplifies a contour to fewer corner points | Traffic signs, buildings, map processing |
| Convex hull | Smallest convex boundary enclosing the shape | Hand gestures, fruit grading, tracking |
| Skeleton | Centerline that preserves overall topology | Fingerprints, roads, blood vessels, handwriting |
| Moments | Numerical properties such as area, centroid, and orientation | Object tracking, shape comparison, grasping, medical analysis |
| Fourier descriptors | Frequency-based representation of a boundary | Signature verification, logo recognition, shape matching |

## 8. Feature matching and similarity measures

Feature matching finds corresponding keypoints between images of the same scene or object.

**Pipeline:** detect keypoints in image A -> extract descriptors -> detect keypoints in image B -> extract descriptors -> compare descriptors -> apply a metric/matcher -> retain matched features -> verify geometry as needed.

### Main similarity measures

| Measure | What it measures | Common descriptor types |
|---|---|---|
| Euclidean distance | Straight-line distance between numeric vectors; smaller means more similar | SIFT, SURF |
| Hamming distance | Number of bit positions that differ; smaller means more similar | ORB, BRIEF, BRISK |
| Cosine similarity | Angle/directional similarity between vectors; near 1 means aligned, near 0 weakly related, near -1 opposite | Deep feature embeddings and image retrieval |

### Matchers

- **Brute-force matcher (BFMatcher):** compares every descriptor in one image against descriptors in the other and chooses close matches. Simple and exhaustive but slow on large collections.
- **FLANN:** approximate nearest-neighbor search avoids exhaustive comparison and scales better to large descriptor sets, with some approximation trade-off.
- **Lowe's ratio test:** compare the best match distance with the second-best. Accept a match when the best is sufficiently better; reject ambiguous matches where both candidates have similar distances.
- **RANSAC:** geometric verification can reject inconsistent matches before estimating a homography or other geometric relationship.

Good matches are distinctive and geometrically consistent. False matches can arise when unrelated features look similar.

---

# Additional Lecture: Image Segmentation and Related Topics

The supplied segmentation PDF also covers template matching, KNN, SVM, Haar Cascade face detection, and evaluation metrics. They are retained here because they appear in that source file alongside segmentation.

## 1. Image segmentation

**Image segmentation** divides an image into meaningful regions or objects so that each can be analyzed separately. It groups pixels based on properties such as intensity, color, texture, or neighborhood similarity.

Applications include tumour and organ delineation, road and pedestrian understanding, face-region localization, satellite mapping, and diseased-crop detection.

### Thresholding

Thresholding separates pixels by intensity. The source gives this example for a threshold of 128:

- If pixel value > 128, assign white (255).
- Otherwise, assign black (0).

Thus 50, 90, and 110 become black; 130, 170, and 250 become white.

**Global thresholding** uses one threshold for the full image. It is fast and simple, and works best under reasonably uniform lighting. A single threshold may fail when one part of the image is bright and another is in shadow.

**Adaptive thresholding** chooses thresholds for local regions. It handles uneven illumination and shadows better, but costs somewhat more computation.

| Global | Adaptive |
|---|---|
| One threshold for the whole image | Different thresholds across local regions |
| Faster and simpler | Usually more robust under uneven lighting |
| Best for uniform lighting | Best for shadows / nonuniform lighting |

### Region-based segmentation and region growing

Region-based methods group neighboring pixels with similar color, brightness, or texture. **Region growing** works as follows:

1. Choose a seed pixel.
2. Examine neighboring pixels.
3. Add a neighbor if it meets the similarity criterion.
4. Continue until no qualifying neighbors remain.

Advantages: produces connected regions and can provide good boundaries. Limitation: results depend on seed selection and similarity criteria. The lecture gives medical MRI segmentation as an example: select a seed in a target region and grow the region through similar pixels.

### K-means clustering

K-means is an unsupervised clustering algorithm that groups pixels into `K` clusters based on similarity. `K` is the chosen number of groups, e.g. two clusters for object/background or three for sky/tree/road.

Steps:

1. Choose `K`.
2. Initialize `K` centroids.
3. Assign each pixel to the nearest centroid.
4. Recompute the centroids from their assigned pixels.
5. Repeat assignment and update until the centroids stop changing or the algorithm meets a stopping condition.

Applications include color segmentation, image compression, medical imaging, satellite analysis, and object detection. Advantages include simplicity and speed. Limitations include needing `K` in advance, sensitivity to initialization, and difficulty with irregularly shaped objects.

### Watershed algorithm

Watershed targets touching or overlapping objects. The source uses a landscape analogy: image intensities define hills and valleys; as water fills valleys, boundaries form where neighboring catchment regions meet. The boundary is the **watershed line**.

Lecture workflow:

1. Convert the image to binary.
2. Identify the foreground/object region.
3. Identify the background.
4. Apply the watershed procedure.
5. Obtain separated objects.

Uses include counting touching cells, separating overlapping coins, medical segmentation, and object counting. It can produce good boundaries but is sensitive to noise and usually benefits from preprocessing.

## 2. Template matching

Template matching locates a small reference patch (template) inside a larger image.

1. Provide the larger image and the template.
2. Slide the template across image positions.
3. Calculate similarity at each position.
4. Select the position with the highest similarity.

Uses include logo and symbol finding, industrial quality inspection, and document analysis. It is straightforward and accurate when object scale and orientation remain similar. It struggles when an object rotates, changes size, or becomes partially occluded.

## 3. K-nearest neighbors (KNN)

KNN classifies a new sample by finding its `K` nearest known examples and applying majority vote. For regression, it averages neighboring target values. The algorithm is instance-based and requires little explicit training, but prediction can be slow for large datasets and the choice of `K` matters.

Applications listed in the source include face recognition, handwriting recognition, medical diagnosis, and recommendation systems.

## 4. Support vector machine (SVM)

SVM separates data classes using a decision boundary called a **hyperplane**. Its objective is to find a boundary with a large margin between classes.

Advantages in the notes: high accuracy, suitability for small datasets, and effectiveness with high-dimensional data. Limitations: greater complexity than KNN and slower performance on very large datasets.

| Feature | KNN | SVM |
|---|---|---|
| Learning style | Instance-based | Model-based |
| Training | Very little explicit training | Fits a separating model |
| Prediction | Can be slow because it searches neighbors | Often faster after training |
| Best fit in the notes | Smaller / simpler problems | More complex classification and high-dimensional data |

## 5. Haar Cascade face detection

**Face detection** identifies whether a face exists and where it is; it does not identify whose face it is.

A **Haar Cascade classifier** uses a trained model and simple light/dark patterns. It scans the image with windows and draws a rectangle around likely face regions.

Applications include face unlock, attendance, CCTV, and camera autofocus. Advantages: fast and suitable for real-time use. Limitations in the notes: lower accuracy for side or rotated faces, poor lighting, and occluded faces.

**Face detection versus face recognition:**

- Detection: find a face and return its location.
- Recognition: identify or verify the person by comparing facial features with stored data.

## 6. Evaluation metrics

Define:

- **TP (true positive):** correctly predicted positive.
- **FP (false positive):** incorrectly predicted positive.
- **FN (false negative):** actual positive that the model missed.

| Metric | Formula | Meaning |
|---|---|---|
| Accuracy | `(TP + TN) / (TP + TN + FP + FN)` or, in the lecture's simpler form, correct predictions / total predictions | Overall share of correct predictions |
| Precision | `TP / (TP + FP)` | Among predicted positives, how many were truly positive? |
| Recall | `TP / (TP + FN)` | Among actual positives, how many did the model find? |

Examples in the source:

- 90 correct predictions out of 100 gives 90% accuracy.
- 18 truly spam messages among 20 messages predicted as spam gives 90% precision.
- 20 detected positives among 25 actual positives gives 80% recall.

Precision concerns the reliability of positive predictions. Recall concerns missed positive cases.

---

# Unit 5: Deep Learning in Computer Vision

## 1. Deep learning and neural-network basics

**Deep learning** is a part of machine learning that uses artificial neural networks with multiple layers to learn patterns from data. In computer vision, the network learns useful image features from examples rather than requiring a person to specify every feature manually.

A neural network consists of:

- **Input layer:** receives data, such as pixel values.
- **Hidden layer(s):** transform the data and learn patterns.
- **Output layer:** produces predictions, such as class labels or probabilities.

A simplified neuron calculates a weighted sum of inputs, adds a bias, and passes the result through an activation function:

`output = activation(weighted sum + bias)`

For an image task, layers may learn increasingly complex features, progressing from edges to shapes, object parts, and whole objects.

## 2. Why CNNs?

A **Convolutional Neural Network (CNN)** is a neural network designed especially for image and spatial data. Images contain many pixels, and neighboring pixels have meaningful relationships. CNN filters examine local neighborhoods and share their weights across image locations, making them well suited to spatial patterns.

Applications listed in the notes include image classification, face recognition, object detection, medical image analysis, autonomous vehicles, facial-expression recognition, and digit/character recognition.

## 3. Main CNN building blocks

### Convolution layer

A small learnable filter, also called a **kernel**, slides across an image or feature map. Its responses highlight learned patterns such as edges, lines, corners, curves, textures, or more complex structures.

### Feature map

A **feature map** is the output produced when a filter operates across an image or previous feature map. Different filters can learn to respond to different features.

### ReLU activation

The **Rectified Linear Unit (ReLU)** applies:

`ReLU(x) = max(0, x)`

Negative values become zero; positive values remain unchanged. ReLU introduces nonlinearity and helps the network learn more complex patterns.

### Pooling

Pooling reduces the spatial size of feature maps and thus reduces computation. It keeps salient local information, but it can also discard detail.

- **Max pooling:** selects the largest value inside a window. For the source's 2x2 example containing values 2, 5, 1, and 3, max pooling outputs 5.

### Flatten

Flatten converts multi-dimensional feature maps into a one-dimensional vector so a dense classifier can consume them.

### Fully connected layer

A **fully connected (FC) layer** connects each neuron to every output from the previous layer and uses the extracted features to make a class prediction.

## 4. Standard CNN classification pipeline

`Input image -> Convolution -> ReLU -> Pooling -> Convolution -> ReLU -> Pooling -> Flatten -> Fully connected layer -> Output`

For a cat-versus-dog example:

1. Pass the image into the CNN.
2. Early convolutions respond to edges, lines, and corners.
3. Later convolutions combine low-level responses into shapes and object parts such as eyes, ears, and noses.
4. Pooling reduces feature-map size.
5. Flatten the feature maps and pass them to dense layers.
6. The output layer produces class scores or probabilities, such as cat 95% and dog 5% in the lecture's illustration.

The percentages are example model outputs, not a guaranteed level of accuracy.

## 5. Automatic feature learning

Traditional computer vision often relies on hand-designed features before classification. A CNN learns task-useful features directly from training images. This hierarchical feature learning is a central advantage of CNNs.

## 6. Object detection

**Object detection = object classification + object localization.** A detector identifies the class of each object and estimates its location.

A **bounding box** is commonly represented as `(x, y, width, height)` or corner coordinates `(x1, y1, x2, y2)`. Classification assigns a label to the whole image; detection can return several objects, each with its own class, confidence score, and box.

A broad detection pipeline is:

`Input image -> Feature extraction -> Object candidates / direct predictions -> Boxes and classes -> Remove duplicate boxes -> Final detections`

Popular approaches in the source include R-CNN, Fast R-CNN, Faster R-CNN, YOLO, SSD, and RetinaNet.

### R-CNN family

Original **R-CNN** uses region proposals and classifies each region:

1. Input image.
2. Generate roughly 2,000 region proposals.
3. Extract each proposed region.
4. Run CNN feature extraction for every region.
5. Classify each proposal.
6. Refine bounding boxes.
7. Produce final detections.

Its main bottleneck is computational cost: the original pipeline runs CNN processing repeatedly for many regions.

- **Fast R-CNN:** runs the CNN once over the complete image, then reuses the feature map for proposed regions.
- **Faster R-CNN:** adds a learned **Region Proposal Network (RPN)**, replacing the slower external proposal-generation stage with a learned mechanism.

R-CNN variants are multi-stage detectors and can deliver strong detection quality, but the original version is slow. Faster R-CNN improves proposal generation but may still not be the first choice when very high real-time speed dominates.

### YOLO: You Only Look Once

YOLO predicts object locations and classes directly in one model pass rather than running a separate region-proposal stage. The original design used a grid in which each cell was responsible for objects whose centers fell inside it; modern versions use more sophisticated multi-scale architectures.

YOLO predicts:

- **Bounding box:** where the object is.
- **Class:** what the object is.
- **Confidence:** how confident the prediction is.

### Non-Maximum Suppression (NMS)

A detector may output several overlapping boxes for one object. NMS compares overlapping candidates and retains the stronger, higher-confidence prediction while discarding redundant boxes.

### R-CNN versus YOLO

| Criterion | R-CNN family (especially original R-CNN) | YOLO |
|---|---|---|
| Basic idea | Region proposals followed by CNN-based classification | Direct end-to-end detection |
| Architecture | Multi-stage | Single model pipeline / single-stage in the lecture's comparison |
| Region proposal step | Yes in R-CNN-family designs; Faster R-CNN learns proposals with an RPN | No separate proposal stage |
| Speed | Original R-CNN is slow; later variants reduce its bottleneck | Designed for high speed and real-time use |
| Typical use | Detection pipelines emphasizing detection quality | Traffic, surveillance, pedestrian/vehicle detection, robotics, sports, and other real-time tasks |
| Limits discussed | Multiple stages add latency | Small objects and crowded scenes can be difficult; speed/accuracy trade-offs depend on model size and hardware |

A custom detection task, such as helmet versus no-helmet detection, still requires a suitable labeled dataset.

## 7. Transfer learning and fine-tuning

**Transfer learning** reuses knowledge learned by a model on one dataset/task for a related task. A model trained on a large dataset such as ImageNet may already represent edges, shapes, textures, and object parts. Reusing those features can reduce the data, time, and compute needed for a new task.

**Fine-tuning** continues training a pretrained model on the new dataset so it adapts to the target task.

Example: a pretrained image model may already recognize generic edges and textures. To classify cat versus dog, replace its final classifier with a new classifier and train it on cat/dog data.

### Feature extraction versus fine-tuning

| Criterion | Feature extraction | Fine-tuning |
|---|---|---|
| Pretrained model | Reused | Reused |
| Existing layers | Mostly frozen | Some existing layers unfrozen and updated |
| Main training focus | Newly added classifier/layers | New classifier plus selected earlier layers |
| Training time | Lower | Higher |
| Flexibility | Lower | Higher |
| Data needs | Often lower | Often higher |

Transfer learning is the broad reuse of learned knowledge. Fine-tuning is one way to adapt a pretrained model by training some or all of its weights on new data.

---

# Unit 6: Motion Analysis and Applications

## 1. Motion analysis and video processing

**Motion analysis** studies how objects move across a sequence of images or video frames. A still image describes what appears in one instant; video adds information about what changes over time.

A **video** is a sequence of frames. **Frame rate (FPS)** is the number of frames displayed or captured per second. Common examples in the notes are 24, 30, and 60 FPS; higher FPS generally yields smoother motion.

### General video-processing pipeline

`Video -> Read/extract frames -> Preprocessing -> Motion/object detection -> Tracking -> Analysis -> Output`

Common operations include frame extraction, resizing, denoising, color conversion, motion detection, object detection, tracking, video classification, display, and saving processed video.

## 2. Motion in video

Motion is a change in object position over time. Comparing consecutive frames can help determine:

- Whether movement occurred.
- Where an object moves.
- Direction and approximate speed of movement.
- Which object is moving.
- Whether movement appears normal or abnormal.

## 3. Optical flow

**Optical flow** estimates the apparent movement of pixels or image features between consecutive frames. A motion vector describes direction and magnitude; a longer vector indicates greater apparent movement.

- **Sparse optical flow:** estimates movement for selected important points, such as corners. It is more computationally economical.
- **Dense optical flow:** estimates movement for almost every pixel. It provides more detailed motion information but requires more computation.

Optical flow describes apparent image motion. Actual object or camera motion can be more complicated because of depth, illumination, occlusion, and camera movement.

## 4. Lucas-Kanade optical flow

Lucas-Kanade is a local method for estimating movement of selected feature points. It examines a small neighborhood around a point and assumes nearby pixels move approximately together.

### Assumptions

1. **Brightness constancy:** a point's brightness remains approximately constant between frames.
2. **Small motion:** movement between consecutive frames is relatively small.
3. **Similar local motion:** nearby pixels have approximately similar motion.

### Workflow

`Input video -> Select feature points -> Compare consecutive frames -> Estimate point movement -> Generate motion vectors -> Track points`

Applications include object tracking, camera-motion estimation, gesture recognition, video stabilization, AR, and robot vision.

## 5. Object detection versus object tracking

| Object detection | Object tracking |
|---|---|
| Finds and locates objects in an image/frame | Follows objects across frames |
| Answers: “Where is the object now?” | Answers: “Where did this object move, and is it the same one?” |
| Can operate independently on individual frames | Uses temporal information to maintain continuity/identity |
| Example: detect a car in one frame | Example: track the same car across a video |

Detection finds objects; tracking associates detections over time and maintains identity where possible.

## 6. Object-tracking techniques

- **Point tracking:** follows selected keypoints/features; Lucas-Kanade is an example.
- **Kernel-based tracking:** follows a region or appearance pattern; Mean Shift and CamShift are examples and work best when appearance remains reasonably stable.
- **Bounding-box tracking:** represents an object with a rectangle and updates the box as the object moves.
- **Detection-based tracking:** detects objects in frames and associates detections across time. The notes list SORT, Deep SORT, and ByteTrack for multi-object tracking.

## 7. Background subtraction

**Background subtraction** separates moving foreground objects from a relatively stationary background. A system builds or stores a background model, compares each current frame with it, and treats substantial differences as candidate foreground.

`Current frame -> Compare with background model -> Difference / foreground mask -> Moving-object candidates`

Methods in the notes:

- **Simple background subtraction:** compare the current frame with one reference background image.
- **MOG (Mixture of Gaussians):** models background pixels using multiple Gaussian distributions.
- **MOG2:** an improved adaptive mixture-of-Gaussians method for changing backgrounds.
- **KNN background subtraction:** uses a K-nearest-neighbors approach to classify pixels as foreground or background.

In OpenCV, the notes name `cv2.createBackgroundSubtractorMOG2()` and `cv2.createBackgroundSubtractorKNN()`.

Limitations: lighting changes, moving foliage, shadows, and camera motion can make foreground separation difficult.

## 8. Motion detection and frame differencing

Motion detection looks for changes between frames. One simple approach computes an absolute pixel difference:

`Difference = |Frame 2 - Frame 1|`

Large differences in a region suggest movement, subject to a threshold and the effects of noise or changing illumination.

Applications include CCTV, intruder detection, traffic monitoring, automatic doors, smart homes, industrial monitoring, and wildlife observation.

## 9. Video analytics

**Video analytics** automatically extracts useful information from video rather than requiring continuous manual observation.

`Camera -> Frames -> Preprocessing -> Object detection -> Tracking -> Motion/behavior analysis -> Decision -> Alert/report`

Possible outputs include people/vehicle counts, entry and exit events, crowd density, unusual movement, abandoned-object detection, restricted-area entry, and other predefined behaviors.

## 10. Face detection and recognition

- **Face detection:** finds whether/where a face appears.
- **Face recognition:** identifies or verifies whose face it is.

Typical recognition pipeline: `Camera -> Face detection -> Extract facial features -> Compare with stored data -> Identity/verification result`.

Applications include smartphone unlocking, attendance, access control, identity verification, and security. The source stresses privacy, consent, accuracy, and bias as important concerns.

## 11. Applications of motion analysis

### Medical imaging

Medical videos can show motion inside or outside the body. An ultrasound sequence may show a heart alternating between expansion and contraction; analysis can help study the movement.

### Autonomous vehicles

Vehicles combine cameras with other sensors such as LiDAR, radar, and GPS. Motion analysis can track pedestrians and other vehicles, estimate trajectories, study traffic flow, and support possible-collision detection.

Typical flow: `Camera -> Detect car/pedestrian -> Track -> Estimate movement -> Predict possible path -> Vehicle decision`.

### Augmented reality

AR adds virtual content to a real view. Feature tracking and optical flow help estimate camera and scene movement so virtual objects remain anchored in appropriate positions as the camera moves.

### Industrial and smart surveillance

Systems can monitor workers, machines, vehicles, safety violations, restricted-area entry, and production-line problems. Smart surveillance pipelines use detection, tracking, analysis, and automatic alerts.

### Other applications

CCTV and security, traffic systems, sports analysis, human activity recognition, robotics, industrial automation, face/object tracking, and smart parking.

## 12. Complete motion-analysis pipeline

`Video -> Frame extraction -> Preprocessing -> Motion detection / object detection -> Background subtraction where appropriate -> Object tracking -> Motion analysis -> Video analytics -> Decision or prediction -> Alert/application`

**Smart parking example:** capture video, extract frames, identify the background, detect cars, track each car, estimate movement, determine occupied/empty spaces and vehicle entry/exit, then display the result in a parking application.

## 13. Benefits and challenges

### Benefits

- Reduces the need for constant manual monitoring.
- Supports real-time monitoring and tracking.
- Helps detect abnormal activities and improve traffic management.
- Supports healthcare analysis, robotics, and industrial automation.

### Challenges

1. **Lighting changes:** can create false motion.
2. **Camera movement:** makes much of the scene appear to move.
3. **Occlusion:** objects hide one another temporarily.
4. **Fast motion:** can make matching and tracking difficult.
5. **Similar objects:** complicate identity association.
6. **Weather:** rain, snow, fog, and shadows degrade results.
7. **Computational cost:** advanced video analysis may need substantial processing power.

---

# Consolidated Comparison Tables

## 1. Classification, detection, segmentation, tracking

| Task | Unit of analysis | Main question | Output |
|---|---|---|---|
| Classification | Whole image | What is present? | One or more image labels |
| Detection | Individual objects in a frame | What is present, and where? | Labels + bounding boxes + confidence |
| Semantic segmentation | Pixels | What class does each pixel belong to? | Per-pixel class labels |
| Instance segmentation | Object pixels | Which pixels belong to each object instance? | Separate object masks |
| Tracking | Objects across frames | Where is the same object over time? | Frame-by-frame locations and identities |

## 2. Quick algorithm picker

| Goal | Technique emphasized in the notes | Main consideration |
|---|---|---|
| Find simple intensity boundaries | Roberts, Prewitt, Sobel | Fast; varying noise sensitivity |
| Obtain clean, thin edges | Canny | More stages; generally cleaner edge maps |
| Find corners/keypoints | Harris or FAST | Harris is structured; FAST is very fast |
| Match robust keypoints across scale | SIFT | Strong scale/rotation robustness; higher cost |
| Balance feature robustness and speed | SURF | Box filters and integral images speed computation |
| Real-time binary feature matching | ORB | Fast and free; Hamming distance |
| Group pixels by brightness | Thresholding | Global threshold assumes uniform illumination; adaptive helps with shadows |
| Grow a connected similar region | Region growing | Depends on seed and similarity criteria |
| Group pixels into K color/intensity clusters | K-means | Must choose K; initialization matters |
| Separate touching objects | Watershed | Noise-sensitive; preprocessing helps |
| Find a fixed-size known patch | Template matching | Sensitive to scale, rotation, and occlusion |
| Follow sparse points between frames | Lucas-Kanade / sparse optical flow | Assumes small local motion and brightness constancy |
| Isolate moving foreground | Background subtraction | Background and lighting changes can cause errors |
| Detect objects quickly in video | YOLO | Real-time speed; small/crowded objects can be challenging |
| Reuse learned image features | Transfer learning | Reduces training requirements for a related task |

## 3. High-yield formulas and rules

- **Image resolution:** `width x height` pixels.
- **Quantization levels:** `2^b` for `b` bits per pixel/channel.
- **Linear intensity transform:** `g(x, y) = a f(x, y) + b`.
- **Frame differencing:** `D = |Frame_t - Frame_(t-1)|`.
- **ReLU:** `max(0, x)`.
- **Harris corner response:** `R = det(M) - k(trace(M))^2`.
- **Precision:** `TP / (TP + FP)`.
- **Recall:** `TP / (TP + FN)`.
- **Accuracy:** correct predictions / all predictions. In confusion-matrix form: `(TP + TN) / (TP + TN + FP + FN)`.
- **SIFT descriptor:** `4 x 4 x 8 = 128` dimensions.
- **SURF descriptor:** typically 64 dimensions; extended variant 128 dimensions.
- **ORB descriptor:** commonly a 256-bit binary descriptor.
- **Original R-CNN:** about 2,000 proposals per image in the lecture notes.

---

# Exam Revision Questions

Use these to test recall after reading the notes. The list combines the topics and question styles visible in the supplied lecture material.

## Unit 1: Foundations

1. Define computer vision and explain how it differs from image processing.
2. Compare human vision with computer vision.
3. Differentiate classification, detection, semantic segmentation, instance segmentation, and tracking.
4. Describe the evolution of computer vision from hand-crafted features to deep learning.
5. Explain the low-, mid-, and high-level technical scope of computer vision.
6. Describe major computer-vision applications in healthcare and discuss deployment challenges.
7. Draw and explain the components of a vision system.
8. Explain pixels, intensity, resolution, spatial resolution, and DPI.
9. Compare RGB, grayscale, HSV, CMYK, and YCbCr.
10. Describe a surveillance or ANPR pipeline.

## Unit 2: Image processing

1. Distinguish image sampling from quantization.
2. Explain the effect of low spatial resolution and low intensity resolution.
3. Compare linear intensity transformation, logarithmic transformation, gamma correction, and histogram equalization.
4. Explain scaling, rotation, translation, affine, and perspective transformations.
5. Distinguish point processing from neighborhood filtering.
6. Explain correlation versus convolution and why image padding is needed.
7. Compare mean, weighted-average, Gaussian, median, min, and max filters.
8. Explain the Laplacian, unsharp masking, and high-boost filtering.
9. Distinguish spatial-domain and frequency-domain filtering.
10. List common image noise types and suitable denoising methods.
11. Compare Roberts, Prewitt, Sobel, and Canny edge detection.
12. Describe the five Canny stages in order.
13. Explain erosion and dilation with examples.

## Unit 3: Features

1. What properties make a feature suitable for matching?
2. Draw the four stages of a feature-based vision pipeline.
3. Explain the Harris detector and the flat/edge/corner cases.
4. Explain FAST and how ORB uses it.
5. Describe the four main stages of SIFT.
6. Compare SIFT, SURF, and ORB by detector, descriptor, distance measure, robustness, speed, and use case.
7. Define contrast, homogeneity, energy, and entropy in texture analysis.
8. Explain GLCM, LBP, Gabor filters, and transform-based texture methods.
9. Compare contour, chain code, polygon approximation, convex hull, skeleton, moments, and Fourier descriptors.
10. Distinguish Euclidean distance, Hamming distance, and cosine similarity.
11. Compare BFMatcher and FLANN. Explain Lowe's ratio test and RANSAC's role.

## Segmentation and related methods

1. Define image segmentation and list its major applications.
2. Compare global and adaptive thresholding.
3. Explain region growing and its dependence on the seed pixel.
4. Describe the K-means segmentation loop and its limitations.
5. Explain how watershed separates touching objects.
6. Describe template matching and its limitations.
7. Compare KNN and SVM.
8. Explain how a Haar Cascade finds face regions.
9. Differentiate face detection from face recognition.
10. Define accuracy, precision, and recall, and explain when precision or recall matters more.

## Unit 5: Deep learning and detection

1. Define a neuron, weight, bias, activation function, and neural-network layer.
2. Explain why CNNs suit image data.
3. Describe convolution, feature maps, ReLU, pooling, flattening, and fully connected layers.
4. Draw the complete CNN pipeline for cat-versus-dog classification.
5. Distinguish classification from object detection.
6. Explain bounding boxes and confidence scores.
7. Describe original R-CNN and explain why it is slow.
8. What changes did Fast R-CNN and Faster R-CNN introduce?
9. Explain YOLO, the original grid idea, and NMS.
10. Compare the R-CNN family with YOLO.
11. Define transfer learning and fine-tuning.
12. Compare feature extraction with fine-tuning.

## Unit 6: Motion analysis

1. Define video, frame, FPS, motion detection, optical flow, and video analytics.
2. Compare sparse and dense optical flow.
3. State the three Lucas-Kanade assumptions and describe its workflow.
4. Distinguish object detection from object tracking.
5. Explain point, kernel-based, bounding-box, and detection-based tracking.
6. Describe background subtraction and compare simple subtraction, MOG, MOG2, and KNN background subtraction.
7. Explain frame differencing and its main weakness.
8. Draw a video analytics pipeline.
9. Compare face detection and face recognition.
10. Explain motion-analysis applications in medical imaging, autonomous vehicles, AR, and smart surveillance.
11. List the major challenges in motion analysis.

---

# One-page memory sheet

- **Computer vision:** pixels in, meaningful information or decisions out.
- **Image processing:** image in, transformed image out.
- **Sampling:** where pixels are; spatial resolution.
- **Quantization:** which intensity values pixels can store; intensity resolution.
- **Smoothing:** reduces noise but can blur edges.
- **Sharpening:** highlights edges/details but can amplify noise.
- **Canny:** Gaussian smoothing -> gradients -> non-maximum suppression -> double threshold -> hysteresis.
- **Feature pipeline:** detect -> describe -> match -> geometrically verify/use.
- **Harris:** corners cause intensity changes in both directions.
- **SIFT:** 128-D floating descriptor, strong scale/rotation robustness.
- **SURF:** Hessian approximation + integral-image box filters, often 64-D.
- **ORB:** FAST + oriented/rotated BRIEF, binary descriptor, Hamming distance.
- **GLCM:** gray-level pair counts; **LBP:** binary neighborhood pattern; **Gabor:** orientation/frequency-tuned texture filter.
- **Thresholding:** intensity split; **region growing:** seed plus similar neighbors; **K-means:** assign to nearest centroid and update; **watershed:** separate touching regions.
- **Detection:** class + location. **Segmentation:** pixel-level regions. **Tracking:** same object across time.
- **CNN:** convolution -> activation -> pooling, repeated -> flatten -> dense classifier.
- **YOLO:** direct, fast detection in one model pass; **R-CNN:** region-proposal family.
- **Transfer learning:** reuse pretrained knowledge; **fine-tuning:** continue training some/all weights for the new task.
- **Optical flow:** apparent movement of image points; **Lucas-Kanade:** local sparse point motion under small-motion/brightness/local-similarity assumptions.
- **Background subtraction:** compare current frame with background; **frame differencing:** compare consecutive frames.
- **Precision:** trustworthiness of positive predictions; **recall:** share of actual positives found; **accuracy:** overall correctness.

---

## Source note

This document summarizes the six user-supplied PDFs. It merges repeated material and keeps the source's examples and terminology. A few PDF equations and symbols did not extract cleanly from the source text, so the notes describe those ideas in words where necessary rather than pretending the damaged extraction was exact. For instructor-specific equation notation, use the original page image as the authority.
