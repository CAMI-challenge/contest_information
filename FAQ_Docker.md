# FAQ for Docker-related questions

### My method works for fastq files, paired fastq files, and contig files, so should I use all of the corresponding variables, or just one?
All input will be available to the container with every call and the mode of operation should be determined by the container or run
command which is passed to the container. You can provide different tasks which do different things with the input. You should implement
those modes with your method which make sense and for produce good results.

### For the profiling Bioboxes interface, CONT_FASTQ_FILE_LISTING is a listing of files. How should the output in CONT_PROFILING_FILES
look like?
When there are multiple input files specified in the listing, you should create one output profile in valid bioboxes format for each
of the input files.

### Is the bioboxes profiling specification only for profiling of assembled data?
No, the specification is for both, unassembled reads and assembled data. But if you want to participate in the read-based profiling part,
you cannot use the contigs but have to take paired or unpaired reads as input (the corresponding contig variable might be empty or point
to an invalid/non-existing file).

### The docker variables in the provided template container are already initialized. How do I pass different values to the container?
Use

    docker -v variable=value
