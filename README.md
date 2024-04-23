# Modernizing gravity processing: use the gravity disturbance

Santiago Soler

_University of British Columbia_

## Information

| Information |                                        |
| ----------- | -------------------------------------- |
| When        | April 23, 2024                         |
| DOI         | [10.6084/m9.figshare.25676571][slides] |

## About

I got invited by Dr. [Jiajia Sun][jiajia] from [University of Houston][houston]
to give a talk about potential fields and available open-source tools for
processing them to their potential field undergrad class students.

## Setup

During this talk we'll use [Juptyer notebooks][jupyter] to perform some gravity
processing.

To be able to follow the live coding and run these notebooks, you'll need to
have access to a Python environment. This could be done through **online
services** like [Google Colab][colab], or through a **local Python
installation** like [Anaconda][anaconda] or [Miniforge][miniforge].

Here will provide instructions to:

- [Configure Google Colab](#configure-google-colab)
- or [Install Python locally](#install-python-locally)


### Configure Google Colab

To be able to run the Jupyter notebooks for this tutorial in Google Colab,
we'll need to follow these steps:

1. Login to our Google Colab account.
1. Create a new notebook.
1. Install `conda` in Google Colab using [`condacolab`][condacolab]
1. Install some Python libraries that we'll need to use, such as
   [harmonica][harmonica].

#### Step 1: Login to our Google Colab account

If you don't have a Google account, create one and log in. If you do, you just
need to log in.

#### Step 2: Create a new notebook

1. Access to Google Colab by going to: https://colab.research.google.com
1. Find the top menu and choose `File` > `New notebook`. A new tab should open
   with a blank notebook in it.

#### Step 3: Install `conda` in Colab

Paste this to **the first cell in the notebook**:

> [!IMPORTANT]
> These lines should be in the very first cell of the notebook. Otherwise, the
> installation will fail.

```
!pip install -q condacolab
import condacolab
condacolab.install()
```

Run the cell, wait until the kernel is restarted, and then follow to the next
step.

#### Step 4: Install some Python libraries

To be able to run the notebook we need to install some Python libraries
that aren't preinstalled in the default Google Colab environment.

1. Add a new cell (below the one you used to install `conda`)
1. Install some packages using `conda` by pasting this content in the cell and
   running it:
   ```
   !conda install harmonica boule ensaio pygmt pyproj
   ```

> [!IMPORTANT]
> Every time you open a notebook in Colab or create a new one, you'll have to
> reinstall `conda` and these packages (Google Colab don't save installed
> states across notebooks).
>
> If it's a new notebook, just follow the previous instructions from the top.
>
> If it's an existing notebook, make sure that it has the two cells described
> in this and in the previous step, and run them.

### Install Python locally

To be able to run the Jupyter notebooks for this tutorial in our own machines,
we'll have to follow these steps:

1. Install a Python distribution (like [Anaconda][anaconda] or
   [miniforge][miniforge]).
1. Create a [_conda environment_][conda-environ] with all the Python packages
   needed.
1. Activate this conda environment and run [Jupyter][jupyter] to start
   coding.

#### Step 1: Install a Python distribution

We recommend installing a Python distribution like [miniforge][miniforge] or
[Anaconda][anaconda].

Both of them will install Python and a package manager that allows us to
install new Python libraries, and also create _environments_.

- Install miniforge: https://github.com/conda-forge/miniforge#install
- Install Anaconda: https://docs.anaconda.com/anaconda/install

#### Step 2: Create the `2024-uh` conda environment

1. Download the [`environment.yml`][environment_yml] file from
   (right-click and select "Save page as" or similar).
1. Make sure that the file is called `environment.yml`.
   Windows sometimes adds a `.txt` to the end, which you should remove.
1. Open a terminal (_Anaconda Prompt_ or _Miniforge Prompt_ if you are running
   Windows). The following steps should be done in the terminal.
1. Navigate to the folder that has the downloaded environment file
   (if you don't know how to do this, take a moment to read [the Software
   Carpentry lesson on the Unix shell][shell-novice]).
1. Create the conda environment by running `conda env create --file
   environment.yml` (this will download and install all of the packages used in
   the tutorial).

#### Step 3: Activate the `2024-uh` environment and start Jupyter

> [!TIP]
> You'll need a browser that is able to run Jupyter (basically anyone except
> Internet Explorer or Edge). If you are in Windows, make sure you change your
> default browser to a different one.

Now we can activate the newly created `2024-uh` environment.

1. Open a terminal (_Anaconda Prompt_ or _Miniforge Prompt_ if you are running
   Windows).
1. Activate the `2024-uh` environment by running
  `conda activate 2024-uh`.
1. With the `2024-uh` environment activated, we can start Jupyter
   by running `jupyter notebook` in the terminal. A new tab in our web browser
   should open showing Jupyter's interface.


## License

This work is licensed under a
[Creative Commons Attribution 4.0 International License][cc-by].

[![CC BY 4.0][cc-by-image]][cc-by]


[cc-by]: http://creativecommons.org/licenses/by/4.0/
[cc-by-image]: https://i.creativecommons.org/l/by/4.0/88x31.png
[jiajia]: https://www.uh.edu/nsm/earth-atmospheric/people/faculty/jiajia-sun/
[houston]: https://www.uh.edu/nsm/earth-atmospheric/
[slides]: https://doi.org/10.6084/m9.figshare.25676571
[colab]: https://colab.research.google.com
[condacolab]: https://github.com/conda-incubator/condacolab
[environment_yml]: https://raw.githubusercontent.com/santisoler/2024-uh/main/environment.yml
[jupyter]: https://jupyter.org/
[shell-novice]: http://swcarpentry.github.io/shell-novice
[anaconda]: https://www.anaconda.com/download
[miniforge]: https://github.com/conda-forge/miniforge
[conda-environ]: https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html
