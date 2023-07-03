# Quantifying Plankton Populations in the Baltic Sea
### Utilizing Deep Learning Models to produce gap-free satellite images and perform predictions of the chlorophyll-a concentration in the Baltic Sea.

This repository hold the code for the Master thesis project of Nina Oehlckers.

The project aims to assess the usability of deep learning models to predict plankton populations in the Baltic Sea by training deep learning models on data derived from satellite imagery as well as oceanographic parameters. In order to do so, the goal is to first apply a deep learning model to fill gaps in the satellite-derived data that can be used as the input to the predicting deep learning model. The result will be evaluated in comparison to the existing numerical model predictions as a baseline and in-situ data as ground-truth.

The gap filling part of the project is based on the models DINCAE by Barth et al. (Code: https://github.com/gher-ulg/DINCAE.jl, Paper: https://doi.org/10.5194/gmd-15-2183-2022) and STpConv3D by Appel (Code: https://github.com/appelmar/STpconv, Paper: https://arxiv.org/abs/2208.08781), appending these models to fit the requirements of the project. The code for these models is saved in the folder "11_DINCAE_python", "12_DINpCAE_python" and "13_pCONV3D". 

The prediction filling part of the project utilizes ConvLSTM layers as well as Sa-ConvLSTM layers as presented by Lin et al. (Code: https://github.com/MahatmaSun1/SaConvSLTM/blob/041ecb020d151a21b4a1c3426c2e4e56269c5bff/SaConvSLTM/SaConvLSTM.py, Paper: https://ojs.aaai.org//index.php/AAAI/article/view/6819)

In the two step approach that is suggested in this study, the data is first gap-filled and the performance of the gap filling models are analysed and compared. Afterwards the gap-filled data is used for the predictions. 