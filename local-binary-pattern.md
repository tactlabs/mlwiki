/ [Home](index.md)

# Local Binary Pattern Algorithm

Local Binary Pattern is a simple and efficient texture operator that labels the pixels of a picture by considering the threshold of the neighborhood of each pixel and considers the result as a binary number.

First, an intermediate image is created which describes the original image better by using a sliding window concept based on the radius and neighbors parameters. Next, the intermediate image is divided into multiple grids for which histograms are plotted. The obtained histograms are concatenated to get a final histogram. These steps are performed again for a new image and the histograms are compared to find similar images.

<br>

**Created by Santhosh Kannan**

---

<br>
