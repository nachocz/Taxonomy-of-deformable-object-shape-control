# A guide for deformable object shape control method characterisation

---
This repository provides a structured framework for the characterisation of deformable object shape control methods based on criteria introduced in our paper "Taxonomy of deformable object shape control."

# Deformable object shape control taxonomy
---
The criteria in our taxonomy are organised into four main groups, as illustrated  in the shape control scheme below:

<img src="https://github.com/user-attachments/assets/b434cd10-bb9c-4b2f-b9a9-0cfaae82c948" alt="scheme" width="400">

Explore each criterion by expanding the drop-down menu (click on them). Each drop-down includes insightful questions and examples to assist you in effectively applying the criteria:

## **A. Deformable Object: System Characteristics**
<details>
<summary> A1. Object's geometry</summary>
    
- What are the intrinsic dimensions of the object?: (1D, 2D, or 3D)
    - In other words, what is the minimum number of dimensions needed to refer to different points within the object's domain?
    - *For example, regardless of its embedding, all points on a deformable linear object (DLO, e.g, a cable) can be referred to with a single parameter (1D), a sheet of paper requires at least two parameters (2D), and a dense foam piece necessitates three parameters to refer to all its material points (3D).*
      
- What are the extrinsic dimensions of the object in the shape control task?: (1D, 2D, or 3D)
    - In other words, what are the dimensions of the space in which the object is being manipulated? Does this space match the object's intrinsic dimensionality or is it larger?
    -  *For instance, consider a cable with 1D intrinsic dimensions. If fitted within a tube, it can be either stretched or compressed (deformation occurring along a 1D path), bent over a table (deformation occurring within a 2D plane), or twisted into a spring-like spiral shape (deformation occurring in 3D space).*
 
Possible combinations of intrinsic and extrinsic object dimensionalities:

<img src="https://github.com/user-attachments/assets/54731d4f-6d88-407e-9a38-3bb989840bc2" alt="scheme" width="400">

  - *Some additional practical examples of object geometry analysis*:
    - *A spring constitutes an open 1D intrinsic, 3D extrinsic geometry.*
    - *An inflated balloon constitutes a closed 2D intrinsic, 3D extrinsic geometry.*
    - *A cable manipulated on a table constitutes an open 1D intrinsic, 2D extrinsic geometry.*

- Is the object's geometry **open** or **closed**?: (specify one of the two: open or closed)
    -  In other terms, does the object's domain have boundaries?
    - *Example 1: A sheet of paper (intrinsic 2D) has a boundary (its contour constitutes a 1D intrinsic domain), and thus it constitutes an open geometry.*
    - *Example 2: An inflated balloon (intrinsic 2D) has no boundaries, it constitutes a closed geometry.*
    - *Example 3: A thin bike tire, which can be considered as a one-dimensional (1D) object, forms a closed loop with no boundaries.*

- For 2D or 3D intrinsic closed object geometries: what is the shape's genus?: (natural number quantifying number of holes)
    - When discussing 2D or 3D intrinsic object geometries, regardless of the object being open or closed, the object's geometry may present several holes. The number of holes can be quantified using the mathematical term "genus" followed up by a natural number.
    - *For example, a torus (doughnut shape) is a closed surface with genus 1. Conversely, a sphere is a closed surface with genus 0.*


- What is the scale of the object?: (Provide an approximate value representative of the length, area, or volume of the object: 1mm, 1cm, 10cm^2, 1m, 10m^3, etc.)
- Is the object predominantly concave or convex? (specify one of the two: concave or convex)
    - Scale and convexity are critical factors influencing object manipulation capabilities, including the number and ease of placement of grippers.
    - *Examples (scale): a grape's scale is approximately 1 cm^3, thus it is hard to manipulate with conventional grippers. On the other hand, a tablecloth's scale is approximately 1 m^2, thus positioning conventional grippers is more convenient in that case.*
    - *Examples (convexity): an octopus is predominantly concave, whereas a cube constitutes a convex geometry. Note how, a purely convex object (like a sphere) might be hard to grasp with conventional grippers.*

