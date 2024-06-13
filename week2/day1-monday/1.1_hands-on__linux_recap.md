# 2024 IGS Summer School in Berlin: Linux Recap

## Overview
* Allocated time: 45 min

## Learning Objectives
* Recap the most important `bash` commands that are essential for using the command line in Bioinformatics. 

## Exercises

### Name to be found
0. Create a new directory named `data` inside the `day1` directory, which is located in the `$HOME/suschool24` path. Change your current working directory to the newly created `data` directory.

1. Please download the `fastq` file from . 
    <details>
    <summary>Oops...</summary>
    ... you accidently messed up the download. There is already a <code>data</code> directory in <code>$HOME/suschool24</code>. You need to move the SarS-CoV-2 file to  <code>$HOME/suschool24/data</code>.
 
    1.1 Create a new directory named <code>SC2</code> inside the <code>$HOME/suschool24/data</code> directory.

    
    1.2 Move the file <code>SC2_SRR12132977.fastq.gz</code> to the newly created <code>SC2</code> directory.

    1.3 Delete the <code>data</code> directory inside <code>$HOME/suschool24/day1</code>
    </details>

2. How large is `SC2_SRR12132977.fastq.gz`? Inspect the first 4 lines of this `fastq` file without decompressing. Explain the structure of a `fastq` file entry.

3. Make a copy of that file. Open the copied file and rename the first sequence identifier to an arbritrary name. Verify the changes by printing the head of both the original and the modified files to the command line. 

4. Report the number of sequences in one of the files.

5. Document your previous command by 