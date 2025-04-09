# Running mice_microbes remotely on Google Colab
The simplest way to use mice_microbes is using this [colab notebook](https://github.com/luquelab/bioinformatics_mice_microbes/blob/main/notebooks/main_pipeline.ipynb)
which runs mice_microbes on a free Google cloud-based platform in a Jupyter environment. The Colab notebook is self documenting and is designed to be simple to use. 
Example sequences to reproduce the outputs in the /docs/tutorial/ can be found in /examples/

## Colab quick-start guide
Follow the steps described below to obtain sequence information on sequences of interest. To help navigate the guide, we recommend displaying the Colab notebook's Table of contents (open the `View` menu on the top bar and choose `Table of contents`):
1. Upload the list of sequences to be analyzed in the Colab /content folder as "sequences.fna"
2. Execute the rest of the notebook by navigating the Colab menu `Runtime` and choosing the option `Run all` or `Run after`. This will run the pipeline and generate and store the results.
  + The execution time and maximum size and number of sequences on the computing power and memory of the Colab cloud service used, which depends on the user's Colab plan.
4. The outputs should write automatically to your /content/ folder in Colab, which can then be downloaded manually to your system.
