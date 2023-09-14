---
# permalink: /publications/
# title: "田建东的论文"
# excerpt: "publication"
# author_profile: true
# redirect_from: 
#   - /pub/
#   - /pub.html
layout: archive
title: "理论成果"
permalink: /pub/
author_profile: true
---

1.大气辐射传输、场景反射、相机成像建模
======
(1)大气辐射光谱计算方法
------
室外环境下，太阳发出的光线经过地球的大气层会受到大气吸收、反射、和散射等影响，导致到达地面的光照会随着时间和大气因素而变化，进而导致室外场景图像的复杂性和多样性。大气物理领域的研究表明**至少20多个参数**会影响光照和天气的变化，但这些参数对于机器人的应用来说**难以获得**。为解决该问题，团队提出了适于机器人视觉成像计算的大气辐射光谱计算方法。我们的方法只需两个参数：天顶角（可根据机器人GPS坐标及时间信息计算）及气溶胶指数（我们在论文中给出了利用图像中阴影强度来计算该参数的方法，在某些具体应用中也可根据天气预报或空气污染指数获得），在参数减少了90%的情况下仍能保持计算精度，详见表1与图1。

<div align = center><img src='/images/pub_sheet1.png'></div>
表1. 我们方法与大气物理中两种经典计算方法（Bird和SMART32）的计算复杂度对比。我们方法只需2个参数和简单计算，经典大气物理方法需要20多个参数和复杂计算，且这20多个参数对于机器人的应用来说难以获得。

<div align = center><img src='/images/pub_img1.png' width = "80%"></div>\
图1. 地表大气辐照度计算结果，左侧为太阳直射光，右侧为天空散射光。第一排为我们方法与大气物理两种经典计算方法（Bird和SMART32）的对比结果。结果表明我们方法（只需2个参数，经过简单计算）可以非常逼近大气物理经典方法（需要20多个参数，经过复杂计算）的计算结果。第二排为我们计算方法和光谱仪实测数据的对比（红色为真实值）。结果表明我们的计算结果非常接近实测结果，可确保用于机器人视觉。

(2)场景反射光谱重建
------
我们的贡献在于提出了相机/人眼响应光谱加权控制反射光谱重建精度，使得相机/人眼响应高的谱段重建精度更高。图2是4个色块的反射率光谱重建结果，其中红色表示真实光谱，绿色表示我们计算得到的光谱, 蓝色表示经典PCA方法得到结果，黑色代表颜色匹配函数三通道的和。横坐标代表波长，纵坐标代表反射率。从结果上看，我们方法在颜色匹配函数（对应于相机的色彩响应曲线）的峰值处的精度远高于PCA方法的精度，这样非常利于提高利用此反射曲线进行成像计算的精度，统计结果表明我们方法得到反射光谱的成像精度比主流方法提高了50%。


<div align = center><img src='/images/pub_img2.png'></div>\
图2. 2个代表性色块的反射光谱重建结果

(3)相机成像建模与仿真
------
研究进入相机的光线经过光电转换后得到的 Raw 数据（图3）以及后续处理的过程（图4），包括解马赛克、相机颜色空间到 sRGB 空间的转换、伽马校正、白平衡、色调映射、色域映射等，仿真计算结果见图5。在此基础上，还提出了相机相机响应曲线估计方法，结果见图6。


<div align = center><img src='/images/pub_img3.png' width = "60%" ></div>\
图3. Raw图像成像过程


<div align = center><img src='/images/pub_img4.png'></div>\
图4. 彩色图像形成及过程


<div align = center><img src='/images/pub_img5.png'></div>\
图5. 左边：Cannon相机的RAW图像和sRGB图像；中间：XCC SG光谱反射率采样；右边：NIKON相机的RAW图像和sRGB图像

同时为了验证本文的方法在不同光照条件的有效性，分别在不同的光照条件下进行了实验：晴天、阴天、蓝天及灯光。计算结果如图2-7所示，其中第一行是佳能5D Mark II的计算结果，第二行是Nikon D100的计算结果。

<div align = center><img src='/images/pub_img6.png'></div>\
图6. 不同光照下相机的光谱响应曲线


[1] Jiandong Tian, Zhigang Duan, Weihong Ren, Zhi Han, Yandong Tang, "Simple and Effective Calculations about Spectral Power Distributions of Outdoor Light Sources for Computer Vision", Optics Express, Vol. 24, No. 7, pp: 7266-7286, 2016.

