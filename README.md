![GRIMER](grimer/img/logo.png)

Examples of GRIMER report

## Reports

- Preterm Infant Resistome downloaded from [MicrobiomeDB](https://microbiomedb.org/mbio/app/record/dataset/DS_82fe0308e2) (124 samples, original publication 10.1038/nmicrobiol.2016.24)

**[GRIMER report](https://pirovc.github.io/grimer-reports/microbiomedb/ResistomeAmplicon.html)**

<details>
  <summary>commands</summary>

```bash
wget https://microbiomedb.org/common/downloads/release-22/82fe0308e2032de2041694df6592ba542ea84b86/ResistomeAmplicon.16s_DADA2.taxon_abundance.biom

wget https://microbiomedb.org/common/downloads/release-22/82fe0308e2032de2041694df6592ba542ea84b86/ResistomeAmplicon.16s_DADA2.taxon_abundance.tsv

grimer -c grimer/config/default.yaml -i ResistomeAmplicon.16s_DADA2.taxon_abundance.biom -m ResistomeAmplicon.16s_DADA2.sample_details.tsv -d -g -t ncbi -r superkingdom phylum class order family genus species --title "MicrobiomeDB Preterm Infant Resistome (V4)" -o ResistomeAmplicon.html
```

</details>

- Antibiotic induced changes in the microbiota disrupt redox dynamics in the gut downloaded from [MGnify](https://www.ebi.ac.uk/metagenomics/studies/MGYS00005180) (573 samples, V4 region of 16S rRNA gene - original publication 10.7554/elife.35987)

**[GRIMER report](https://pirovc.github.io/grimer-reports/mgnify/MGYS00005180.html)**

<details>
  <summary>commands</summary>

```bash
# Download
STUDYACC="MGYS00005180"
grimer/scripts/mgnify_download.py $STUDYACC mgnify/

# Select largest profile available and metadata
TABLE=$(ls -S mgnify/${PREFIX}*taxonomy_abundances*.tsv.gz | head -n 1)
METADATA="mgnify/${STUDYACC}_metadata.tsv.gz"

grimer -c config/default.yaml -i $TABLE -m $METADATA -f ";" --obs-replace '^.+__' '' '_' ' ' -r superkingdom kingdom phylum class order family genus species -t ncbi -d -g -o "mgnify/${STUDYACC}.html" --title "MGnify ${STUDYACC}"  

```

</details>
