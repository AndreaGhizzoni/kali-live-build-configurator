# [Customizing Kali-Live Build](https://goo.gl/NpsSMK)

## Controlling the Packages Included in Your Build
The list of packages included in your build will be present in the respective 
`kali-$variant` directory:
```bash
cd kali-config/variant-$variant/package-lists/kali.list.chroot. 
```
By default, this list includes the `kali-linux-full` metapackage, as well as 
some others. These can be commented out and replaced with a manual list of 
packages to include in the ISO for greater granularity.

## Overlaying files in your build
You have the option to include additional files or scripts in your build by
overlaying them on the existing filesystem, inside the 
`includes.{chroot,binary,installer}` directories, respectively. For example, 
if we wanted to include our own custom script into the `/root/` directory of the
ISO (this would correspond to the “chroot” stage), then we would drop this 
script file in the `kali-config/common/includes.chroot/` directory before 
building the ISO.

# Building Kali with Different Desktop Environments
Since Kali 2.0, we now support built in configurations for various desktop
environments, including KDE, Gnome, E17, I3WM, LXDE, MATE and XFCE. To build any
of these, you would use syntax similar to the following:
```bash
# These are the different Desktop Environment build options:
#./build.sh --distribution kali-rolling --variant {gnome,kde,xfce,mate,e17,lxde,i3wm} --verbose

# To build a KDE ISO:
./build.sh --distribution kali-rolling --variant kde --verbose
# To build a MATE ISO:
./build.sh --distribution kali-rolling --variant mate --verbose

#...and so on.
```