[2] Jiandong Tian,Yandong Tang, "Wavelength-sensitive-function controlled reflectance reconstruction", Optics Letters, Vol. 38, No. 15, pp: 2818–2820, 2013.

[3] Denglu Wu, Jiandong Tian*, Yandong Tang, "Optimized basis function for spectral reflectance recovery from tristimulus values", Optical Review, Vol. 21, No. 2, pp: 117–126, 2014.

[4] Denglu Wu，Jiandong Tian*，Bingfeng Li, Yandong Tang,"Recovering Sensor Spectral Sensitivity from Raw Data", Journal of Electronic Imaging Vol. 22, No 2, pp: 023-032, 2013.



2.复杂光照下图像处理的理论模型及算法
======
结合大气物理与成像光学，我们在早期工作中提出了图像中阴影的三色衰减模型（Tricolor Attenuation Model, TAM）和光照线性模型（Illumination Linearity Model），它们分别描述了图像中阴影和非阴影背景之间的三通道衰减以及线性比率关系。在理论上证明了该模型的参数不依赖于物体的反射曲线，即不管场景多复杂，被阴影覆盖的不同物体同其周围的非阴影区域的像素比值是定值，并且证明了该值由太阳角度（天顶角）唯一确定。

<div align = center><img src='/images/pub_img7.png'></div>
图7. 阴影覆盖的不同物体同其周围的非阴影区域的像素比值是定值，且该值由太阳角度（天顶角）唯一确定

我们进一步计算了不同太阳角度和不同气象条件下（气溶胶）下的太阳辐射光谱和天空辐射光谱，根据室外阴影只受天空光照射的特点，提出了光谱比率理论（Spectrum Ratio），总结了不同太阳角度和天气下光谱比率的共同点，据此发现了四个新的阴影物理特征，适用于不同天气下的光照处理，揭示了图像中光照变化特征与太阳角度的关系。在我们三色衰减模型、线性模型和光谱比率理论等前述工作的基础上，团队历时2年采集了不同光照条件、不同反照率、不同场景、不同季节、不同时间段、和不同太阳光角度下的3088对有阴影/无阴影图像，建立了首个，也是迄今为止最大、最丰富的光照处理数据库（SRD），首次将光照物理特性（线性模型与光谱比率理论）与深度学习工具相结合，提出了图像去阴影深度网络Deshadownet，并提出了大规模数据库下阴影去除的基本评价准则（Evaluation Metrics）。在线性模型和光谱比率理论的基础上，我们提出了基于反射光谱的反光消除模型，提出了阴影去除和光照分解、变换算法，图像处理结果见图7。开展了复杂光照下视觉算法的研究，提升了目标识别、目标跟踪、图像分割等视觉任务的性能，结果见图8。

<div align = center><img src='/images/pub_img71.png'></div>\
图7. 阴影、反光去除、光照变换和光照分离图像处理结果展示

<div align = center><img src='/images/pub_img8.png'></div>\
图8. 复杂光照下的目标跟踪、识别视觉任务结果

代表性论文：\
<!-- 相关成果分别发表在图像处理领域权威期刊IEEE Transactions on image processing，2009（第一作者, DOI: 10.1109/TIP.2009.2026682）和视觉旗舰会议 IEEE CVPR，2011（第一作者, DOI: 10.1109/CVPR.2011.5995622）。该工作发表于模式识别著名期刊 Pattern Recognition，2016 （第一作者, DOI:10.1016/j.patcog.2015.09.006）。该工作发表于视觉领域顶级会议IEEE CVPR 2017（通讯作者，spotlight oral paper, DOI: 10.1109/ CVPR.2017.248）。相关成果发表于图像处理领域权威期刊IEEE Transactions on image processing，2017 (通讯作者，DOI: 10.1109/TIP. 2017.2675204)，IEEE Transactions on image processing，2016 (第二作者，DOI: 10.1109/TIP.2016.2642788)，视觉领域顶级会议IEEE CVPR，2017（通讯作者，DOI: 10.1109/ CVPR.2017.248）。代表性论文发表在IEEE Transactions on Image Processing，2022（通讯作者，DOI: 10.1109/TIP.2022.3166638），IEEE Transactions on Multimedia 2021（第二作者，DOI: 10.1109/TMM.2021.3087347），Pattern Recognition 2021（通讯作者，DOI：10.1016/j.patcog.2021.108129）。 -->

