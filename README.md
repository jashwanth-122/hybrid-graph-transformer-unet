Hybrid Graph-Transformer U-Nets for Multi-Modality Medical Image Segmentation

Code for the IEEE ICHI paper "Hybrid Graph–Transformer U-Nets for Multi-Modality Medical Image Segmentation" (Jashwanth Alasyam, Bhuvan Tanneru, Muhammad Khan, Belinda Copus — University of Central Missouri).

We compare three bottlenecks inside the same 2D U-Net: a TransUNet-style transformer, a Graph U-Net with GraphSAGE message passing, and a hybrid that applies GraphSAGE layers before transformer attention. Experiments cover seven public datasets: ACDC, MS-CMRSeg, OCT cystoid fluid, DRISHTI-GS, chest X-ray (JSRT + PadChest), DRIVE, and panoramic dental radiographs.

Repository contents
hybrid_graph_transformer_unet.ipynb   Full pipeline: data loading, the three bottleneck models,
                                      training, evaluation (Dice, IoU, HD95, SSIM, ROC-AUC), and figures
requirements.txt                      Python packages
Setup
git clone https://github.com/jashwanth-122/hybrid-graph-transformer-unet.git
cd hybrid-graph-transformer-unet
pip install -r requirements.txt
Data

The datasets are not included in this repository. Download each one from its official source and place it under data/<dataset_name>/:

ACDC: https://www.creatis.insa-lyon.fr/Challenge/acdc/
MS-CMRSeg: https://zmiclab.github.io/zxh/0/mscmrseg19/
DRISHTI-GS: https://cvit.iiit.ac.in/projects/mip/drishti-gs/
DRIVE: https://drive.grand-challenge.org/
Chest X-ray (JSRT + PadChest subset): see Gaggion et al., IEEE TMI 2023
Dental: https://www.kaggle.com/datasets/humansintheloop/teeth-segmentation-on-dental-x-ray-images
OCT cystoid fluid: see Ahmed et al., Int. J. Imaging Syst. Technol. 2022
Running

Open hybrid_graph_transformer_unet.ipynb (Jupyter or Google Colab), set the dataset path, and run all cells. Set the bottleneck variable to transformer, graph, or hybrid to train each variant.

Results (held-out test Dice, %)
Method	ACDC	MS-CMRSeg	OCT	DRISHTI-GS	DRIVE	Chest X-ray	Dental
TransUNet variant	89.20	87.99	89.12	84.87	78.30	96.62	90.01
Graph U-Net variant	88.67	87.41	89.17	82.82	76.71	96.57	90.01
Hybrid (proposed)	89.99	87.85	89.95	85.04	77.74	96.71	90.11
