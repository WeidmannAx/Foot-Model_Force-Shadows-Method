# Foot-Model_Force-Shadows-Method

"MeshData.mat" is a matlab data file containing the used foot model.

__________________________________________________________________________________________________________________

The data regarding the left foot is contained in the structure "MSH_left"; "MHS_right" contains the right foot data.

Within MSH_left and MSH_right, the data is divided into the following substructures:
	Heel, Arch, MetaL (left metatarsum part), MetaR (right metatarsum part), 
	ToeL (left part of toes), ToeR (right part of toes), Total (the boundary polygon of the total foot);
	confer also Figure 1 on the right for the parts (separated by the black solid line).
	
Each of the mentioned substructures comprise three matrices, "p", "TR", and "bp", where
	"p" 				denotes all nodes (points) of the triangles within one subregion,
	"TR"				denotes the indices of the triangles, e.g., the nodes concerning the first triangle 
						can be obtained via the first line of TR, and
	"bp" 				denotes the boundary polygon of the respective subregion.
	The triangle meshes are depicted in Figure 1 on the right (grey color).
	
__________________________________________________________________________________________________________________
	
Example Code (MATLAB):
	Each triangle polygon consists of three nodes.
	The nodes/points of the left heel can be obtained via: "MSH_left.Heel.p".
	
	To plot the first triangle, we define (for abbreviation purposes)
	"TR = MSH_left.Heel.TR(1,:);"
	"p = MSH_left.Heel.p;"
	
	Then, the nodes can be called by "p(TR)", and, in order to plot the closed triangle 
	(i.e., again include the first node after the third node), we code:
	"plot([p(TR([1:3, 1]), 1)], [p(TR([1:3, 1]), 2)]);" 	(2D plot).
	
	For plotting the whole triangle mesh of the heel, we loop over the lines of "MSH_left.Heel.TR".
	
