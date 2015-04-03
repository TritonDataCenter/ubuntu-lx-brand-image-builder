# Ubuntu lx-brand Image Builder

This is a collection of scripts used for creating an lx-brand Ubuntu image.

## Requirements

In order to use these scripts you'll need:

- Ubuntu (or Debian) running in a VM or bare metal (required for the `install` script)
- debootstrap: `apt-get install -y debootstrap`
- A SmartOS (or SDC headnode) install (required for the `create-lx-image` script)


## Usage

1. Run `./install -d <chroot> -m <mirror> -i <image name> -p <proper name> -u <image docs>` under Ubuntu to install Ubuntu 14.04 in a given directory. This will create a tarball of the installation in your working directory (named `<image name>-<YYMMDD>.tar.gz`). See `./install -h` for detailed usage
2. Copy the tarball to a SmartOS machine or SDC headnode and run `./create-lx-image -t /full/path/to/<image name>-<YYMMDD>.tar.gz` (substituting the name of your tar file). This will create the image file and manifest.
