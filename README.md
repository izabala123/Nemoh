<!--
  Title: Nemoh v115
  Description: NEMOH is the first open source Boundary Element Method (BEM) code. This repository includes v115 source and binaries.
  -->
  
# Nemoh v115 64 bits
**NEMOH is the first open source Boundary Element Method (BEM) code.  
This repository includes v115 source and binaries compiled in 64 bits able to process >12000 panel meshes**

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)


[NEMOH](https://lheea.ec-nantes.fr/logiciels-et-brevets/nemoh-presentation-192863.kjsp) is a [Boundary Element Method (BEM)](https://en.wikipedia.org/wiki/Boundary_element_method) code dedicated to the computation of first order wave loads on offshore structures (added mass, radiation damping, diffraction forces). It has been developed by researchers at [École Centrale de Nantes](https://www.ec-nantes.fr/) for 30 years. Typical use is estimation of dynamic response of floating structures or performance assessment of wave energy converters.

NEMOH is the world first open source BEM code. Since January 2014, it has been released under the terms of the Apache 2 licence. Copy of the license may be obtained at http://www.apache.org/licenses/LICENSE-2.0. All the original documentation can be got from [NEMOH Installation](https://lheea.ec-nantes.fr/logiciels-et-brevets/nemoh-presentation-192863.kjsp).

This repository includes NEMOH v115 source and binaries. These sources have been got from the [public LHEEA Mercurial repository](http://130.66.47.2/cgi-bin/hgweb.cgi/nemoh/) that holds until version v118. The latest version that generates valid executables is the v115, and it has been shown that the improvements over the [public v113 executables](https://box.lheea.ec-nantes.fr/index.php/s/6MybIloTDqWSFDL) are so significant, that it worths to create this fork providing them to the offshore researchers community.

The Windows binaries run almost out-of-the-box, as the Intel version requires to install previously the [Redistributable Libraries for Intel® Fortran 2019 Compiler for Windows](https://software.intel.com/content/www/us/en/develop/articles/redistributable-libraries-for-intel-c-and-fortran-2019-compilers-for-windows.html), from [here](http://registrationcenter-download.intel.com/akdlm/irc_nas/tec/15799/ww_ifort_redist_msi_2019.5.281.zip). Please install the 64 bits version.

Some changes have been made to the original files:
- Binaries 'preprocessor', 'solver' and 'postprocessor', have been joined into a single 'nemoh' binary. See instructions below
- Removed id.dat file, and added estimated time (ET) after each problem solving
- Added [Code::Blocks](http://cbfortran.sourceforge.net/) .cbp and [Visual Studio](https://visualstudio.microsoft.com/) .sln project files to compile it using [GNU Fortran](https://gcc.gnu.org/fortran/) and [Intel Fortran](https://software.intel.com/en-us/fortran-compilers)
- 64 bits binaries included capable of solving meshes of >12000 panels
- Included DeepCWind offshore wind platform example

 'Nemoh' binary options:
   - -h             Shows this help
   - -pre -preprocessor  Runs the preprocessor
   - -solver        Runs the solver
   - -post -postprocessor Runs the postprocessor
   - -all           Runs preprocessor, solver and postprocessor

DeepCWind offshore wind platform example plots from v113 and v115:

<p align="center"><img src="https://github.com/izabala123/Nemoh/blob/master/other/md%20resources/Aheave.jpg" width="800" title="Heave added mass"></p>

<p align="center"><img src="https://github.com/izabala123/Nemoh/blob/master/other/md%20resources/Bheave.jpg" width="800" title="Heave damping"></p>

As long simulations may be rather slow, it is adviced in this case to use [BEMRosetta](https://github.com/izabala123/BEMRosetta) NEMOH launcher to parallelize simulations.

The purpose of this project is solely to make available to the community a set of ready to use binaries and sources with the best known version of NEMOH. It is expected that in the near future this project will be overtaken by the blazing fast [Capytaine](https://github.com/mancellin/capytaine) solver developed by [Matthieu Ancellin](https://ancell.in/).
