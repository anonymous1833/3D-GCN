# 3D-GCN
This is the data and code for submission#683.

## Dataset

Our dataset is from the [NYC Bike](https://www.citibikenyc.com/system-data). We obtained road network and 9 categories of PoIs from [OpenStreatMap](https://www.openstreetmap.org/#map=4/36.96/104.17). We devided the city into 82 irregular regions, based on road network. ![image](https://github.com/anonymous1833/3D-GCN/blob/master/ny_region.png)

The dataset contains 2208 time intervals, spanning from Jul. 1st to Sept. 30th, 2017 (92 days, 24 intervals per day). You can download the dataset via following links:
[Jul, 2017](https://s3.amazonaws.com/tripdata/201707-citibike-tripdata.csv.zip)
[Aug, 2017](https://s3.amazonaws.com/tripdata/201708-citibike-tripdata.csv.zip)
[Sept, 2017](https://s3.amazonaws.com/tripdata/201709-citibike-tripdata.csv.zip)

## Requirements

- python 2.7
- PyTorch 0.2.0
- NumPy
- JSON

## Project Structure

- /data
  - flow_bike_nyc_irregular.json contains the inflows, outflows obtained from the dataset
  - irregular_feature.npy is the poi features of all regions ![](http://latex.codecogs.com/gif.latex?\\bm{F})
  - irregular_idx.npy is the index of labeled regions ![](http://latex.codecogs.com/gif.latex?\\mathcal{V}_L)
  - irregular_label.npy is the labels of all regions ![](http://latex.codecogs.com/gif.latex?\\bm{\\Omega})
  - irregular_weight.npy is the normalization term ![](http://latex.codecogs.com/gif.latex?\\frac{1}{|\\mathcal{V}_L^{\\Omega_i}|})
  - irregular_path.npy contains the historical OD flows for the irregular dataset
- /code
  - main.py ***run this file to get the results of 3D-GCN in our paper***
  - gcn.py is the implementation of our neural network
  - dataset.py loads the dataset

## Usage

> python main.py