</details>

<details>
<summary>A2. Object's deformation properties</summary>

<img src="https://github.com/user-attachments/assets/9a6b7f90-a8ff-4276-9303-ef7a90579849" alt="scheme" width="400">

- What are the **object deformation capabilities**?: (specify if the object can undergo: low/large strain, and/or low/large bending deformation processes. If possible, provide guideline quantifications as described below.)
  - This refers to how the object can be deformed. The main distinctions here are **strain deformation** and **bending deformation**.
  - Strain Deformation:
    - Can a deformation process lead to variations in the length, area, or volume of the object (locally or globally)? If so, the object can undergo strain deformation.
    - Geometrical quantification: It should preferably be quantified with relative strain percentage (%), which refers to the relative change in length, area, or volume with respect to the object's rest configuration: i.e., ((length - at_rest_length)/at_rest_length) * 100.
      - < 0% indicates compression.
      - &gt; 0% indicates elongation or stretching.
    - Guide Values:
      - Low Strain Deformation: Approximately 1-5%.
      - Large Strain Deformation: From 20% upwards.
    - Object's opposition to this deformation: If possible provide approximate values of the Elastic Modulus (e.g., Young's modulus, [N/m^2]), which quantifies the "ease" (tension/deformation ratio) with which the object can undergo strain deformation.
    - *Example of strain deformation: a rubber band stretched horizontally to double its initial length involves a 100% stretching process.*
  - Bending Deformation:
    - Can a deformation process cause significant changes in the curvature of the object's geometry? If so, the object can undergo bending processes.
    - Geometrical quantification: The amount of extrinsic deformation can be quantified by the change in extrinsic curvature, which can be expressed as a percentage (i.e., the relative change in curvature, thus providing a measure of how much the curvature has changed relative to its initial value).
    - Guide Values:
      - Low Bending Deformation: Relative change in curvature < 10%, indicating minor deformation.
      - High Bending Deformation: Relative change in curvature &gt; 50%, indicating significant deformation.
    - Object's opposition to this deformation: The resistance of the object (tension/deformation ratio) to this deformation is measured by its shear, bending, and torsional stiffness. If possible provide approximate values ([N/m]) for:
      - Shear Stiffness: Resistance to shear deformation.
      - Bending Stiffness: Resistance to bending, quantified by the bending modulus or flexural rigidity.
      - Torsional Stiffness: Resistance to twisting deformation.
    - Note: We refer to an isometric deformation when the object is purely bending, with no change in length, area, or volume.
    - *Example of bending (isometric) deformation: a piece of paper that can be bent easily but is impossible to stretch it without tearing it.*

  - *Examples:*
    - *Low Strain Deformation: 5% strain on a tablecloth that is being stretched.*
    - *High Strain Deformation: -30% strain on a sponge that is being pushed (compressed) against a table.*
    - *Low Bending Deformation: 5% relative change in curvature on a metal bar.*
    - *High Bending Deformation: 75% relative change in curvature in a folding sheet of paper.*

  
