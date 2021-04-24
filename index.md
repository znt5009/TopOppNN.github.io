---
layout: default
---

<html>
	<body>
		<table >
			<colgroup>
				<col style="width: 300px" />
				<col style="width: 160px" />
			</colgroup>
			<thead>
				<tr>
					<th colspan="2">
						<em>  </em>
					</th>
				</tr>
			</thead>
			<tbody>
				<tr>
					<td>
						<div> <img src = "https://raw.githubusercontent.com/znt5009/TopOppNN.github.io/gh-pages/initial_train.png" width ="500" img align="center"> </div>
					</td>
					<td>
						<img src = "https://raw.githubusercontent.com/znt5009/TopOppNN.github.io/gh-pages/final_train.png" width = "500"img align="center"> 
					</td>
				</tr>
			</tbody>
		</table>
	</body>
</html>

# How can using three dimensional convolution neural networks help speed up topology optimization?
Topology optimization seeks to calculate the ideal structure to support a given set of boundary and loading conditions within a given design domain. Following iterations of FEA and optimization, the results are presenting as element density probablilities. This iterative optimization process is computationally intensive, requiring large amounts of computing resources and time. The research team aims to try to speed up this portion of topology optmization by implementing a three dimensional convulation neural network to predict the final result after only a few optimization iterations. 

## Topology Optimization
Topology optimization is a process of optimizing layers of material to meet a given set of loads, boundry conditions, and other constraints. Topology optimization has been used in many different application for light weighting, in industries, additive manufacturing, aerospace industries, academia and many other. (Sosnovik and Oseledets,2019) Due to it’s importantance of this technique , a lot of research is being conducted to better improve the process. Our focus in our project is to increase the speed for more complicated geometry through the use of convolutional neural networks, which should lead to a lot of benefits to different industries such as aerospace and automotive industries in the future.

## Convolution Neural Networks
A convolutional neural network (CNN) is a neural network that can handle image processing much better than traditional neural networks. In this project the use of CNN would better suited than the use of traditional neural networks. A CNN works by using filters on the image and calculates a value for those points in the image. This value is then run through the layers of the CNN to pull the more important infomation from the image, thus allowing for the key features of the image to be passed along. This allows for many applications and the most common application is image processing that could label certain pictures as certain items that the CNN has been train to recognized. For this project the CNN is being used to identify areas of importance in the topology optimization process in order to speed up the entire process. This is done by training the CNN on a part to recognize patterns of topology optimization to then allow the program to skip steps in tradtional topology optimization. This will then lead to faster speeds for topology optimization which is a key issue with the implementation of topology optimization within broad industry.

## Synthetic Data Generation
The quality of a trained neural network is directly dependent on the quality of the data used to train and test the architecture. Large and complete datasets regarding topology optimization are a spectacle to come across, so the team decided to synthetically generate a dataset to be used to train the network. In order to build a more adaptable network, the dataset needed to be generated with a high degree of variability. To do this, the team used the free matlab program _top3d_ from Liu and Tovar (insert ref here). A key focus of this work was to feed more advanced models to the network through the use of specified holes within the elements internally and externally. This would create more unique starting geometry to represent more realistic loading conditions for parts in the real world. 
<html>
	<body>
		<table >
			<colgroup>
				<col style="width: 300px" />
				<col style="width: 160px" />
			</colgroup>
			<thead>
				<tr>
					<th colspan="2">
						<em> Description: </em>
					</th>
				</tr>
			</thead>
			<tbody>
				<tr>
					<td>
						<div> <img src = "https://raw.githubusercontent.com/znt5009/TopOppNN.github.io/gh-pages/DistForce.png" width ="500" align="center"> </div>
					</td>
					<td>
						<img src = "https://raw.githubusercontent.com/znt5009/TopOppNN.github.io/gh-pages/OvalPassive.png" width = "500" align="center"> 
					</td>
				</tr>
			</tbody>
		</table>
	</body>
</html>
 

Each model space contained 32 elements in the x direction, 12 elements in the y direction, and 8 elements in the z direction totalling in 3,072 unit elements. Constant parameters used inlcude a penalty of 3, an rmin of 1.5, volfrac of 0.3, Young's modulus of 1, and Poisson's ratio of 0.3. This model was run 4,000 times with randomization of the inclusion of holes, boundary conditions, and loading. The models had a 3/14 chance to have an internal hole, that had equal probability to go through 1 of the primary axes, be oval or rectangular, have three potential sizes, and up to four possible orientations depending on the size. There is also a 3/14 chance that a model would have an eternal hole on a randomly chosen plane, with four possible locations for each plane, with a random length and depth up to half the number of elements in the given direction. For boudary conditions, there would be equal chance to have 3 to 4 pinned nodes or a cantalievered face. The pinned nodes could be all planar or random with a weighted preference towards the outer edge of the part for more realistic conditions. The forces on the part follow a similar random distribution as the boundary conditions with the point forces ranging in number from 3 to 6.

After running each model, the nodal density probability and gradient data was compressed and saved for the first ten iterations as well as the final iteration. In addition to this, the nodal data for the loads and boundary conditions were also saved along the elemental data for their pbeing a whole, ie an element was passive. This set of data was then used in part or as a whole to train the developed neural networks.
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
