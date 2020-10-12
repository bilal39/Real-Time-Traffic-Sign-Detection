# Real-Time-Traffic-Sign-Detection
I have trained SSDlite-MobilenetV2 Model on GTSDB. I was able to achieve 75% mAP on testing dataset of GTSDB. It took me 22768 steps to train the model. Afterwards my validation accuracy started to decrease.
Here are the steps i did in order to train a model.
First of all i downloaded the GTSDB dataset from this link https://sid.erda.dk/public/archives/ff17dc924eba88d5d01a807357d6614c/published-archive.html
The dataset is in PPM format so i converted it them to png format using the file ppm_to_png.py given in above link.
Then i created tensorflow record(tfrecord) file. You can take help from the link https://github.com/EdjeElectronics/TensorFlow-Object-Detection-API-Tutorial-Train-Multiple-Objects-Windows-10
After creating tfrecord file, i migrated to Google Colab since i didn't had access to heavy GPU and CPU.
I used premium account in order to train the model.It took me 6-8 hours straight to train the model.
I trained the model twice.First time with training dataset(containing 600 images) and validation dataset(300 images which is originally for testing ).Once i got the approximate number of steps around which my model trained for the first time. On second run , i trained the model straight to that number of steps that is 22768.(The reason i didn't train the model in single run only because i had limited 900 pictures only in which 600 for training and 300 for testing. I didn't want to further split training dataset into (training and validation dataset).
i have attached a picture in results folder of mAP calculated during first training run with name mAP1 and for second training i, mAP picture is named as mAP2.
I have also attaced PR(precision recall) curves of it in the results folder.Testing samples are also attached in result folder.
Then i implemented this model on raspberry pi 4. I got FPS from (1.6 - 2.1) FPS.
I also added audio assist system to it. The model say out loud the name of the class of traffic sign it detected.
