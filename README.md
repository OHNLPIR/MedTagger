# Introduction

MedTagger contains a suite of programs that the Mayo Clinic NLP program has developed in the past three years.
It includes three major components: MedTagger for indexing based on dictionaries, MedTaggerIE for
information extraction based on patterns, and MedTaggerML for machine learning-based named entity recognition.

# Sub Directories

- `javasrc` - source folder includes java source codes distributed
- `autosrc` - source folder automatically generated by JCas_gen for the centralized type system
- `descsrc` - source folder contains types and primitive analysis engines, collection readers, and cas consumers (not recommended to modify if you have limited knowledge with respect to UIMA)
- `desc` - example descriptors for aggregate analysis engines and collection processing engines
- `docs` - documentation as a background for the MedTagger suite
- `lib` - a collection of libraries that MedTagger is based on
- `resources` - resources required to run MedTagger
- `testdata` - shipped test data to run all annotators

# Installation and Execution

To install, download distribution and unzip the package

To execute MedTagger for a collection of documents, simply go to MedTagger installation home
and run runMedTaggerCVD.bat (runMedTaggerCVD.sh) or runMedTaggerCPE.bat (runMedTaggerCPE.sh)
 which will test processable analysis engines and collection processing engines.

In Windows:
```
java -Xms512M -Xmx2000M -cp resources;desc;descsrc;MedTagger-1.0.1.jar org.apache.uima.tools.cvd.CVD
```
or
```
java -Xms512M -Xmx2000M -cp resources;desc;descsrc;MedTagger-1.0.1.jar org.apache.uima.tools.cpm.CpmFrame
```

In Unix/Linux:
```
java -Xms512M -Xmx2000M -cp resources:desc:descsrc:MedTagger-1.0.1.jar org.apache.uima.tools.cvd.CVD
```
or
```
java -Xms512M -Xmx2000M -cp resources:desc:descsrc:MedTagger-1.0.1.jar org.apache.uima.tools.cpm.CpmFrame
```

It will fire up UIMA Cas Visual Debugger (CVD) or the collection processing engine (CPE) GUI.

To visualize a specific aggregate engine through CVD
- Go to load AE under the Run menu
- Choose `$MedTaggerHOME/desc/medtaggerdesc/aggregate_analysis_engine`

To process a collection of documents, go to the FILE menu and open the corresponding CPE descriptor file
available in `$MedTaggerHOME/desc/`

E.G., to index clinical concepts for clinical reports stored in a directory of your choice, use
`$MedTaggerHOME/desc/medtaggerdesc/collection_processing_engine/MedTaggerCPE.xml`
