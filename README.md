# TumorClassifier

ELEC0134 project at UCL for classifying brain scans and their corresponding tumor diagnoses.

## Coverage:

Developed and executed on cloud VPC

Instance details:

- Julia v1.6 binaries
- Intel XEON CPU E5-2686 v4 @ 2.30GHz
	- 8 vCPU
	- 16 GB memory / vCPU
- NVIDIA Tesla V100-SXM2 16GB (used for prototyping)
	- CUDA version 11.2
	- Driver version 460.73.01

## Contents:

1. Main program: `src/TumorClassifier.jl`
2. Data pipelines and wrangling: `src/wrangling.jl`
   - exports module: `Data`
3. Classifier: `src/`
   1. Support vector machine: `src/svc.jl`
      - exports module: `SVC`
   2. Convolutional neural network: `src/cnn.jl`
      - exports module: `CNN`
4. Visualization: `src/viz.jl`

## Usage

To use this package, open a julia REPL at source root, the run:

```julia
julia> ]
(@v1.6) Pkg> activate .
julia> include("src/TumorClassifier.jl")
```

after which you will now have access to all defintions, function and local memory data under the `TumorClassifier` module.
You can call functions, such as `TumorClassifier.CNN.trainClass(; kwargs...)` to train an LeNet5 CNN or `TumorClassifier.SVC.trainEval(...)` to train and evaluate an SVC model.

## Dependencies:

See `Project.toml` and `Manifest.toml` for a detailed breakdown of libraries used and their recursive dependencies.

To intall all depencies automatically, open a julia REPL in the package source directory `TumorClassifier`, then run:

```julia
julia> ]
(@v1.6) Pkg> activate .
(TumorClassifier) Pkg> instantiate
```

## Data Set:

> Brain Tumor Classification (MRI)

Available at [this](https://www.kaggle.com/sartajbhuvaji/brain-tumor-classification-mri) link.
