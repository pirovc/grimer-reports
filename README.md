![GRIMER](https://raw.githubusercontent.com/pirovc/grimer/main/grimer/img/logo.png)

Examples of reports generated with [GRIMER](https://github.com/pirovc/grimer)

---

### WGS analysis from Leiby et al. "Lack of detection of a human placenta microbiome in samples from preterm and term deliveries"

***original publication: [10.1186/s40168-018-0575-4](https://doi.org/10.1186/s40168-018-0575-4)***

--> **[GRIMER report WGS](https://pirovc.github.io/grimer-reports/others/placenta_wgs.html)** <--

--> **[GRIMER report AMPLICON](https://pirovc.github.io/grimer-reports/others/placenta_amplicon.html)** <--

---

### Preterm Infant Resistome downloaded from [MicrobiomeDB](https://microbiomedb.org/mbio/app/record/dataset/DS_82fe0308e2) 

***original publication: [10.1038/nmicrobiol.2016.24](https://doi.org/10.1038/nmicrobiol.2016.24)***

--> **[GRIMER report](https://pirovc.github.io/grimer-reports/microbiomedb/ResistomeAmplicon.html)** <--

<details>
<summary>cmds</summary>
<pre>
# Download
wget https://microbiomedb.org/common/downloads/release-22/82fe0308e2032de2041694df6592ba542ea84b86/ResistomeAmplicon.16s_DADA2.taxon_abundance.biom
wget https://microbiomedb.org/common/downloads/release-22/82fe0308e2032de2041694df6592ba542ea84b86/ResistomeAmplicon.16s_DADA2.sample_details.tsv
# Run
grimer -c grimer/config/default.yaml -i ResistomeAmplicon.16s_DADA2.taxon_abundance.biom -m ResistomeAmplicon.16s_DADA2.sample_details.tsv -d -g -t ncbi -r superkingdom phylum class order family genus species --title "MicrobiomeDB Preterm Infant Resistome (V4)" -o ResistomeAmplicon.html
</pre>
</details>

---

### Antibiotic induced changes in the microbiota disrupt redox dynamics in the gut downloaded from [MGnify](https://www.ebi.ac.uk/metagenomics/studies/MGYS00005180)

***original publication [10.7554/elife.35987](https://doi.org/10.7554/elife.35987)***

--> **[GRIMER report](https://pirovc.github.io/grimer-reports/mgnify/MGYS00005180.html)** <--

<details>
<summary>cmds</summary>
<pre>
# Download and run
./grimer-mgnify.py -i MGYS00005180 -o MGYS00005180 -g "-d -g" 
</pre>
</details>
