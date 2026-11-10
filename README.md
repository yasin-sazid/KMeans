# K-Means Image Color Clustering

A Java image-processing application that groups RGB pixels into `K` clusters and reconstructs an image using the resulting cluster centers. The project demonstrates unsupervised learning through a visual color-quantization workflow.

## Processing pipeline

```text
Input image → RGBArray → Clustering → OutputImage → Photos/output.jpg
```

- **`RGBArray`** extracts image pixels into a collection of Java `Color` values.
- **`Clustering`** initializes centers, assigns colors to clusters, and updates representative colors.
- **`OutputImage`** replaces pixels with cluster-center colors and writes a JPEG result.
- **`MainPackage.MainClass`** reads the image location and cluster count interactively and coordinates the workflow.

The implementation uses Java's built-in image APIs and explicitly implements the clustering logic, making the relationship between RGB distance, grouping, and the visual output easy to inspect.

## Run

Use a JDK and launch from `Kmeans/` so the output location resolves to its `Photos/` directory:

```bash
cd Kmeans
javac -d /tmp/kmeans-classes src/MainPackage/*.java src/othersPackage/*.java
java -cp /tmp/kmeans-classes MainPackage.MainClass
```

At the prompts, enter an image path such as `Photos/coco1.jpg`, followed by a cluster count. Inspect `Photos/output.jpg` after processing. The `Photos/` directory includes sample images for exploration.

## Explore the implementation

Start with [MainClass.java](Kmeans/src/MainPackage/MainClass.java), then follow the three processing classes under [othersPackage](Kmeans/src/othersPackage). Try different cluster counts to see how the palette changes as more representative colors become available.

**Technologies:** Java, AWT `Color`, `BufferedImage`, ImageIO, collections, and randomized initialization.
