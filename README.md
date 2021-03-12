# D-PPIN
D-PPIN is a dynamic network dataset, which consists of 12 different dynamic protein-protein interaction networks of yeast cells in 12 folders.

In each dynamic network of D-PPIN (e.g. Krogan_LCMS), the node represents a gene coding protein, the edge represents the protein-protein interaction at a certain timestamp, and each edge is timestamped like (node_u, node_v, timestamp, weight).

In each folder, "Dynamic_PPIN.txt" stores temporal edges at different timestamps, "Static_PPIN.txt" stores the original static network, and "Node_Features" records the temporal gene expression value of each protein and the format is "id, node, value_at_t_1, ..., value_at_t_36".

Plus, "Node_Labels.xlsx" stores labels (i.e., types) of 6,738 protein nodes, which covers each node of 12 generated dynamic protein-protein interaction networks. The label of each  protein is retrievaled from the [Saccharomyces Genome Database](https://www.yeastgenome.org/).

## Statistics of D-PPIN
The statistics of all 12 generated dynamic networks are shown in Table 1. 

<p align="center"> Table 1. Generated Dynamic Networks. </p>
<p align="center"> <img align="center" src="/data_stats.png" width="377" height="291"> </p>


## Generation of D-PPIN
In brief, two components are needed to construct a dynamic protein-protein interaction network. The first one is a static protein-protein interation network and the second one is the time-aware gene expression value series of each protein. Through the activity and co-expression analysis (as shown in Figure 1), a dynamic network is constructed.

![pic](/generation_process.png)
<p align="center"> Figure 1. Dynamic Protein Network Generation Process. </p>

The static networks for building D-PPIN are available at this [link](https://www.inetbio.org/yeastnet/downloadnetwork.php).

The yeast temporal gene expression value (GSE3431.txt) from the paper "Tu BP, Kudlicki A, Rowicka M, McKnight SL. Logic of the yeast metabolic cycle: temporal compartmentalization of cellular processes. Science 2005." is available at this [link](https://www.ncbi.nlm.nih.gov/geo/download/?acc=GSE3431).

The dynamic network construction method is mainly adopted from "Zhang, Yijia, Hongfei Lin, Zhihao Yang, Jian Wang, Yiwei Liu, and Shengtian Sang. A method for predicting protein complex in dynamic PPI networks. BMC bioinformatics 2016.", which is available at this [link](https://bmcbioinformatics.biomedcentral.com/articles/10.1186/s12859-016-1101-y).

## How to Run
The dynamic networks have already been constructed in each folder, users can directly use it. If you want to construct them again on your own and modify some parameters, just run main.py. The main.py program will analyze the GES3431 gene expression value and the static network in each folder to generate the corresponding dynamic network and store it in that folder.

The program is written under Python 3.7, and the prerequisites are listed below.
- numpy 1.20.1
- scipy 1.6.0
