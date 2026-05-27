# Simplifying Complex Geology with Smarter Domaining – Machine Learning EDA for Geological Domaining, a Nickel Laterite Case Study

## Background
- Geology is always the key for domaining.
- Domaining decisions determine the tonnage and grade of the final estimation.
- In Nickel laterite, the geological domain derived from logging is usually deemed robust, and can be used for estimation domain.
- But, how can we(you) be so sure?
- This study will compare the estimation procedure based on logging and machine learning.
<img width="2240" height="689" alt="pic 1" src="https://github.com/user-attachments/assets/f95439ea-661d-4b94-a8c0-f4d5cc62ee84" />

## Workflow
<img width="1418" height="603" alt="workflow" src="https://github.com/user-attachments/assets/304c1efa-8bac-4be5-a7d3-ac2195509ad2" />

## Clean Database is Crucial
- Dirty database gives 33 possible domains. This is common in old or heritage data.
- One way to get around it is:
  - Blindly follow the domain.
  - Generalise the domain.
  - Make use of the multivariate data using k-means clustering.
<img width="3149" height="1515" alt="clean database is crucial" src="https://github.com/user-attachments/assets/5141a70c-a5cb-4255-b6bd-6b5d9f2943ad" />
blindly follow the domain


<img width="3149" height="1515" alt="clean database is crucial 2" src="https://github.com/user-attachments/assets/5937fdcf-12c4-4253-a52f-3dad8a5b70b5" />
generalise the domain


<img width="3149" height="1515" alt="clean database is crucial 3" src="https://github.com/user-attachments/assets/a6ac62fc-2a35-4c4a-9b05-6530d3069433" />
Make use of the multivariate data using k-means clustering


## K-means Clustering as a Tool for Geological Domaining
- K-means clustering is an unsupervised machine learning technique.
- The objective of clustering is to group similar data points and to discover underlying patterns or structures in the data.
- Similarity is an amount that reflects the strength of relationship between two data objects.
- K-mean algorithm works by establishing a centroid point in the middle of clustered data.
- All data points are then assigned to the nearest cluster based on their statistical similarity (association rules algorithm).
- The most appropriate number of  clustering or clustering algorithm for a particular problem often needs to be chosen experimentally.
<img width="1909" height="488" alt="k-means" src="https://github.com/user-attachments/assets/daf0af5d-7841-4b21-9fd1-328d858b4ade" />

## Principal Component Analysis as a Tool for Geological Domaining
- PCA is also an unsupervised machine learning technique.
- The objective of PCA is to capture the most variance in the data with fewer dimensions (principal components).
- Consider a geochemical dataset consisting of 2 elements A and B.
  - Trends and spatial correlation can be easily determined.

- Consider a geochemical dataset consisting of 2 elements A, B and C.
  - Trends and spatial correlation can be determined, but not that easily.

- Consider a geochemical dataset consisting of 2 elements A, B, C and D.
  - Trends and spatial correlation can possibly be determined, but increasingly challenging.
  - Numerical, noise, and irrelevant data trends are introduced.

- Consider a geochemical dataset consisting of 2 elements A, B, C, D, …n:
  - Trends and spatial correlation are challenging to visually determine as dimensions increase.
  - Numerical, noise, spurious correlations, and irrelevant data trends are significant.
  - It is essential to remove the noise, by reducing the dimension of the data, using PCA. A PCA plot converts the correlation (or the lack of) among all cells into a 2d graph.
<img width="1610" height="1188" alt="pca" src="https://github.com/user-attachments/assets/8216bddf-3dcd-4bff-a9dd-3e3ae6682356" />

## Data Preparation
- The cluster analysis process relies on samples that contained a complete set of analyses, missing or null values have a strong adverse effect on the classification outcome (Reid, 2019).
- Minimize closure effect.
- Data normalization.
<img width="2296" height="1557" alt="data prep" src="https://github.com/user-attachments/assets/321da597-7652-4224-ae4a-9f0af687fa4c" />

## Perform K-means and Review Cluster
- Let the machine learns!
- From the silhouette score provided, the most appropriate cluster are two or three clusters.
- Let’s review each possibility.
<img width="3219" height="713" alt="perform k-means" src="https://github.com/user-attachments/assets/34ad752d-c97d-4cc2-9040-016aa786e3e4" />

## Visual validation shows high agreement with manual domaining
<img width="3094" height="1470" alt="visual validations" src="https://github.com/user-attachments/assets/d9d93c0a-dd3f-4c13-966b-480c278f43fd" />
<img width="3094" height="1470" alt="visual validations 2" src="https://github.com/user-attachments/assets/7114b4c8-603d-4703-8676-d7589f899f08" />

## Validate with PCA
- Let the machine learns (again)!
- 2 PCs (PC1 and PC2) account for 77% total variance!
  - This indicates that a significant portion of the dataset's variance can be effectively summarized by just these two components, while the variance explained by the remaining five components is not significant and likely due to random processes or noise.
- The eigenvector plots derived from the PCA analysis provide insights into how each element influences principal components. 
- The influence on PC1 appears to be strongly linked to the type of lithology within the study area, suggesting that the primary variance in the dataset is related to geological differences of the limonite and saprolite present.
- The variation captured by PC2 is likely explained by the presence of metals, indicating that PC2 is sensitive to geochemical variations associated with mineralization processes.
<img width="2437" height="739" alt="validate with PCA" src="https://github.com/user-attachments/assets/bb983f4b-b343-439c-828b-5ab6fa52a16a" />

## Validate with PCA (cont..)
- Linear projections of multi-axis data onto a two-dimensional plane shows the PCs in context of the previous clusters.
- Samples are depicted as points, and variables are represented as vectors.
- The length of these vectors is proportional to their variability within the principal components being displayed.
- Elements such as Fe and Al2O3 are positively correlated towards PC1, associated with C2 cluster, while both elements are negatively correlated with SiO2 and MgO, which associated with C1 cluster.
- Ni shows high PC2, and is in the middle of PC1 and PC2, which means Ni is present in both C1 and C2 cluster. 
<img width="347" height="218" alt="validate with PCA 2" src="https://github.com/user-attachments/assets/09a33672-35c5-4388-9261-3fb3ab525017" />

## Conclusions
- Geological domaining is a critical step in resource estimation, and is a subjective decision.
- Machine learning can help uncover pattern in data, make the domaining process more objective and data driven.
- The data exhibits consistent results between manual domaining and domaining based on clustering.
- Further validation using PCA supports the clustering technique, by showing variance can be explained by two PCs and those two PCs are in high agreement with the clusters from previous k-means clustering analysis.
- Machine learning could be a powerful tool for geologists to explore the spatial uncertainty of the domain by a given dataset quickly.
