1. We want to get the outline of the defects so we will want to find the edges in the image
	1. We may need to run a filter to:
		1. Grayscale the image to make the edges look reasonable
		2. Blur or median filter to remove the noise caused by the color of the road
	2. I'll add a function to remove the small, squarish, edges that are made by the road.
		1. Turns out that rocks and very cracked roads make it really hard to have meaningful defects be generated.
2. Either pattern match or find another way to find the defects (rest of the fucking owl)
	1. Try considering each "feature" a defect and find ways to remove the ones that aren't
		1. Think about data mining a some kind of k-means
			1. Maybe not k-means, but some way to group the defect contours together
			2. Try to get a list of nodes that are part of the defect, then future defects will make sure that the nodes that they check aren't part of another defect.
		2. Can remove the non defects using some form of machine learning set
			1. This mean that we'll extract potential defects as their own pictures
			2. We'll also need a bank of pictures to train the system