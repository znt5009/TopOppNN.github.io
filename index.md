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
						<img src = "https://raw.githubusercontent.com/znt5009/TopOppNN.github.io/gh-pages/final_train.png" width = "500" img align="center"> 
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
Our network consists of 3D convolutional layers with Rectified Linear Unit(ReLU) as the non-linear activiation function. We also use MaxPopoling to downsize the input data in order to encode the data into the network. Then Up Sampling was used to help decode the encoded the data along with concatenation layers to link certain weights from previous layers. Finally, we used the hyperbolic tangent as the activation function for the decoder, because this resulted in the highest accurary compared to the other activiation functions that were tested. When checking for loss in the model due to the nature of what we wanted to accomplish the binary cross entropy loss function was used. 

## Results
Overall the project was fairly successful in using CNN as part of the topology optimization process. In this project, the team was able to get a binary acurracy of 95.1% and an RMS Acurracy of 80.2%. This means that through the use of this CNN a prediction of what the model will look like after topology optimizatioin is determined with a fairly high accuracy to what the actual model will look like. This process still takes a lot of time and computional resources, but with better technology this CNN could be used to save hours in the design process of parts that need to be optimizied for industries like space travel. In the table below you can see the input data, the actual output, the predictied output, and the binary predictions.

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
						<em> Actual Topology vs Model Topology </em>
					</th>
				</tr>
			</thead>
			<tbody>
				<tr>
					<td>
						<div> <img src = "https://raw.githubusercontent.com/znt5009/TopOppNN.github.io/gh-pages/Input%20Data.PNG" width ="500" align="center"> </div>
					</td>
					<td>
						<img src = "https://raw.githubusercontent.com/znt5009/TopOppNN.github.io/gh-pages/True%20Output.PNG" width = "500" align="center"> 
					</td>
				</tr>
				<tr>
					<td>
						<div> <img src = "https://raw.githubusercontent.com/znt5009/TopOppNN.github.io/gh-pages/intital%20prediction%20non%20binary.PNG" width ="500" align="center"> </div>
					</td>
					<td>
						<img src = "https://raw.githubusercontent.com/znt5009/TopOppNN.github.io/gh-pages/Predicted%20Output.PNG" width = "500" align="center"> 
					</td>
					
				</tr>
			</tbody>
		</table>
	</body>
</html>



## Reference
I. Sosnovik and I. Oseledets, “Neural networks for topology optimization,” Russian Journal of Numerical Analysis and Mathematical Modelling, vol. 34, no. 4, pp. 215–223, Aug. 2019, doi: 10.1515/rnam-2019-0018.
