---
layout: default
title: Overview
---




S²E is a platform for writing tools that analyze the properties and
behavior of software systems. S²E is a virtual machine augmented
with symbolic execution and modular path analyzers. S²E runs
unmodified x86, x86-64, or ARM software stacks, including programs,
libraries, the kernel, and drivers. Symbolic execution then
automatically explores hundreds of thousands of paths through the
system, while analyzers check that the desired properties hold on
these paths and selectors focus path exploration on components of interest.

We have used S²E to develop a
comprehensive performance profiler, a reverse engineering tool for
proprietary software, and a bug finding tool for both kernel-mode
and user-mode binaries. Others have used S²E to build scalable
file system checkers, symbolic execution engines for interpreted languages,
tools for finding trojan messages in distributed systems, verifying
software routers, testing embedded systems, and more.

<!--
<table>
<tr>
<td><img src="/images/s2e-sel.png" height="300px"/></td>
<td><img src="/images/s2e-vm.png" height="300px"/></td>
</tr>
</table>
-->

<img src="/images/s2e-sel.png" height="300px"/>
<img src="/images/s2e-vm.png" height="300px"/>


<hr/>



S²E's novelty consists of its ability to scale to large real
systems, such as a full Windows stack. S²E is based on two new ideas:

  *  Selective symbolic execution, a way to automatically minimize the amount of code that has to be executed symbolically given a target analysis; and
  *  Relaxed execution consistency models, a way to make principled performance/accuracy trade-offs in complex analyses.

These techniques give S²E three key abilities:

  *  to simultaneously analyze entire families of execution paths, instead of just one execution at a time;
  *  to perform the analyses in-vivo within a real software stack—user programs, libraries, kernel, drivers, etc.—instead of using abstract models of these layers; and
  *  to operate directly on binaries, thus being able to analyze even proprietary software.


Conceptually, S²E is an automated path explorer with modular path
analyzers: the explorer drives the target system down all execution
paths of interest, while analyzers check properties of each such
path (e.g., to look for bugs) or simply collect information (e.g.,
count page faults). Desired paths can be specified in multiple ways,
and S²E users can either combine existing analyzers to build a
custom analysis tool, or write new analyzers using the S²E API.

S²E helps make analyses based on symbolic execution practical for
large software that runs in real environments, without requiring
explicit modeling of these environments.

