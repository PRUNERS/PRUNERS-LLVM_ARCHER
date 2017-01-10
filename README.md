<div id="table-of-contents">
<h2>Table of Contents</h2>
<div id="text-table-of-contents">
<ul>
<li><a href="#sec-1">1. License</a></li>
<li><a href="#sec-2">2. Introduction</a></li>
<li><a href="#sec-3">3. Prerequisites</a></li>
<li><a href="#sec-4">4. Installation</a>
<ul>
<li><a href="#sec-4-1">4.1. Automatic Building</a></li>
</ul>
</li>
<li><a href="#sec-5">5. Sponsors</a></li>
</ul>
</div>
</div>


# License<a id="sec-1" name="sec-1"></a>

Please see LICENSE for usage terms.

# Introduction<a id="sec-2" name="sec-2"></a>

<img src="resources/images/archer_logo.png" hspace="5" vspace="5" height="45%" width="45%" alt="Archer Logo" title="Archer" align="right" />

**Archer** is a data race detector for OpenMP programs.


Archer combines static and dynamic techniques to identify data races
in large OpenMP applications, leading to low runtime and memory
overheads, while still offering high accuracy and precision. It builds
on open-source tools infrastructure such as LLVM and ThreadSanitizer
to provide portability.

# Prerequisites<a id="sec-3" name="sec-3"></a>

To compile Archer you need an host GCC version >= 4.7 and a CMake
version >= 3.0.

Ninja build system is preferred. For more information how to obtain
Ninja visit <https://martine.github.io/ninja/>.

# Installation<a id="sec-4" name="sec-4"></a>

Archer has been developed under LLVM 3.8 (for
more information visit <http://llvm.org>).

## Automatic Building<a id="sec-4-1" name="sec-4-1"></a>

Archer comes as an LLVM tool, in order to compile it we must compile
the entire LLVM/Clang infrastructure. Archer developers provide a
patched LLVM/Clang version based on the main LLVM/Clang trunk.

In order to obtain and build LLVM/Clang with Archer execute the
following commands in your command-line (instructions are based on
bash shell, GCC-4.9.3 version and Ninja build system).

Build Archer by running `install.sh`:

    ./install.sh --prefix=llvm_install_path [default: --prefix=/usr]

The installation script will create a folder called **LLVM** at the same
level of the Archer directory and install LLVM to *llvm_install_path*.

In case your GCC is not installed in a standard path you need to
specify the GCC toolchain path for LLVM/Clang using the flag
*&#x2013;gcc-toolchain-path*:

    ./install.sh --prefix=llvm_install_path --gcc-toolchain-path=gcc_toolchain_path

Once the installation completes, you need to setup your environement
to allow Archer to work correctly.

Please set the following path variables:

    export PATH=${LLVM_INSTALL}/bin:${LLVM_INSTALL}/bin/archer:\${PATH}"
    export LD_LIBRARY_PATH=${LLVM_INSTALL}/lib:\${LD_LIBRARY_PATH}"

To make the environment permanent add the previous lines or
equivalents to your shell start-up script such as "~/.bashrc".

# Sponsors<a id="sec-5" name="sec-5"></a>

<img src="resources/images/uofu_logo.png" hspace="15" vspace="5" height="23%" width="23%" alt="UofU Logo" title="University of Utah" style="float:left" /> <img src="resources/images/llnl_logo.png" hspace="70" vspace="5" height="30%" width="30%" alt="LLNL Logo" title="Lawrence Livermore National Laboratory" style="float:center" /> <img src="resources/images/rwthaachen_logo.png" hspace="15" vspace="5" height="23%" width="23%" alt="RWTH AACHEN Logo" title="RWTH AACHEN University" style="float:left" />