- What is the object's **response to stress**?: (Specify the predominant beahaviour: elastic, plastic, or elasto-plastic)

    - Elastic behaviour: The object returns to its original shape after the stress is removed. This indicates that the deformation is temporary and the material's structure is not permanently altered.
    - Plastic behaviour: The object undergoes a permanent change in shape after the stress is applied, meaning it does not return to its original form even after the stress is removed. This indicates a permanent alteration in the material's structure.
    - Elasto-Plastic behaviour: The object initially deforms elastically, returning to its original shape up to a certain stress threshold. Beyond this threshold, it deforms plastically, resulting in permanent deformation. 

  - For quantification, if possible provide:
    - Elastic Modulus (Young's Modulus): Measured in megapascals (MPa) or gigapascals (GPa), this metric indicates the stiffness of a material under elastic deformation. A higher elastic modulus means the material is stiffer and deforms less under a given stress.
    - Elastic Limit (Yield Strength): This metric quantifies the maximum stress that a material can withstand while still exhibiting elastic behaviour. Beyond this point, the material will start to deform plastically.

  - *Example (guideline) values:*
    - *Steel:* 
      - *Elastic Modulus: Approximately 200 GPa*
      - *Elastic Limit: Approximately 250 MPa*
    - *Rubber:*
      - *Elastic Modulus: Approximately 0.01 GPa (10 MPa)*
      - *Elastic Limit: Approximately 5 MPa*
    - *Polystyrene (Plastic):*
      - *Elastic Modulus: Approximately 3 GPa*
      - *Elastic Limit: Approximately 70 MPa*

- What is the inherent structure of the object?: (Specify the predominant structure: isotropic, orthotropic, or anisotropic)
    -  That is, specify whether it exhibits uniform properties in all directions (isotropic), different properties in orthogonal directions (orthotropic), or varying properties in all directions (anisotropic).
  - *Examples:*
    - *Isotropic: Uniform properties in all directions, like a homogeneous material.*
    - *Orthotropic: Different properties in different directions, similar to wood or some composite materials.*
    - *Anisotropic: Varies significantly in all directions, such as certain types of carbon fiber composites.*

- Is the object made of a single material, multiple materials, and/or mechanically joint components?: (Specify: single or multiple materials, and single or several mechanically joint parts)
    - If the object is made of several mechanically joint parts, quantify the number of parts.
        - *Examples:
            - *Few parts: 2 main parts, as in a book cover or a hinge.*
            - *Many parts: 100 parts, as in a chain-mail, which behaves very much like cloth.*
    - In the case of multiple materials, specify the composite's name:
        - *Example: carbon fiber.*
</details>
<details>
<summary>A3. Object's perception and interaction suitability</summary>

<img src="https://github.com/user-attachments/assets/91b3af63-9f92-4bc8-a2a3-8a408fb2bb9f" alt="scheme" width="400">


- Is the visual texture of the object rich or low?: (specify either)
  - Evaluate the richness of visual texture regarding object recognition and description, Is it high or low?. Specify how it may affect the perception of the object.
  - *Examples:*
    - *Poor/Low visual texture: Smooth surface, few distinctive visual features (e.g., 5 ORB features can be extracted and tracked under object deformation).*
    - *Rich/High visual texture: surface with highly distinctive and detailed visual features  (e.g., 50 ORB features could be extracted and consistently tracked under object deformation).*
- Can the object's optical properties affect its perception?: (yes/no, specify why)
  - Discuss the object's reflectivity and other optical characteristics affecting sensor suitability.
  - Example metrics:   reflectivity (percentage), translucency, color index, refractive index, etc.
  - *Example Values:*
    - *Low Reflectivity: 10%, matte surface, suitable for RGB-D cameras with infra-red projected patterns.*
    - *High Reflectivity: 80%, glossy surface, not suitable for general-use visual or haptic sensors.*
- Do the object's surface properties affect the use of mechanical or tactile sensors?: (yes/no, specify why)
  - Consider the influence of tactility and roughness on grasping and mechanical sensor usage. Surface texture can affect friction, grip, and the sensitivity of touch sensors.
  - Metrics:
     - Roughness (Ra in micrometers, µm): Low (0.1 µm, very smooth) to High (10 µm, very rough).
     - Friction Coefficient (dimensionless, computed with respect to the gripper material): Low (0.2, slippery) to High (0.8, very *grippy*).
- What's the object's dependence on specific or specialised sensors and actuators?: (low, medium or high; specify suitable types of sensors and actuators)
  - Discuss the dependence on specific or specialised sensors or actuators. Different objects may require various levels of sensor or actuator sophistication to be accurately perceived or controlled.
    - Low Dependency: The object can be perceived with generic sensors (*e.g., standard RGB-D cameras, basic tactile sensors*).
    - Medium Dependency: The object requires moderately specialised sensors (*e.g., infrared sensors, ultrasonic sensors*).
    - High Dependency: The object requires highly specialised sensors (*e.g., medical imaging sensors like MRI or CT scanners, specialised tomographs*).
</details>

## **B. Available object information classification**

<details>
<summary>B1. Information Type</summary>
    
From the control system's point of view, what is the available object information?

- Does the control system make use of **mechanical information**?: (yes/no, if yes, which type: density, elasticity constants, stress, etc.)
    - The control system might receive and use data about the mechanical properties or behaviour of the object. Although some of the mechanical properties may have been specified in section A, it is now important to specify which of them are actually being exploited by the control system.

- Does the control system make use of **geometric information**?: (yes/no, if yes, which type: intrinsic and extrinsic dimensions, scale, etc.)
  - The control system may receive geometric information. This requires specifying both intrinsic and extrinsic dimensions of such information, as discussed in the previous criterion A1. Note that the received geometric information does not necessarily correspond directly to the actual object's geometry:
    - *For example: A contour extraction of a balloon observed in a 2D image provides closed 1D intrinsic, 2D extrinsic information (apparent contour), whereas the actual object (the balloon) has a closed 2D intrinsic, 3D extrinsic geometry.*
   
Possible combinations of intrinsic and extrinsic geometries of the available geometric information: 

<img src="https://github.com/user-attachments/assets/ea99341f-713c-4a17-88a7-709337054ae8" alt="scheme" width="400">

</details>
<details>
<summary>B2. Information Resolution</summary>

<img src="https://github.com/user-attachments/assets/d178589a-6974-408b-ac43-d9f458eb1047" alt="scheme" width="400">

- What is the **spatial resolution or density** of the input information?: (specify: low, medium or high. If possible, quantify)
  - **Low-density**: Sparse/Discrete geometric information, providing very basic geometric information like very sparse feature location or a single segment's curvature approximation.
    - *Example: the position of 5 visual features extracted from fiducial markers attached to the object.*

  - **Medium-density**: offering more detailed geometric and structured representation of the object's geometry.
    - *Example: A 3D mesh with 50 vertices.*

  - **High-density**: Dense/Continuous data points or measurements, providing precise geometric details of the object.
    - *Example: A 3D point cloud with 500 points capturing fine surface details.*
  - *Note: Specifying the number of extracted discrete features (for sparse information) or the pixel density (e.g., pixels per meter [ppm]) can provide a valuable measure of the information's geometric resolution.*

- What is the **temporal resolution** of the input information?: (specify: low, medium or high. If possible, quantify in [Hz])
  - **Low Temporal Resolution**: sparse data captured over longer intervals.
    - *Example: Sensor data sampled at 1 Hz.*

  - **Medium Temporal Resolution**: data captured at moderate intervals.
    - *Example: Sensor data sampled at 15 Hz, which already complies with some industry standards.*

  - **High Temporal Resolution**: continuous and high-frequency data capture.
    - *Example: Sensor data sampled at 120 Hz, providing real-time updates (note: *real-time* as in a computer vision context).*
</details>
<details>
<summary>B3. Information Acquisition</summary>

<img src="https://github.com/user-attachments/assets/a3394476-a0f9-4349-a35c-e23c4923cc46" alt="scheme" width="400">

- What is the information source?: (Specify whether and how the employed information is assumed, estimated and/or measured)
  - **Assumed**: Information based on assumptions or theoretical models.
    - *Example: assuming the elastic modulus of an object based on its material (from tables).*
  - **Estimated**: Data derived from indirect measurements or visual parameters.
    - *Example: Estimating the weight distribution of an object based on its geometry and materials.*
  - **Measured**: Directly obtained from sensors or empirical measurements.
    - *Example: Using strain gauges to measure deformation iduring a bending operation.*
  - *Note: How much can you trust your information? The certainty of information source is crucial as it directly impacts the reliability and accuracy of the data used for shape control. Assumed or estimated information may introduce uncertainties, whereas measured data provides more accurate inputs for precise control algorithms.*

- When and how often can you obtain such information?: (Specify when each piece of information is obtained: a priori, offline or online)
  - **A Priori**: Information obtained before any interaction with the object, often from design specifications or initial setup.
    - *Example: Knowing the dimensions and material properties of a metal sheet from a generic piece CAD model before starting a deformation process.*
  - **Offline**: Information acquired before the active control phase but involving direct observation or preparation steps.
    - *Example: Conducting a laser scan of a prototype to capture detailed surface contours before the control process.*
  - **Online**: Real-time information gathered during the shape control process, allowing for immediate adjustments based on current conditions.
    - *Example: Using computer vision to track the position and orientation of an object's surface in real-time.*
  - *Note: The acquisition phase is critical for ensuring timely and relevant data availability during the control process. A priori and offline information helps in planning and preparation, while online information enables adaptive and responsive control strategies.*
</details>

## **C. Shape error definition**
<details>
<summary>C1. Shape control scope</summary>

<img src="https://github.com/user-attachments/assets/7bbf831b-9333-4031-8e5e-b1fe8fc9440b" alt="scheme" width="700">

What does the control system *care* about in its shape error computation?: (specify one of the 3 options below)
- Shape, Scale, and Transport:
  - Control involving shape, size, and rigid body transformations (translation and rotation).
- Shape and Scale:
  - Control involving shape and size, but not rigid body transformations.
- Shape Only:
  - Control involving only the shape, without considering size or rigid body transformations.

</details>
<details>
<summary>C2. Error dimensionality</summary>

<img src="https://github.com/user-attachments/assets/6dc8b769-21b1-459d-91a3-ac750fcf0072" alt="scheme" width="700">

- What dimensionality does the shape error consider?: (Specify intrinsic and extrinsic dimensionalities: 1D, 2D, or 3D)
  - This refers to how the dimensions of the object’s information correspond to the dimensions used for calculating the shape error.
  - *For example: you might capture detailed 3D information of a pizza using an RGB-D camera, yet only utilize the 1D intrinsic contour (the flat circular shape of the pizza) to compute the control error signal. If the pizza were to deform into a cone-like shape that maintains its circular contour, the previously described error signal would fail to detect the shape change, despite the available information.*
</details>
<details>
<summary>C3. Reference's Time Dependence</summary>
<img src="https://github.com/user-attachments/assets/6dc8b769-21b1-459d-91a3-ac750fcf0072" alt="scheme" width="700">

Does the reference shape information vary through time? How does it vary?: (specify one of the three options below)

- **Fixed Target Shape (Constant Reference)**:
  - The control reference remains constant, this sometimes facilitates stability analysis as the derivative of the shape reference is zero.

- **Fixed Target Shape with Variable Reference**:
  - While the target shape remains fixed, new intermediate control references defined between the target shape and the current shape can be computed. This approach includes methods like interpolating intermediate states or optimizing geometric alignment (Procrustes analysis), facilitating shape control convergence.

- **Variable Target Shape (Shape Trajectory Control)**:
  - The reference shape itself varies over time, presenting a challenge in maintaining proper shape control over the target shape evolution. This scenario involves shaping trajectories where the desired shape changes dynamically as a function of time.
</details>
<details>
<summary>C4. Error Definition Types</summary>

<img src="https://github.com/user-attachments/assets/ca814835-c717-4676-b127-0ac440ab3791" alt="scheme" width="700">

What method does the shape control system use in order to compare the current and target shape representations?: (specify one of the categories below)

- **Discrete Feature-Based Errors**:
  - Compares sparse visual or geometric features between the current and target shapes, such as specific keypoints or distinctive visual elements.
  - *Example*: Detecting, matching, and comparing the position of ORB features between two different object configurations. 
  - *Note*: the example's method relies on the presence and consistent placement of visual features in the target shape. If the target shape lacks these features or they are positioned differently (e.g., comparing two newspapers from different dates), the visual error measurement may be misleading.


- **Point Alignment Errors**:
  - Focuses on aligning specific points on the object to points on the target shape, without directly computing point correspondences.
  - *Example*: Aligning pixels from an object with a homogeneous texture (where no geometric or visual features are extracted), aiming to maximize the overlap between the current and target pixel positions.

- **Shape Point Matching**:
  - Matches sets of points sampled from the shape's geometric domains (e.g., homogeneous point sampling from contours, surfaces, etc.). This can involve:
    - **Homogeneous Matching**: Points are uniformly distributed across the current and target shapes. This method is effective for isometric deformations where point correspondence remains consistent.
      - *Example*: Sampling 10 evenly spaced points along the medial axis of a deformable linear object (DLO) in both its current and target configurations, then matching these points based on their order in the sequence.
      
    - **Elastic Matching**: Point matches are distributed variably to represent material points during strain deformations, suitable for accommodating non-uniform deformations such as stretching or compression.
      - *Example*: Sampling points uniformly along the contours of a cloth that is going to be highly stretched. Then, performing a matching process that accounts for the stretching, resulting in a non-uniform distribution of matched points on the target contour: fewer matched point density where the cloth has been stretched and more matched points density where the object has been compressed.


- **Parametric Errors**:
  - Based on comparing mathematical parameters that define **curves** (e.g., Bézier curves) or **series** (e.g., Fourier series), quantifying differences based on mathematical representations.
  - *Example*: comparing the value of the complex Fourier coefficients between two closed contours.

- **Continuous Map Errors**:
  - Compares continuous representations of shape domains. These are the more complete and detailed ways of comparing two shapes. Continuous maps include:
    - **Homogeneous Continuous Maps**: Points are uniformly distributed in the mapped space, such as in functional maps for surfaces.
    - **Elastic Continuous Maps**: Points are variably distributed, adapting to deformations like stretching or compressing, such as in FMM continuous contour mapping.
</details>

## **D. Control strategy characterisation**
<details>
<summary>D1. System Modeling</summary>

<img src="https://github.com/user-attachments/assets/c69e6b57-6f6a-48ff-9207-fa5444e61963" alt="scheme" width="400">

- Is your model physically meaningful or abstract?: (specify if your model is constitutive/physically accurate, or abstract/phenomenological, you may employ our proposed quantification scale, from 1 to 8, presented below)

    - Physically Meaningful (**1-3**: Constitutive/Physically accurate)
        - **1**: Fully constitutive model with detailed physical accuracy (*e.g., Finite Element Method (FEM), detailed thermodynamic models*).
        - **2**: Mostly constitutive with some abstract elements (*e.g., simplified FEM with some empirical adjustments*).
        - **3**: Balanced between constitutive and abstract elements (*e.g., reduced-order models with significant physical basis*).

    - Mixed (**4-5**: Intermediate/Mixed models)
        - **4**: Predominantly abstract but includes key physical parameters (*e.g., simplified physical models with empirical data*).
        - **5**: Equally abstract and physical (*e.g., mixed methods combining physical laws and statistical approaches*).

    - Abstract (**6-8**: Abstract/Phenomenological models)
        - **6**: Mostly abstract with minimal physical parameters (*e.g., basic empirical models, data-driven with minimal physical basis*).
        - **7**: Highly abstract with some physical parameters used for calibration (*e.g., control models with physical constraints*).
        - **8**: Fully abstract control-oriented model with few or no physical parameters (*e.g., neural networks, pure statistical models*).


- Can the model apply to various scenarios or is it specific to certain objects or materials? (Clearly state the application range of the model. Is it a one-case model, or can it be used in multiple scenarios? If it can be used in several scenarios, what changes or modifications are needed?)

- What is the model's complexity? (specify, if possible, algorithmic complexity with Big O notation, and time-cost in [Hz] for a particular implementation or programming language)

- How well does the model predict the real object behaviour? (Specify the model's accuracy as the mean squared error between the model's predicted and observed deformable object behaviour in the experiments)

</details>

<details>
<summary>D2. Manageable Deformation Scale</summary>

<img src="https://github.com/user-attachments/assets/fd4b67b3-d67d-4eab-9dfd-5ac9747298b6" alt="scheme" width="400">

The ability of an object to undergo large deformations does not necessarily mean that a control system can handle such deformations effectively. It is important to distinguish between the deformation capabilities of the object and the manageable deformations of the control strategy.

- What types of deformations can the shape control system handle?: (specify if the control system can handle strain and/or bending deformation, as detailed in criterion A.2)
  - **Strain Deformations:** Handling changes in length or stretching.
  - **Bending Deformations:** Handling changes in shape such as folding or curving.
  - *Note: this should be clearly analysed as, for example, some shape control systems may excel at isometric deformations but fail to converge when strain deformations occur.*

- Can the control system handle large deformations? What are the limitations? (specify, for each type of deformation (strain/bending), whether the control system can handle them locally or globally)
  - **Local Deformations:** Ability of the strategy to handle small-scale changes (< 5 %).
  - **Global Deformations:** Ability of the strategy to handle both small and large-scale bending or stretching (&gt; 50 % in bending and  &gt; 20 % in strain deformation).
</details>

<details>
<summary>D3. System Stability</summary>

<img src="https://github.com/user-attachments/assets/d3748025-0802-4371-a27e-8b304d42c32e" alt="scheme" width="400">

- Does the shape control approach provide any type of formal stability analysis? (yes/no, if yes: what type?: local stability, local asymptotic stability, global asymptotic stability, etc.)

- Does the approach provide controllability/reachability analysis? (yes/no, if yes, specify the domain: is it full-state, local, in a set or sub-set?)

- Specify the impact in the system's stabiltiy, controllability, and/or reachability regarding the number and placement of actuators: (high, moderate, or low)
    - **High impact**: Stabiltiy/controllability/reachability can be achieved with a high number of actuators (e.g., >10 grippers) that are optimally located.
    - **Moderate impact**: Stabiltiy/controllability/reachability can be achieved with sufficient actuators (e.g., 5 to 10 grippers) placed in strategic locations.
    - **Low impact**: Stabiltiy/controllability/reachability is can be achieved even when few actuators are employed (e.g., 1 to 4 grippers) or there is an inconvenient placement of such actuators.

- Is reachability considered in the definition of target shapes?: (yes/no, if yes specify to which degree)
    - **Highly considered**: Explicit and precise definitions of target shapes are obtained analysing reachable regions in the state space.
    - **Moderately considered**: There exists some discussion on how the definition of target shapes considers some notion of reachability.
    - **Non-specified**: no explicit specifications on how target shapes are defined with respect to a theoretical reachability analysis.
    - *Note: In the literature, researchers often use robots to obtain several shapes with a specific gripper placement. These shapes are then used as target shapes in experiments, ensuring they are known to be reachable.*

</details>

<details>
<summary>D4. Considerations and constraints</summary>

<img src="https://github.com/user-attachments/assets/312845d9-60a9-42a4-9a8e-b22ec00af110" alt="scheme" width="400">

- How easily can the method be reproduced across different scenarios? Evaluate, from 1 (best) to 5 (worst), the following aspects:

    - **Implementation complexity**:
      - **1**: Very easy to implement with no special requirements (*e.g., PID controller*).
      - **2**: Simple implementation with minimal expertise needed  (*e.g., Jacobian-based controller*).
      - **3**: Requires some expertise or specific setup (*e.g., Model Predictive Control*).
      - **4**: Complex implementation needing advanced knowledge (*e.g., Reinforcement Learning based controller*).
      - **5**: Highly complex, requiring deep expertise and advanced techniques (*e.g., Koopman-based non-linear control*).

    - **Transferability**:
      - **1**: Easily transferable across different scenarios with no modifications.
      - **2**: Mostly transferable with minor adjustments needed.
      - **3**: Requires some adjustments or parameter tuning.
      - **4**: Hard to transfer, needing significant modifications.
      - **5**: Very difficult to transfer, requiring extensive changes or completely different approaches.

    - **Resource requirements**:
      - **1**: Minimal resources required (*e.g., <10 MB of data, basic laptop*).
      - **2**: Low to moderate resources required (*e.g., 10-100 MB of data, standard desktop PC*).
      - **3**: Moderate resources needed (*e.g., 100 MB - 1 GB of data, moderate computational power*).
      - **4**: High resources required (*e.g., >1 GB of data, high computational power*).
      - **5**: Extremely high resources required (*e.g., specialized hardware, large-scale computing infrastructure*).

    - **Training and setup time**:
      - **1**: Very short setup time (*e.g., <1 hour*).
      - **2**: Short setup time (*e.g., 1-4 hours*).
      - **3**: Moderate setup time (*e.g., 4-12 hours*).
      - **4**: Long setup time (*e.g., 12-24 hours*).
      - **5**: Very long setup time (*e.g., >24 hours, including extensive training periods*).

  - *Examples:*
      - *Jacobian-based online updated strategy: implementation complexity = 2, transferability = 1, resource requirements = 2, training and setup time =1.*
      - *Deep reinforcement learning-based controller: implementation complexity = 4, transferability = 4, resource requirements = 4, training and setup time =5.*

- How do performance metrics such as control accuracy and convergence time change with increasing object size or number of actuators?: (from 1 (great) to 5 (poor), specify the scalability of the shape control system)

    - **1**: Maintains high control accuracy and fast convergence across a wide range of object sizes or actuator numbers.
    - **2**: Generally consistent performance with minor variations in control accuracy and convergence time.
    - **3**: Moderate consistency in performance, with noticeable changes in control accuracy or convergence time.
    - **4**: Performance varies significantly with object size or number of actuators, impacting control accuracy and convergence time.
    - **5**: Poor scalability, with drastic changes in performance metrics that make the strategy ineffective with variations in object size or actuator numbers.


- Is the control system capable of maintaining closed-loop frequencies that meet real application requirements? (specify the controller's processing time cost [ms] or frequency [Hz])

- Does the shape control method incorporate collision avoidance, object strain limits, and other feasibility considerations?: (Clearly specify the practical constraints considered by the system)
  
</details>

<details>
<summary>D5. Control Actions</summary>

<img src="https://github.com/user-attachments/assets/bdc53bbe-af02-4f4c-9743-1448bae90048" alt="scheme" width="400">

- **Action Type:** Describe the types of control outputs, focusing on whether they involve end-effector position control, velocity control or other types.
  - *For example, while position-based control is relatively common, it may not be suitable for tasks involving highly inertial deformations, such as manipulating a cloth hanging from a robotic gripper. Alternatively, force-based actions are suitable for considering stress limits in delicate objects.*

- **Dimensions and Degrees of Freedom (DoF):** Specify the dimensions (1D, 2D or 3D) and the number of degrees of freedom (DoF, i.e. independent motions) involved in the control actions.
    - *Note: In the existing literature, shape control usually takes place in 2D planes (2D translation + 1D rotation = 3 DoF). The extension to 6 DoF (3 translations + 3 rotations) introduces complexities due to the likelihood of multiple solutions and singularities that need to be carefully considered.*

- **Object Contact Type:** Clearly specify the type of actuator-object contact: how does it actually occur in reality, and how is it taken into account in the control system (if at all)? 
  - *Examples: In the literature, a common assumption is to consider the gripper-object contact as a single point, although alternative approaches consider larger contact areas to model how rotational actions are transmitted to the object. Some methods incorporate contact points with the environment (such as tables or obstacles) as collaborative actuation elements within their control systems. It is essential to explicitly describe how contact information is processed and used by the control system.*
</details>


---

*NOTE: When seeking precise characterisation of a method, we recommend using formal mathematical notation and International System of Units (SI) quantifications. In this form we provide recommendations and example values for such metrics. For instance, strain in percentage (\% change of m), bending in curvature change (\% change of m^-1), spatial resolution in pixels per meter [ppm], computational time cost in milliseconds [ms], or complexity using big O notation. However, not all criteria will always need quantification; qualitative descriptions are also valuable, e.g., the use of Local Binary Patterns to quantify the visual texture of the object may be excessive if one simply indicates sufficient visual texture for robust ORB feature extraction.*

---


