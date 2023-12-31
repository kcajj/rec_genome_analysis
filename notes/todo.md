- [ ] phage isolates
    - [ ] build pipeline
        - [x] assembly
        - [ ] rename of the assemblies (i renamed them by hand)
        - [x] map reads on assembly
        - [x] map references on assembly
        - [x] map references on references
        - [x] map assemblies on assemblies (analysis on evolution of each phage)
            (the assemblies need to be renamed or else they are all named contig_1, i renamed them by hand)
    - [ ] build plotting scipt
        - [x] mutation density between assembly and references
        - [x] mutation density between references
        - [ ] integrate the script in the pipeline (take in input the folders)
- [ ] phage populations
    - [x] run evo genome analysis on the three references
    - [x] run evo genome analysis on the assembled recombinant genomes
- [ ] look into the results
    - [ ] secondary mappings in correspondance of the gap
- [ ] improve the results
    - [x] correct the recombinant assemblies by hand
    - [ ] make dot_plot-mutation_density_between_references-coverage_of_population_on_reference plot in the evo-genome-analysis pipeline
        - [x] duplicate and modify the coverage plot of evo-genome-analysis
        - [x] write the script to build the dotplot
        - [x] copy the code to plot the mutation density between references
        - [x] plot the three plots on on top of the other
        - [ ] insert this plot in the pipeline
        - [ ] correct the title of the dotplot
    - [x] look at reads stats, filter reads by length
        <pre>
        more or less half of the reads are above 2500
        between 10 to 20 % of reads are below 500. we can use it as a threshold.
        i did used some bash commands to filter out short reads
        timepoints=("1" "3" "5" "7")
        for t in "${timepoints[@]}"
        do
        seqkit seq -m 1000 P2_$t.fastq.gz > P2_$t.fastq
        done
        both for P2 and P3
        then i gzip the files
        for t in "${timepoints[@]}"
        do
        gzip P2_$t.fastq
        done
        </pre>
    - [x] sweep minimap parameters
        - [x] asm-5
        - [x] -M
        doesn't work
    - [x] msa alignment stats
        - [x] phage isolates
            - [x] msa with mafft
            - [x] extract stats and plot
        - [x] long reads
            - [x] extract long reads (doesn't work)
                - [x] select the reads by looking at population alignment data
                - [x] select the reads having the best mapping
            - [x] save the best reads in individual files
            - [x] msa with mafft
            - [x] plot
    - [ ] 