[5]Jiandong Tian, Jing Sun, Yandong Tang,“Tricolor Attenuation Model for Shadow Detection”,IEEE Transactions on Image Processing, Vol. 18, No. 10, pp: 2355-2363, 2009.

[6]Jiandong Tian, Yandong Tang, “Linearity of each channel pixel values from a surface in and out of shadows and its applications”, IEEE Conference on Computer Vision and Pattern Recognition (IEEE CVPR 2011).

[7]Jiandong Tian, Xiaojun Qi, Liangqiong Qu, and Yandong Tang, "New Spectrum Ratio Properties and Features for Shadow Detection", Pattern Recognition, Vol. 51, No. 3, pp: 85–96, 2016.

[8]Liangqiong Qu, Jiandong Tian*, Shengfeng He, Yandong Tang, Rynson Lau, "DeshadowNet: A Multi-context Embedding Deep Network for Shadow Removal", IEEE International Conference on Computer Vision and Pattern Recognition (CVPR), 2017. (spotlight oral paper)

[9]Weihong Ren, Jiandong Tian*, Zhi Han, Yandong Tang,"Video Desnowing and Deraining Based on Matrix Decomposition", IEEE International Conference on Computer Vision and Pattern Recognition (CVPR), 2017.

[10]Zhi Han, Jiandong Tian, Liangqiong Qu, and Yandong Tang, "A New Intrinsic-Lighting Color Space for Daytime Outdoor Images", IEEE Transactions on Image Processing, Vol. 26 No. 2, pp: 1031- 1039, 2017.

[11]Fan Baojie, Tian Jiandong, Peng Yan, Tang Yandong, "Discriminative Siamese Complementary Tracker with Flexible Update", IEEE Transactions on Multimedia,2021.

[12]Fan Baojie, Cong Yang, Tian Jiandong*, Tang Yandong, "Dynamic and reliable subtask tracker with general schatten p-norm regularization", Pattern Recognition,Vol. 120,pp: 108129,2021.

3.恶劣天气下图像处理的理论模型及算法
======
太阳角度（天顶角）对于从大气物理与成像计算角度理解并处理复杂光照处理至关重要；大气浑浊度（气溶胶）则对于恶劣天气的图像建模与处理具有重要价值。
在大气散射传输建模和图像去雾研究方面，我们推导了严重散射条件下的近场散射光线传输方程，发现了非均匀散射现象，提出了新的大气光值估计函数。该方法能够恢复出清晰的细节和对比度较高的无雾图像，而且速度非常快，**适于机器人视觉的实时性处理需求**。

<div align = center><img src='/images/pub_img10.png'></div>
图10. 大气和水下散射去除的结果和对比

在去除雨雪的研究方面，我们提出了一种基于雨雪物理光学模型的积分时间差分求解方程，可同时适用于稀疏和稠密雨雪的建模与消除，**非常适合应用于机器人面临的动态场景和相机移动的情况**，结果对比见图11。

<div align = center><img src='/images/pub_img11.png'></div>
图11. 雨雪去除对比

代表性论文：

[13]Jiandong Tian, Zak Murez, Tong Cui, Zhen Zhang, David Kriegman, Ravi Ramamoorthi,"Depth and Image Restoration from Light Field in a Scattering Medium", International Conference on Computer Vision (ICCV) 2017.

[14]Li Pengyue, Tian Jiandong*, Tang Yandong, Wang Guolin, Wu Chengdong, "Deep Retinex Network for Single Image Dehazing", IEEE Transactions on Image Processing,Vol. 30,pp: 1100-1115,2020.

[15]Weihong Ren, Jiandong Tian*, Zhi Han, Yandong Tang,"Video Desnowing and Deraining Based on Matrix Decomposition", IEEE International Conference on Computer Vision and Pattern Recognition (CVPR), 2017.

[16]Jiandong Tian, Zhi Han, Weihong Ren, Xiai Chen, Yandong Tang, "Snowflake removal for videos via global and local low-rank decomposition", IEEE Transactions on Multimedia, Vol. 20, No. 10, 2018, pp: 2659-2669.

[17]Pengyue Li, Mengshen Yun, Jiandong Tian*, Yandong Tang, Guolin Wang, Chengdong Wu, "Stacked Dense Networks for Single-Image Snow Removal", Neurocomputing, Vol. 367, No. 20, pp: 152-163, November 2019.

