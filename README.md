# Deep-Shape-from-Template
Shape-from-Template (SfT) solves 3D vision from a single image and a deformable 3D object model, called a template. Concretely, SfT computes registration (the correspondence between the template and the image) and reconstruction (the depth in camera frame). It constrains the object deformation to quasi-isometry. Real-time and automatic SfT represents an open problem for complex objects and imaging conditions. We present four contributions to address core unmet challenges to realise SfT with a Deep Neural Network (DNN). First, we propose a novel DNN called DeepSfT, which encodes the template in its weights and hence copes with highly complex templates. Second, we propose a semi-supervised training procedure to exploit real data. This is a practical solution to overcome the render gap that occurs when training only with simulated data. Third, we propose a geometry adaptation module to deal with different cameras at training and inference. Fourth, we combine statistical learning with physics-based reasoning. DeepSfT runs automatically and in real-time and we show with numerous experiments and an ablation study that it consistently achieves a lower 3D error than previous work. It outperforms in generalisation and achieves an unprecedented performance with wide-baseline, occlusions, illumination changes, weak texture and blur.
![Alt text](diagrama_tof.png?raw=true "System Blocks Diagram")
# Working Conditions
This code runs on Tensorflow 2.0
# Train
To train the system it is necessary to download the GOTPD database from the following URL:

https://www.kaggle.com/lehomme/overhead-depth-images-people-detection-gotpd1

The Data have to be stored in GOTPD_DATABASE folder and divided in gaussianas, imagenes and validacion folders, where we have the training set output images, the training set input images and the validation and test subsets, dividid in another gaussianas and imagenes subfolders.

Once you adapted the data to the folders system, you'll only have to run Train.py and the system will train and save the trained model in DPDnet.h5 (it only save the weights).

# Test
The repository stores a DPDnet trained model, it is only a demo model to provide a demonstration, so it won't report the optimal results of the system.
To test the only step needed its to run Test.py, and the system will load the demo sequence to show the results obtained with the proposed system.

# Sample Data
In the GOTPD_DATABASE/validacion/imagenes and GOTPD_DATABASE/validacion/gaussianas you will find an example test sequence that will load Test.py to show how the system works and compare prediction and groundtruth.

# Citation

If you make use of this code and/or its related documentation, you are kindly requested to cite the paper:

David Fuentes-Jimenez, Roberto Martin-Lopez, Cristina Losada-Gutierrez, David Casillas-Perez, Javier Macias-Guarasa, Carlos A. Luna, Daniel Pizarro. DPDnet: A Robust People Detector using Deep Learning with an Overhead Depth Camera, Expert Systems with Applications, 2019, 113168, ISSN 0957-4174
    https://doi.org/10.1016/j.eswa.2019.113168.
    (http://www.sciencedirect.com/science/article/pii/S0957417419308851)
