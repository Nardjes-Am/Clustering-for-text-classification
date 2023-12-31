# Clustering-for-text-classification

### Pseudo algorithm 
```
Input:
DT={DL, DU_}: A collection of labeled and unlabeled samples.
Output:
FinalClusters: a collection of labeled clusters
Labels for the unlabeled samples in DT
Method
(i). Initialization
Step 1. K = Number of unique labels in DT (number of classes)
Step 2. InitialSeeds = randomly chosen K samples (one from each unique class present in DT
)
Step 3. SeedLabels + cluster indices of IntialSeeds
(ii). Initial K-means clustering
Step 4. Apply K-means on DT with IntialSeeds as initial cluster centroids to get K clusters say, Partition
(iii). Recursive K-means clustering
Step 5. For every cluster Pi in the Partition
Step 6. NCPi = Number of unique class labels in Pi and
        LSPi = Number of labeled samples of each unique class in Pi
Step 7. If NCPi > 1 then,
Step 8. ClassLabel(Pi) = Label (max (LSPi))
Step 9. For each class j other than in ClassLabel(Pi)
Step 10. RelativePercentagej = (LSPi [j] / LSPi [ClassLabel(Pi)])*100
Step 11. If RelativePercentagej > greater than Th then,
Step 12. RKMSSL (Pi)
Step 13. Goto step 15;
end
End for
Add Pi to the FinalClusters set
Step 14. End if
(iv) Labeling
Step 15. For every unlabeled document du in cluster Pi
Step 16. Label(du) = ClassLabel(Pi)
Step 17. End for
Step 18. End for
Algorithm Ends
```
### Reference 