4.成像系统研制
======
团队以我们全天候视觉原创性理论为指导，结合先进光学成像技术，研制了多款新型相机和镜头，如下图所示。

<div align = center><img src='/images/pub_img12.png'></div>
图12.团队研制的新型成像器件

这些硬件系统嵌入我们提出的复杂光照和恶劣天气图像处理算法，软硬件结合发挥最大效能，形成了全天候视觉系统，成像效果如下图所示。
<div align = center><img src='/images/pub_img13.png'></div>
图13.团队研制的视觉系统成像结果


<!-- Getting started
======
1. Register a GitHub account if you don't have one and confirm your e-mail (required!)
1. Fork [this repository](https://github.com/academicpages/academicpages.github.io) by clicking the "fork" button in the top right. 
1. Go to the repository's settings (rightmost item in the tabs that start with "Code", should be below "Unwatch"). Rename the repository "[your GitHub username].github.io", which will also be your website's URL.
1. Set site-wide configuration and create content & metadata (see below -- also see [this set of diffs](http://archive.is/3TPas) showing what files were changed to set up [an example site](https://getorg-testacct.github.io) for a user with the username "getorg-testacct")
1. Upload any files (like PDFs, .zip files, etc.) to the files/ directory. They will appear at https://[your GitHub username].github.io/files/example.pdf.  
1. Check status by going to the repository settings, in the "GitHub pages" section

<!-- Site-wide configuration
------
The main configuration file for the site is in the base directory in [_config.yml](https://github.com/academicpages/academicpages.github.io/blob/master/_config.yml), which defines the content in the sidebars and other site-wide features. You will need to replace the default variables with ones about yourself and your site's github repository. The configuration file for the top menu is in [_data/navigation.yml](https://github.com/academicpages/academicpages.github.io/blob/master/_data/navigation.yml). For example, if you don't have a portfolio or blog posts, you can remove those items from that navigation.yml file to remove them from the header. 

Create content & metadata
------
For site content, there is one markdown file for each type of content, which are stored in directories like _publications, _talks, _posts, _teaching, or _pages. For example, each talk is a markdown file in the [_talks directory](https://github.com/academicpages/academicpages.github.io/tree/master/_talks). At the top of each markdown file is structured data in YAML about the talk, which the theme will parse to do lots of cool stuff. The same structured data about a talk is used to generate the list of talks on the [Talks page](https://academicpages.github.io/talks), each [individual page](https://academicpages.github.io/talks/2012-03-01-talk-1) for specific talks, the talks section for the [CV page](https://academicpages.github.io/cv), and the [map of places you've given a talk](https://academicpages.github.io/talkmap.html) (if you run this [python file](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.py) or [Jupyter notebook](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.ipynb), which creates the HTML for the map based on the contents of the _talks directory).

**Markdown generator**

I have also created [a set of Jupyter notebooks](https://github.com/academicpages/academicpages.github.io/tree/master/markdown_generator
) that converts a CSV containing structured data about talks or presentations into individual markdown files that will be properly formatted for the academicpages template. The sample CSVs in that directory are the ones I used to create my own personal website at stuartgeiger.com. My usual workflow is that I keep a spreadsheet of my publications and talks, then run the code in these notebooks to generate the markdown files, then commit and push them to the GitHub repository.

How to edit your site's GitHub repository
------
Many people use a git client to create files on their local computer and then push them to GitHub's servers. If you are not familiar with git, you can directly edit these configuration and markdown files directly in the github.com interface. Navigate to a file (like [this one](https://github.com/academicpages/academicpages.github.io/blob/master/_talks/2012-03-01-talk-1.md) and click the pencil icon in the top right of the content preview (to the right of the "Raw | Blame | History" buttons). You can delete a file by clicking the trashcan icon to the right of the pencil icon. You can also create new files or upload files by navigating to a directory and clicking the "Create new file" or "Upload files" buttons. 

Example: editing a markdown file for a talk
![Editing a markdown file for a talk](/images/editing-talk.png)

For more info
------
More info about configuring academicpages can be found in [the guide](https://academicpages.github.io/markdown/). The [guides for the Minimal Mistakes theme](https://mmistakes.github.io/minimal-mistakes/docs/configuration/) (which this theme was forked from) might also be helpful. --> 
