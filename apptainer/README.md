 Building anTraX using apptainer
=================================

This is an [apptainer][APP] (aka singularity) definition file to build a container for using anTraX in HPC environments.

To build the container (typically a sif-file), run the following commands (Note: The definition file is expected to be in a subdirectory of the main anTraX repository, otherwise the build will fail likely fail.):

    cd /path/to/anTraX-src/apptainer
    (unset APPTAINER_BIND; apptainer build /path/to/container.sif antrax.def)

A [MATLAB compiler runtime 2019a][MCR] installation is expected to be mounted into the container under `/usr/local/MATLAB`. Install the MCR outside of the container, e.g. to "$HOME/MATLAB", then set an environment variable like this:

    export APPTAINER_BIND=$HOME/MATLAB:/usr/local/MATLAB

You can execute the generated sif file directly to run the application or use `apptainer run /path/to/container.sif`.

[APP]: https://apptainer.org/docs/user/main/introduction.html
[MCR]: https://www.mathworks.com/products/compiler/matlab-runtime.html
