# CAuthNet: A Unified Embeddings for Continuous Authentication in Smartphones


Despite significant recent advances in continuous authentication, implementing it efficiently at scale remains challenging. In this paper, we introduce CAuthNet, a system that directly learns a mapping from smartphone sensor readings related to touch events to a compact Euclidean space, where distances correspond to a measure of touch similarity on the phones. We train one-shot Seismic network architecture tailored for continuous authentication. This approach streamlines continuous authentication by training a single model using training data belonging to a few users. However, the trained model can then be deployed on new users' smartphones without further training, ensuring both privacy and portability. As the smartphone sensors' data is often noisy, we introduced a novel feature extraction technique for each touch events and shown that aggregating few consecutive touches significantly enhances the accuracy of the trained model.  The proposed algorithm is validated using the H-MOG dataset, one of the largest publically available smartphone datasets, which contains an accelerometer, gyroscope, magnetometer and touch sensor data collected from $100$ users. We used half of the users' data to train a model and then tested the performance of the trained model using the remaining half of the users.  The proposed algorithm achieves up to $97\%$ true positive and true negative rates ($3\%$ Equal Error Rate) on unseen users. This is the first known portable continuous authentication technique with a simple and scalable architecture, making it suitable for real-world deployments.

# How to use the code

1. Download the H-MOG dataset from (https://hmog-dataset.github.io/hmog/) and unzip
2. Use CAuthNetFeatureExtraction.ipynb to extract features from the H-MOG dataset
3. Then use FacenetbasedOneshotLearning.ipynb to train and test the models
4. Then use AccuracyDifferentTestSize.ipynb to get EER for different combinations of test data
5. Then use ClassificationUsingEmbeddings.ipynb to perform various experiments using the extracted embeddings
6. tSNE.ipynb to generate tSNE plots
7. Use AttackByMixingUsers.ipynb to test the ribsutness of the CAuthNet
