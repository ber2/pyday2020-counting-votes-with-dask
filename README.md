# Counting votes with Dask

Notebooks and code for my talk at the [Barcelona PyDay](https://pybcn.org/events/pyday_bcn/pyday_bcn_2020/), December 12th, 2020.

The topic of the talk is how Dask does an excellent job at analyzing datasets that do not fit on
single-machine memory while introducing little overhead and staying in the single-machine context.
We have shown an example built around counting votes in order to find out the winner of an election.

__Disclaimer__: all of the data shown in the talk has been artificially generated and any
relationship between the election example portrayed in the talk and recent events in a faraway
country is pure coincidence.

## Regarding Dask

[Dask](https://dask.org/) is a project with excellent [documentation](https://docs.dask.org/en/latest/). Since we have focused on a simple use case for the
purpose of the talk, many of the nuances about how Dask works have only been sketched.

If you wish to play more with it, I highly recommend checking the documentation. The section on [use cases](https://stories.dask.org/en/latest/) is a good showcase of what is possible.

In particular, Dask can be set up either on a single machine or on a cluster. We have focused on the
first case and have used the [Dask JupyterLab Extension](https://github.com/dask/dask-labextension) for the management of the scheduler. I recommend checking the documentation on the [single-machine scheduler](https://docs.dask.org/en/latest/setup/single-machine.html) for more details on ways to configure a single-machine cluster.

## Video for the talk

The talk will be published in the [PyBCN Youtube channel](https://www.youtube.com/channel/UCEhI2CfdT5--TYq47K4en4A). A more precise link will be made available after the event.

## Slides for the talk

I used beautiful.ai to craft the slides; they are available [here](https://www.beautiful.ai/player/-MO5OSZEML6fSM-KYecq). 


# Doing this at home

## Data for the examples

Since the data for the examples is artificially generated, I have deemed it unnecessary to publish a
dataset weighing a few gigabytes with zero interest beyond this talk.

Instead, I have made the code that generates the dataset available. Please have a look and feel free
to use it in order to generate data for your own purposes:

- [ber2/pyday2020-generate](https://github.com/ber2/pyday2020-generate)
## Installing Dask and the JupyterLab extension

### On conda

As explained during the talk, Dask ships with anaconda. In order to replicate the setup in the talk,
first install JupyterLab:
```bash
conda install jupyterlab nodejs
```
Then, install the Dask lab extension:
```bash
conda install -c conda-forge dask-labextension
```
Finally, build the extension
```bash
jupyter labextension install dask-labextension
jupyter serverextension enable dask_labextension
```

### Using poetry

I have provided the bare minimum necessary to run the examples on a fresh Python 3.8 virtual
environment using [pyenv](https://github.com/pyenv/pyenv) and [poetry](https://python-poetry.org/).

If you have these tools installed, set up a virtual env running Python 3.8 and, on the root of this
repository, execute the following:
```bash
pip update -U pip
poetry install
jupyter labextension install dask-labextension
jupyter serverextension enable dask_labextension
```

## Notebooks

They are the four `ipynb` files at the root of this repository, and they are numbered according to
their exposition order.
- [1_one_file.ipynb](1_one_file.ipynb)
- [2_find_out_winner.ipynb](2_find_out_winner.ipynb)
- [3_stop_the_count.ipynb](3_stop_the_count.ipynb)
- [4_voting_twice.ipynb](4_voting_twice.ipynb)

