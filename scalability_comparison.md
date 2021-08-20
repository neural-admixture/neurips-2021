# Training scalability comparison

As an extension to [a previous analysis](https://github.com/neural-admixture/neurips-2021/blob/main/scalability.md),
we have compared the execution times of ALStructure, TeraStructure and Neural ADMIXTURE (using both CPU and GPU) on artificially generated
datasets.

The datasets consist of all combinations of <img src="https://render.githubusercontent.com/render/math?math=n \in \{1000, 5000, 10000, 50000\}">
and <img src="https://render.githubusercontent.com/render/math?math=m \in \{1000, 10000, 50000, 100000\}">,
where <img src="https://render.githubusercontent.com/render/math?math=n"> is the number of samples and
<img src="https://render.githubusercontent.com/render/math?math=m"> is the number of variants (SNPs).

Results do not include ALStructure's execution time on datasets of 50000 samples because ALStructure is so slow on such datasets. (For 1000 SNPs, execution was halted after >13 hours without convergence being achieved.) While TeraStructure and Neural ADMIXTURE are able to handle large number of samples (>50000), ALStructure is not capable of handling such numbers of samples, as seen in the plots where the number of SNPs are being fixed.

Results, which can be observed below, show that Neural ADMIXTURE is consistently far faster than ALStructure and TeraStructure, especially for larger datasets, which is the area of application of all the methods. Moreover, and not surprisingly, Neural ADMIXTURE scales even better than the other methods when using GPUs.


## Fixed number of samples
![fixed_samples_1000](https://user-images.githubusercontent.com/88712503/130130307-8e5a296a-eccf-4f5c-8562-d48f1f9b8591.png)
![fixed_samples_5000](https://user-images.githubusercontent.com/88712503/130130312-eceeffae-c8d2-46fa-80e0-41a33c861359.png)
![fixed_samples_10000](https://user-images.githubusercontent.com/88712503/130130314-4143769b-9b5d-486c-bd94-fc3a4fbe4995.png)
![fixed_samples_50000](https://user-images.githubusercontent.com/88712503/130130315-9287201e-9cb3-4752-a92c-82fed29ff465.png)

## Fixed number of SNPs
![fixed_snps_1000](https://user-images.githubusercontent.com/88712503/130130403-ddd4cb64-a7ff-4055-8ceb-d37870eba54f.png)
![fixed_snps_10000](https://user-images.githubusercontent.com/88712503/130130406-3543dc24-4fa4-45f0-b1cc-f69a19bdf94c.png)
![fixed_snps_50000](https://user-images.githubusercontent.com/88712503/130130411-4912cb15-1ab5-495e-a13e-9d6563b47924.png)
![fixed_snps_100000](https://user-images.githubusercontent.com/88712503/130130412-68effa91-65b3-47ff-89d3-431847d610f3.png)
