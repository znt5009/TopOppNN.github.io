---
layout: default
---
# How can using three dimensional convolution neural networks help speed up topology optimization?
Topology optimization seeks to calculate the ideal structure to support a given set of boundary and loading conditions within a given design domain. Following iterations of FEA and optimization, the results are presenting as element density probablilities. This iterative optimization process is computationally intensive, requiring large amounts of computing resources and time. The research team aims to try to speed up this portion of topology optmization by implementing a three dimensional convulation neural network to predict the final result after only a few optimization iterations. 

## Topology Optimization

Topology optimization has been used in many different application for light weighting, in industries, additive manufacturing, aerospace industries, academia and many other. (Sosnovik and Oseledets,2019) Due it it’s important , a lot of companies are focusing on this technology in order to provide a better quality manufacturing. Our focus in our project is to increase the speed for more complicated geometry to be run throughout the topology method using neural network technology which should lead to a lot of benefits to different industries such as aerospace and automotive industries in the future.

## Convolution Neural Networks
A convolutional neural network (CNN) is a neural network that can handle image processing much better than traditional neural networks. In this project the use of CNN would better suited than the use of traditional neural networks. A CNN works by using filters on the image and calculates a value for those points in the image. This value is then run through the layers of the CNN to pull the more important infomation from the image, thus allowing for the key features of the image to be passed along. This allows for many applications and the most common application is image processing that could label certain pictures as certain items that the CNN has been train to recognized. For this project the CNN is being used to identify areas of importance in the topology optimization process in order to speed up the entire process. This is done by training the CNN on a part to recognize patterns of topology optimization to then allow the program to skip steps in tradtional topology optimization. This will then lead to faster speeds for topology optimization which is a key issue with the implementation of topology optimization within broad industry.

## Synthetic Data Generation

## Neural Network Architecture

## Results

## Reference
I. Sosnovik and I. Oseledets, “Neural networks for topology optimization,” Russian Journal of Numerical Analysis and Mathematical Modelling, vol. 34, no. 4, pp. 215–223, Aug. 2019, doi: 10.1515/rnam-2019-0018.

You can use the [editor on GitHub](https://github.com/znt5009/TopOppNN.github.io/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/znt5009/TopOppNN.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
