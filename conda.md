Practical `conda`
===
#### Info
    conda -V
    conda info
    conda config [ --show [solver] ]
    conda config --show channels
    conda config --show channel_alias
    conda list [mamb]
#### Set
    conda config --set solver libmamba
    conda config --set default_channels []
    conda config --set notify_outdated_conda false
#### Update
    BAAAADDDDD conda update -y -c conda-forge --override-channels --update-deps conda -vv
