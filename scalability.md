# Training scalability analysis

To assess the scalability of the architecture, we have trained networks on artificially generated data.
We have trained on all combinations of <img src="https://render.githubusercontent.com/render/math?math=n \in \{1000, 5000, 10000, 50000\}">
and <img src="https://render.githubusercontent.com/render/math?math=m \in \{1000, 10000, 50000, 100000, 300000\}">,
where <img src="https://render.githubusercontent.com/render/math?math=n"> is the number of samples and
<img src="https://render.githubusercontent.com/render/math?math=m"> is the number of variants, but one
(n=50000, m=300000) due to resource limitations. All networks were trained using GPUs.

While the following plots will qualitatively show that when fixing one of the variables the execution time is linear with respect to the other, we have
been able to model the execution time <img src="https://render.githubusercontent.com/render/math?math=t"> with an R<sup>2</sup> > 0.99 with a simple linear model
which only takes into account both variables as well as the interaction between them
(<img src="https://render.githubusercontent.com/render/math?math=t(n,m) \approx a %2B b \cdot n %2B c \cdot m %2B d \cdot n \cdot m">).

## Fixed number of samples
![fixed_samples_1000](https://user-images.githubusercontent.com/88712503/128860407-3a761d78-f8c2-4e02-9e8a-4997c7f27764.png)
![fixed_samples_5000](https://user-images.githubusercontent.com/88712503/128860413-fa5f47f3-9296-4399-ac66-9f2ecd6d1d83.png)
![fixed_samples_10000](https://user-images.githubusercontent.com/88712503/128860414-ad004176-ac1c-4489-94f9-512e0d50f17a.png)
![fixed_samples_50000](https://user-images.githubusercontent.com/88712503/128860416-fdef1422-adca-4a5e-8193-115588a252a6.png)

When fixing the number of samples, the execution time looks like it is linear with respect to the number of SNPs.


## Fixed number of SNPs
![fixed_snps_1000](https://user-images.githubusercontent.com/88712503/128860418-71409015-5c2e-4317-8035-c11bf9d6f41d.png)
![fixed_snps_10000](https://user-images.githubusercontent.com/88712503/128860421-b6413eca-a80f-47af-b70b-eb57bde30c56.png)
![fixed_snps_50000](https://user-images.githubusercontent.com/88712503/128860424-1dd121d3-9236-4959-b573-9a296360f7d5.png)
![fixed_snps_100000](https://user-images.githubusercontent.com/88712503/128860425-bba93bf6-81bf-4556-a3ae-4e7df1bd53ba.png)
![fixed_snps_300000](https://user-images.githubusercontent.com/88712503/128860427-098d734a-50cc-4e47-8f1c-654ba7763c26.png)

Similarly, when fixing the number of SNPs, the execution time appears to be linear with respect to the number of samples.
