# Homologous_facedataset
A self built small-scale, high-quality, and diverse deepfake dataset.
## 1. The original intention of dataset creation
Due to the poor performance of the forgery methods used in existing large-scale facial datasets in the later fusion stage, the quality of the generated forgery facial videos/images is low, and even there are obvious visual artifacts, which reduces the difficulty of deep forgery detection and makes it impossible to test the true performance of deep forgery detectors. In order to further promote the development of deep forgery detection technology, we have constructed a new dataset of forged faces called Homologous_facedataset.
## 2. The contribution of this dataset
1. For the first time, video format attribute editing facial data was provided;
2. All forged faces, whether in images or videos, have no visual artifacts, further increasing the challenge of deep forgery detection technology.
## 3. Introduction
Our Deep Forged Face Dataset Homologous_ Facedataset includes all four types of fake faces: full face generation, attribute editing, expression driven, and face exchange. Among them, only the fake faces generated by full face generation are presented in image form, while the other three types of fake faces are presented in video form. Next, we will introduce the collection process of the source facial video, as well as the scale, forgery methods, and naming rules of the four types of forged faces.
### 3.1 Overview of Dataset Catalog:
--Homologous_facedataset
  --GAN_images
  --video
  	--fake
  	  --avatarify_video
  	  --edit_video
  	    --age_edit_2.0
  	    --hair_edit_2.0
  	  --swap_video
  	--real
  	  --face_video
  	  --raw_video
### 3.2 Real video
#### 3.2.1 raw_video
We collected a total of 100 interview videos of different characters, including 50 males and 50 females, from the personal spaces of two interview type UP hosts on the Bilibili platform -[二狗App-单身青年故事](https://space.bilibili.com/524930260?spm_id_from=333.337.0.0), and [凉子访谈录](https://space.bilibili.com/496688267?spm_id_from=333.337.0.0). The length of these videos is about 10 minutes. Due to the long duration of the source video, we only took a 15 second clip from each video as our source facial video, named sequentially from 1 to 100, with a resolution of 1280 × 720, with a frame rate of 30 frames per second.
#### 3.2.2 face_video
Due to the fact that face extraction is a necessary step in all deep forgery processes, we also provide a source face video that only contains the face part. We use the MTCNN face detection algorithm to crop the face from the source face video with a time length of 15 seconds to form a new source face video, and set the resolution of all new source face videos to 350 × 350.
### 3.3 Fake video
#### 3.3.1 swap_video
The concept of face exchange: Face exchange requires two different faces as raw materials, namely the source face and the target face. There has been no unified academic consensus on the definition of the source face and the target face. In our dataset, we define the source face as the face that provides facial identity, and the target face as the face that provides expression and background, that is to say, We replaced the identity of the source face with the target face, and the exchanged face has a different identity compared to the target face, with all other information remaining the same.
Quantity: 100 videos
Method: SwapFace[Swapface](https://swapface.org/#/home)
Naming format: target-face_ Source-face
#### 3.3.2 avatarify_video
Concept: Given a target face avatar to be driven, and then a segment of the source face, providing driving actions for the target face to be driven.
Quantity: 100 videos
Method: ICCV2023-MCNET[ICCV2023-MCNET](https://github.com/harlanhong/ICCV2023-MCNET)
Naming format: target-face_ Source-face
#### 3.3.3 edit_video
Concept: Given a facial image, edit the hair color, beard, baldness, age, gender, and makeup of the given face. In our dataset, we edited the age and hair color attributes of the source facial video separately, with an editing factor of 2.0.
Quantity: 200 videos, with 100 videos for age editors and 100 videos for hair color editors each
Method: StyleGANEX[StyleGANEX](https://github.com/williamyang1991/StyleGANEX?tab=readme-ov-file)
#### 3.3.4 GAN_images
Concept: Using a large number of real face images to train a latent space that conforms to the distribution of faces, randomly selecting a random vector from this latent space, and finally generating a face image through deformation upsampling operation.
Quantity: 6802 images
Method: Face-Attribute-Editing-StyleGAN3——text2stylegan【[Face-Attribute-Editing-StyleGAN3](https://github.com/MingtaoGuo/Face-Attribute-Editing-StyleGAN3)】
## 4. Download
