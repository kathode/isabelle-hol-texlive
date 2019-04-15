# isabelle-hol-texlive
[Debian Stretch](https://wiki.debian.org/DebianStretch)-based Docker image of [Isabelle2018](https://isabelle.in.tum.de/) with [TeX Live](https://www.tug.org/texlive/). The Dockerfile closely follows that of the official distribution ([makarius/isabelle](https://hub.docker.com/r/makarius/isabelle/)) and in addition provides the following sessions pre-built:

* HOL
* HOL-Algebra
* HOL-Computational_Algebra
* HOL-Library

We also include the following debian LaTeX packages as they are typically required to build theory documentation:

* texlive
* texlive-latex-extra (required packages eg. fullpage.sty)
* texlive-math-extra (required packages eg. stmaryrd.sty)

## Usage
The image is available on Docker hub as [```pfribeiro/isabelle-hol-texlive```](https://hub.docker.com/r/pfribeiro/isabelle-hol-texlive/). It is automatically built from this repository using the Docker cloud.

## Using jEdit with docker image
It turns out you can use this docker image as is to run the GUI version too. For example on OSX this is possible following [these instructions](https://gist.github.com/cschiewek/246a244ba23da8b9f0e7b11a68bf3285):

1. Install XQuartz.
2. Launch XQuartz and change Preferences to "Allow connections from network clients".
3. Run ```xhost + ${hostname}```.
4. Run isabelle docker as follows:
```
docker run --rm -ti -e DISPLAY=${HOSTNAME}:0 -v /tmp/.X11-unix:/tmp/.X11-unix:rw pfribeiro/isabelle-hol-texlive:debian jedit
```
Enjoy your pre-built HOL session!
