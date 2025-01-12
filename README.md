# RTS_ComponentLevel

## This GitHub repository contains the following:
 - The Bash script file (file name is: downloadJava8.sh) we used to:
    - Download, compile, and run the test cases for all 1,200 revisions of the 12 subjects used in our experiments.
    - Integrate the RTS tools Ekstazi and STARTS plugins to each revision and run these RTS tools and store their output.
    - Run JDeps tool to extract the class-level dependencies on each of the 1,200 revisions.  
 - The dataset: the dataset includes the ACDC-recovered architectures for all 1,200 revisions of the 12 Java projects used in the experimental evaluation. Each project is associated with a copressed directory (i.e., a zip file) containing architecture files for its revisions. These files provide detailed information about components, the classes within each component, and the static dependencies among classes. Each revision's files are labeled with the corresponding SHA identifier, enabling users to retrieve the specific source code revision from the project's GitHub repository. Below we provide detailed description for the dataset contents.

## The dataset:

In this repository, each subject has a corresponding directory (compressed as a `.zip` file) containing architectural files for 100 revisions of that subject. The files for each individual revision are labeled with the revision’s SHA identifier, which can be used to retrieve the source code of that specific revision from the project's GitHub repository.

We used the **ARCADE framework** to recover the ACDC components for each revision of a subject. For each revision, ARCADE generates three types of output files, named as follows:
1. `acdc_clustered.rsf`
2. `acdc_smells.ser`
3. `deps.rsf`

To differentiate the files, we concatenate the subject name and the revision’s SHA identifier with each filename. For example, for the revision `a189697fe51f4d304b8999886dc7a22281cd470e` of the `commons-compress` subject, the following files are generated:
1. `commons-compressV0_a189697fe51f4d304b8999886dc7a22281cd470e_acdc_clustered.rsf`
2. `commons-compressV0_a189697fe51f4d304b8999886dc7a22281cd470e_acdc_smells.ser`
3. `commons-compressV0_a189697fe51f4d304b8999886dc7a22281cd470e_deps.rsf`

### File Descriptions
- **`*_acdc_clustered.rsf`**: Contains recovered components and their corresponding classes. Each line in this file represents a class-to-component relationship in the format of `entity-cluster`.
- **`*_acdc_smells.ser`**: Serialized XML-like file listing dependency-based and concern-based architectural smells.
- **`*_deps.rsf`**: Contains the class-level dependencies.

## Reference to ARCADE Framework
The architectural recovery was conducted using the ARCADE framework, as detailed in the following reference:

> Schmitt Laser, Marcelo, Nenad Medvidovic, Duc Minh Le, and Joshua Garcia.  
> "ARCADE: An extensible workbench for architecture recovery, change, and decay evaluation."  
> *Proceedings of the 28th ACM Joint Meeting on European Software Engineering Conference and Symposium on the Foundations of Software Engineering*, pp. 1546-1550, 2020.

