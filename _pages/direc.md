---
layout: archive
title: Directions    
permalink: /direc/
author_profile: true
---


研究背景
======
**复杂光照和恶劣天气下的机器人视觉及环境感知是机器人学科中的一个瓶颈问题，室外场景存在光照、天气或季节等复杂多变的环境因素**，不同的光照条件、不同的气象条件甚至不同的时间（早晨、上午、下午、傍晚）都会造成图像的巨大差异，严重降低了机器人视觉及环境感知算法的稳定性。

图1：针对复杂光照与恶劣天气的图像处理对于提高智能机器人在室外环境下的环境感知、导航避障和作业能力具有重要意义。
<img src='/images/图1.png'>

图像是视觉算法的基础，**光照和天气的变化改变了图像的像素值分布**（如图1-b和1-c对比所示），**这影响了机器人视觉算法的根基**，进而影响了机器人的一些基本能力如SLAM、避障导航、视觉伺服、环境理解及作业，给机器人环境感知与行为决策带来了巨大的挑战。**目前视觉算法大多是针对质量好、光照条件稳定图像（如图1-c所示）开发的**。实际上，在室外复杂的自然光照与恶劣气象条件下，**图像质量差别很大（如图1-b所示）**。这种情况下，机器人视觉系统的表现往往差强人意，缺乏对环境的自适应能力及鲁棒性，因此针对该问题的图像预处理（图1-b到图1-c）对机器人视觉非常重要。

研究方向：
======

（1）复杂光照下图像处理的理论模型及算法
------
主要研究内容包括基于大气辐射传输计算的图像光照建模、阴影检测与去除、反光去除、光照恒常、光照分解和光照变换等。

（2）恶劣天气下图像处理的理论模型及算法
------
主要研究内容主要包括大气吸收和散射传输计算方法、水体散射传输模型、雨雪雾去除算法等

（3）成像系统研制
------
主要研究内容包括基于先进光学成像技术的新型相机和镜头研制，ISP优化等


<!-- 
Getting started
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
