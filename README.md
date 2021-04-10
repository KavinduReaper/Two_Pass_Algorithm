# Two Pass Algorithm
This is a fast and very simple method to implement and understand. It is based on graph traversal methods in graph theory. In short, once the first pixel of a connected component is found, all the connected pixels of that connected component are labelled before going onto the next pixel in the image. This algorithm is part of Vincent and Soille's watershed segmentation algorithm, other implementations also exist.

## Algorithm

### On the first pass:

1. Iterate through each element of the data by a column, then by row (Raster Scanning)
2. If the element is not the background
    1. Get the neighboring elements of the current element
    2. If there are no neighbors, uniquely label the current element and continue
    3. Otherwise, find the neighbor with the smallest label and assign it to the current element
    4. Store the equivalence between neighboring labels

### On the second pass:

1. Iterate through each element of the data by column, then by row
2. If the element is not the background
    1. Relabel the element with the lowest equivalent label

Here, the background is a classification, specific to the data, used to distinguish salient elements from the foreground. If the background variable is omitted, then the two-pass algorithm will treat the background as another region.
