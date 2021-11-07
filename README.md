# Training Data Reduction for Performance Models of Data Analytics Jobs in the Cloud

## Repository Content

- The [C3O runtime predictor](/RuntimePrediction)
- The [C3O cluster configurator](/ClusterConfiguration) as a prototype
- The [Spark jobs runtime data](/data) which originates from a [previous paper](https://github.com/dos-group/c3o-experiments)
- An [evaluation of the C3O runtime predictor](/evaluation) with the cluster analysis methods (K-Means, K-Medoids & DBSCAN)

## Evaluation of the C3O runtime predictor after reducing the runtime data

- The runtime data were reduced using cluster analysis methods (K-Means, K-Medoids & DBSCAN)
- There are three evaluations with the results after the compression:
  /evaluation/training_data_compression_dbscan.ipynb
  /evaluation/training_data_compression_kmeans.ipynb
  /evaluation/training_data_compression_kmedoids.ipynb
- The running time of the C3O runtime predictor was also measured during training (/evaluation/time_tracking.pdf)

### Dependencies

- Python >= 3.6
- Libraries: [scipy](https://pypi.org/project/scipy/), [scikit-learn](https://pypi.org/project/scikit-learn/), [numpy](https://pypi.org/project/numpy/), [pandas](https://pypi.org/project/pandas/)


### Testing the prototype

The prototype can be tested by executing `c3o.py`.  
The file `c3o_cc_examples.sh` contains usage examples. On systems that have [bash](https://en.wikipedia.org/wiki/Bash_\(Unix_shell\)), it can be executed directly after making it executable.


### Example Execution

```
$ python c3o.py 'Page Rank' 330 2000000 3000000 0.0007

Configuring cluster to execute a Page Rank job in 330s with a confidence of 0.95
Execution context for Page Rank:
    links: 2000000
    pages: 3000000
    convergence_criterion: 0.0007
Estimated mean runtime prediction error: 0.69s, standard deviation: 12.99s
Required tolerance to reach the deadline in 95.0% of cases: 22.06s
Estimated optimal cluster configuration: 6 x r4.2xlarge with estimated runtime: 299.66s
```
