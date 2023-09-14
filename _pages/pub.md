---
# permalink: /publications/
# title: "田建东的论文"
# excerpt: "publication"
# author_profile: true
# redirect_from: 
#   - /pub/
#   - /pub.html
layout: archive
title: "Publications"
permalink: /pub/
author_profile: true
---

1. 大气辐射传输、场景反射、相机成像建模
======
室外环境下，太阳发出的光线经过地球的大气层会受到大气吸收、反射、和散射等影响，导致到达地面的光照会随着时间和大气因素而变化，进而导致室外场景图像的复杂性和多样性。大气物理领域的研究表明**至少20多个参数**会影响光照和天气的变化，但这些参数对于机器人的应用来说**难以获得**。为解决该问题，团队提出了适于机器人视觉成像计算的大气辐射光谱计算方法。我们的方法只需两个参数：天顶角（可根据机器人GPS坐标及时间信息计算）及气溶胶指数（我们在论文中给出了利用图像中阴影强度来计算该参数的方法，在某些具体应用中也可根据天气预报或空气污染指数获得），在参数减少了90%的情况下仍能保持计算精度，详见表1与图1。

表1. 我们方法与大气物理中两种经典计算方法（Bird和SMART32）的计算复杂度对比。我们方法只需2个参数和简单计算，经典大气物理方法需要20多个参数和复杂计算，且这20多个参数对于机器人的应用来说难以获得。
<img src='/images/pub_data1.png'>

图1. 地表大气辐照度计算结果，左侧为太阳直射光，右侧为天空散射光。第一排为我们方法与大气物理两种经典计算方法（Bird和SMART32）的对比结果。结果表明我们方法（只需2个参数，经过简单计算）可以非常逼近大气物理经典方法（需要20多个参数，经过复杂计算）的计算结果。第二排为我们计算方法和光谱仪实测数据的对比（红色为真实值）。结果表明我们的计算结果非常接近实测结果，可确保用于机器人视觉。
<img src='/images/pub_img1.png'>


2. 场景反射光谱重建
======
我们的贡献在于提出了相机/人眼响应光谱加权控制反射光谱重建精度，使得相机/人眼响应高的谱段重建精度更高。图2是4个色块的反射率光谱重建结果，其中红色表示真实光谱，绿色表示我们计算得到的光谱, 蓝色表示经典PCA方法得到结果，黑色代表颜色匹配函数三通道的和。横坐标代表波长，纵坐标代表反射率。从结果上看，我们方法在颜色匹配函数（对应于相机的色彩响应曲线）的峰值处的精度远高于PCA方法的精度，这样非常利于提高利用此反射曲线进行成像计算的精度，统计结果表明我们方法得到反射光谱的成像精度比主流方法提高了50%。

图2. 2个代表性色块的反射光谱重建结果
<img src='/images/pub_img2.png'>

3. 相机成像建模与仿真
======
研究进入相机的光线经过光电转换后得到的 Raw 数据（图3）以及后续处理的过程（图4），包括解马赛克、相机颜色空间到 sRGB 空间的转换、伽马校正、白平衡、色调映射、色域映射等，仿真计算结果见图5。在此基础上，还提出了相机相机响应曲线估计方法，结果见图6。

图3. Raw图像成像过程
<img src='/images/pub_img3.png'>

图4. 彩色图像形成及过程
<img src='/images/pub_img4.png'>

图5. 左边：Cannon相机的RAW图像和sRGB图像；中间：XCC SG光谱反射率采样；右边：NIKON相机的RAW图像和sRGB图像
<img src='/images/pub_img5.png'>

同时为了验证本文的方法在不同光照条件的有效性，分别在不同的光照条件下进行了实验：晴天、阴天、蓝天及灯光。计算结果如图2-7所示，其中第一行是佳能5D Mark II的计算结果，第二行是Nikon D100的计算结果。

图6. 不同光照下相机的光谱响应曲线
<img src='/images/pub_img6.png'>

<!-- Getting started
======
1. Register a GitHub account if you don't have one and confirm your e-mail (required!)
1. Fork [this repository](https://github.com/academicpages/academicpages.github.io) by clicking the "fork" button in the top right. 
1. Go to the repository's settings (rightmost item in the tabs that start with "Code", should be below "Unwatch"). Rename the repository "[your GitHub username].github.io", which will also be your website's URL.
1. Set site-wide configuration and create content & metadata (see below -- also see [this set of diffs](http://archive.is/3TPas) showing what files were changed to set up [an example site](https://getorg-testacct.github.io) for a user with the username "getorg-testacct")
1. Upload any files (like PDFs, .zip files, etc.) to the files/ directory. They will appear at https://[your GitHub username].github.io/files/example.pdf.  
1. Check status by going to the repository settings, in the "GitHub pages" section

Site-wide configuration
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
