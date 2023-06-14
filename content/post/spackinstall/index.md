---
title: Libraries installation using spack
subtitle: 

# Summary for listings and search engines
summary: use spack to install software

# Link this post with a project
projects: []

# Date published
date: '2022-07-01T00:00:00Z'

# Date updated
lastmod: '2022-07-01T00:00:00Z'

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

authors:
  - admin

tags:
  - spack
  - software

categories:
  - Tutorial


---

## 1. Introduction

This blog will walk you through the process of installing spack and a few library packages on a Linux machine. Later, we will utilize spack as package management software to create research software. It is simple to use and administer. Spack will be used to install cuda, openmpi, and intel-mkl. The software dependencies are critical for reproducibility in research.

## 2. Install spack
First you need to clone spack.

```
git clone -c feature.manyFiles=true https://github.com/spack/spack.git $HOME/spack
. $HOME/spack/share/spack/setup-env.sh
```

This will create a folder called spack in your home directory. The spack environment should then be activated. Spack does not recognize the compiler tools. You should be prepared with your own compiler. It can be either system-generated or module-generated. After that, ensure that spack can find it. You can do `spack compiler find`. 
For example, on my linux machine I have two compilers.
```
hongy0a@qaysar:~$ spack compiler find
==> Added 2 new compilers to /home/hongy0a/.spack/linux/compilers.yaml
    gcc@7.5.0  gcc@6.5.0
==> Compilers are defined in the following files:
    /home/hongy0a/.spack/linux/compilers.yaml
```

## 3. Software

Then you may install libraries using spack! It might take up to an hour to install all libraries. When installing the library, you must provide the gcc version and target system. If you wish to install the libraries using gcc 7.5.0 and an x86 64 machine, for example.

```
spack install cuda@11.5.0~allow-unsupported-compilers~dev%gcc@7.5.0 target=x86_64
spack install openmpi%gcc@7.5.0 target=x86_64
spack install cmake%gcc@7.5.0 target=x86_64
spack install intel-mkl%gcc@7.5.0 target=x86_64
```

Have a look at what we’ve installed.

```
hongy0a@qaysar:~$ spack find
==> 39 installed packages
-- linux-ubuntu18.04-x86_64 / gcc@7.5.0 -------------------------
autoconf@2.69                       cpio@2.13      intel-mkl@2020.4.304  libtool@2.4.7   openssl@1.1.1p  util-macros@1.19.3
automake@1.16.5                     cuda@11.5.0    krb5@1.19.3           libxml2@2.9.13  perl@5.34.1     xz@5.2.5
berkeley-db@18.1.40                 curl@7.83.0    libedit@3.1-20210216  m4@1.4.19       pigz@2.7        zlib@1.2.12
bison@3.8.2                         diffutils@3.8  libevent@2.1.12       ncurses@6.2     pkgconf@1.8.0   zstd@1.5.2
bzip2@1.0.8                         gdbm@1.19      libiconv@1.16         numactl@2.0.14  pmix@4.1.2
ca-certificates-mozilla@2022-03-29  gettext@0.21   libpciaccess@0.16     openmpi@4.1.4   readline@8.1
cmake@3.23.2                        hwloc@2.7.1    libsigsegv@2.13       openssh@9.0p1   tar@1.34
hongy0a@qaysar:~$
```