# Homologous_deepfake_dataset
A self built small-scale, high-quality, and diverse deepfake dataset.

**Production Unit**: Xidian University, Modern Image Processing Lab

**Dataset project**：https://github.com/mirro-yyf/Homologous_deepfake_dataset
## 1. The contribution of this dataset
- Provided for the first time a facial dataset for Chinese people;
- Provided attribute editing facial video data for the first time.
## 2. Introduction
The Homologous_deepfake dataset covers four types of deepfake images/videos: full-face generation, attribute editing, expression driven, and face swap. Among them, full-face generation provides 6802 fake images, and attribute editing provides 200 fake videos, 100 fake videos for expression driven, and 100 fake videos for face swap. All faces are Chinese.
### 3. Overview of Dataset Catalog:
![dataset_diretory](https://github.com/mirro-yyf/Homologous_facedataset/assets/89956031/7908e479-aa1f-402e-81bf-c12d9db1834a)
### 3.1 Deepfake images
#### Full-face generation images(GAN_images)
- Concept: Using a large number of real face images to train a latent space that conforms to the distribution of faces, randomly selecting a random vector from this latent space, and finally generating a face image through deformation upsampling operation.
- Quantity: 6802 images
- Method: Face-Attribute-Editing-StyleGAN3——text2stylegan——[Face-Attribute-Editing-StyleGAN3](https://github.com/MingtaoGuo/Face-Attribute-Editing-StyleGAN3)
### 3.2 Deepfake videos
#### 3.2.1 Expression driven videos(avatarify_video)
- Concept: Given a target face avatar to be driven, and then a segment of the source face, providing driving actions for the target face to be driven.
- Quantity: 100 videos
- Method: ICCV2023-MCNET——[ICCV2023-MCNET](https://github.com/harlanhong/ICCV2023-MCNET)
- Naming format: target-face_ Source-face
#### 3.2.2 Attribute editing videos(edit_video)
- Concept: Given a facial image, edit the hair color, beard, baldness, age, gender, and makeup of the given face. In our dataset, we edited the age and hair color attributes of the source facial video separately, with an editing factor of 2.0.
- Quantity: 200 videos, with 100 videos for age editors and 100 videos for hair color editors each
- Method: StyleGANEX——[StyleGANEX](https://github.com/williamyang1991/StyleGANEX?tab=readme-ov-file)
#### 3.2.3 Face swap videos(swap_video)
- Concept: Face swap requires two different faces as raw materials, namely the source face and the target face. There has been no unified academic consensus on the definition of the source face and the target face. In our dataset, we define the source face as the face that provides facial identity, and the target face as the face that provides expression and background, that is to say, We replaced the identity of the source face with the target face, and the exchanged face has a different identity compared to the target face, with all other information remaining the same.
- Quantity: 100 videos
- Method: SwapFace——[Swapface](https://swapface.org/#/home)
- Naming format: target-face_ Source-face
### 3.3 Real videos
#### 3.3.1 Source videos(raw_video)
We collected a total of 100 interview videos of different characters, including 50 males and 50 females, from the personal spaces of two interview type UP hosts on the Bilibili platform -[二狗App-单身青年故事](https://space.bilibili.com/524930260?spm_id_from=333.337.0.0), and [凉子访谈录](https://space.bilibili.com/496688267?spm_id_from=333.337.0.0). The length of these videos is about 10 minutes. Due to the long duration of the source video, we only took a 15 second clip from each video as our source facial video, named sequentially from 1 to 100, with a resolution of 1280 × 720, with a frame rate of 30 frames per second.
#### 3.3.2 Facial extraction videos(face_video)
Due to the fact that face extraction is a necessary step in all deep forgery processes, we also provide a source face video that only contains the face part. We use the MTCNN face detection algorithm to crop the face from the source face video with a time length of 15 seconds to form a new source face video, and set the resolution of all new source face videos to 350 × 350.
## 4. Dataset display
![数据集图片展示](https://github.com/mirro-yyf/Homologous_facedataset/assets/89956031/31039df1-29d8-4fe2-801a-38d23a20ab6d)
## 5. Download_link
Baidu Netdisk: 

Google Drive: https://drive.google.com/file/d/1y9KEtJqxVsE8AxMl-LyLeJe5AtSBbBtA/view?usp=drive_link
## 6. Technical Support
e-mail: 13759792638@163.com
QQ: 84489770
