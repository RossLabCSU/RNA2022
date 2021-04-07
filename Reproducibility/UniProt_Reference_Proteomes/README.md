# Reproducing identification and Pfam analyses of RS domains among UniProt reference proteomes

### Instructions
1. Download all files in the UniProt_Reference_Proteomes directory.
2. Download all archaeal, bacterial, eukaryotic, and viral proteomes from https://figshare.com/articles/dataset/Archaea_ProteinSequences/12937637, (https://figshare.com/articles/dataset/Bacteria_ProteinSequences_Part1/12939812, https://figshare.com/articles/dataset/Bacteria_ProteinSequences_Part2/12939980), (https://figshare.com/articles/dataset/Eukaryota_ProteinSequences_Part1/12937703, https://figshare.com/articles/dataset/Eukaryota_ProteinSequences_Part2/12939479), and https://figshare.com/articles/dataset/Viruses_ProteinSequences/12942362 respectively. NOTE: the bacterial and eukaryotic sets were split into two downloads due to file size constraints.
3. Extract the proteome files *__in separate folders corresponding to each domain of life. The folders MUST be named "Archaea", "Bacteria", "Eukaryota", and "Viruses", respectively__*.
4. Place a copy the "LCD-Composer_MultiProteomeVersion.py", "make_SRcompRange_BatchFile_DomainsOfLife.py", and "get_SR_prots_above_CombinedSRthreshold_MultiOrganismVersion.py" scripts into each of the folders that you created in Step 3. By default, the LCD-Composer_MultiProteomeVersion.py script will scan all sub-folders for FASTA files, so each of the folders should only contain the above-mentioned files with no other subfolders or FASTA files.
5. Navigate to appropriate folder(s) via command line.
6. Run the following commands (NOTE: the commands corresponding to different domains of life can be run concurrently to decrease overall computation time. Additionally, batch files can be divided into smaller batch files and run concurrently to further decrease computation time.):

In the Archaea folder run the following commands:
```    
python make_SRcompRange_BatchFile_DomainsOfLife.py Archaea
```

```    
./RUN_LCD-Composer_Archaea_SRcompRANGE_Batch.bat
```

```    
python get_SR_prots_above_CombinedSRthreshold_MultiOrganismVersion.py Archaea
```

In the Bacteria folder run the following commands:
```    
python make_SRcompRange_BatchFile_DomainsOfLife.py Bacteria
```

```    
./RUN_LCD-Composer_Bacteria_SRcompRANGE_Batch.bat
```

```    
python get_SR_prots_above_CombinedSRthreshold_MultiOrganismVersion.py Bacteria
```

In the Eukaryota folder run the following commands:
```    
python make_SRcompRange_BatchFile_DomainsOfLife.py Eukaryota
```

```    
./RUN_LCD-Composer_Eukaryota_SRcompRANGE_Batch.bat
```

```    
python get_SR_prots_above_CombinedSRthreshold_MultiOrganismVersion.py Eukaryota
```

In the Viruses folder run the following commands:
```    
python make_SRcompRange_BatchFile_DomainsOfLife.py Viruses
```

```    
./RUN_LCD-Composer_Viruses_SRcompRANGE_Batch.bat
```

```    
python get_SR_prots_above_CombinedSRthreshold_MultiOrganismVersion.py Viruses
```
</br>
7. Once all of the commands listed above have finished running, each folder should contain a file ending in "SequenceDictionary" (.fasta file) and a file ending in "SR_proteins_with_Combined_S-R_Above_70" (.tsv file). Copy these files from each folder into a single location that also contains the XXXXXXXXXXXXXXXXXXx scripts.
8. Navigate to this new location via command line and run the following commands in-sequence:

```    
python get_DomainsOfLife_OrganismList_df.py
```

```    
python plot_NumberOfProts_with_SRdomain_DomainsOfLife.py
```

These two commands generate Fig 4A and Tables S3-S6.