# Benchmarks


Apart from benchmarking against ADMIXTURE, we are also including a benchmark against TeraStructure and ALStructure, two of the newest fast alternatives to ADMIXTURE.
We include a table below to show that we match or outperform competing methods both in speed and clustering accuracy results.

Specifically, we show that Neural ADMIXTURE outperforms in speed TeraStructure (in both CPU and GPU), and surpasses ALStructure in GPU while being competitive in CPU.
While ALStructure seems to provide faster computation in some scenarios, the clustering results are quite poor
(_e.g._ observe the high error in CHM-22-SIM dataset). Therefore, we show that our proposed approach, on average,
surpasses competing methods in both speed and clustering quality. Moreover, we include another dataset consisting of all chromosomes,
where we have pruned and filtered the markers to minimize linkage disequilibrium (LD).
Furthermore, we have included two more unsupervised evaluation metrics in our benchmark: the [Fowlkes-Mallows index](https://www.tandfonline.com/doi/abs/10.1080/01621459.1983.10478008) and the [V-Measure](https://aclanthology.org/D07-1043.pdf).

As neither TeraStructure nor ALStructure offer a projective analysis/inference mode (that is, they cannot be trivially used to get predictions on unseen data), we are only
reporting the metrics on the training data in the following table. 

<img width="785" alt="new_tab" src="https://user-images.githubusercontent.com/88712503/128921313-67973d64-9a0b-4898-b108-f6b01f5602f8.png">

