![Alvis](alvis_logo.svg)
# Batch Connect - Alvis OnDemand RStudio

Interactive App Plugin for running RStudio Server at [Alvis OnDemand](https://portal.c3se.chalmers.se).

This app was inspired by the [OSC RStudio Server App](https://github.com/OSC/bc_osc_rstudio_server).

## Prerequisites

This app is developed for Alvis OnDemand and relies on (albeit few) custom data
structures (e.g. `<%= SlurmData... %>` as seen in `form.yml.erb`). These local
additions has not yet been accepted upstream and is likely not available in
your OOD instance. If you are interested in these changes please contact the
Alvis team at support@c3se.chalmers.se.

Tested with:
* Singularity 3.8.7-1.el8
* RStudio Server >= 4.1.3

For running in debug mode you need `lsof` installed.

## Install
The app itself is pretty much self-contained and should only need to be placed
as e.g. `/var/www/ood/apps/sys/bc_alvis_rstudio`.

```
$ cd /var/www/ood/apps/sys/
$ git clone https://github.com/c3se/bc_alvis_rstudio.git
```

You will need to make the script `rstudio-server-auth` available for RStudio
Server instances as it is used for authentication. At Alvis it is placed on a
shared filesystem.

## Customizations
You can customize which RStudio Server container is used by creating `~/bc_alvis_rstudio.env`.
```
# Use a custom RStudio Server singularity image
export RSTUDIO_SERVER_IMAGE=$HOME/my_rstudio_server.sif
```

## Debugging
RStudio logs gets written to default location `$HOME/.local/share/rstudio/`.

## License
RStudio is a registered trademark of
[RStudio](https://www.rstudio.com/about/trademark/). The RStudio logo usage
adhears to the [RStudio Logo Guidelines](https://www.rstudio.com/about/logos/).
