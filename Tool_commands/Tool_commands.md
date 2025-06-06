# Phyloflash
```phyloFlash.pl -dbhome /path/to/database -lib ${input_fastq1}_phyloflash -read1 ${input_fastq1} -read2 ${input_fastq2} -readlength 150```

# MAFFT
```mafft --localpair --maxiterate 1000 $in_fasta > ${outdir}/${in_fasta##*/}_aligned```

# trimal
```trimal -in  ${outdir}/${in_fasta##*/}_aligned -out ${outdir}/${in_fasta##*/}_trimmed -automated1```

# IQ-TREE2 chosen model
```iqtree2 -s ${outdir}/${in_fasta##*/}_aligned -bb 1000 -T 64 -m ${model}```

# IQ-TREE2 modelfinder
```iqtree2 -s ${outdir}/${in_fasta##*/}_aligned -bb 1000 -T 64 ```

# EggNOG
```emapper.py -m mmseqs --mmseqs_db ${eggNOG_mmseq_bacterial_database} --data_dir ${EggNOG_diamond_database} -i ${input_genome} --itype genome -o ${outputfile} --cpu 32```
