---
layout: post
title: "Find processor (cpu) information on linux"
date: 2009-10-26T23:49:00+05:30
comments: false
categories:
 - linux
---
Below command will give you all the details about CPU
```
cat /proc/cpuinfo
```
#### Example use
on my ubuntu machine, It showed me below information :
```
processor : 0
vendor_id : GenuineIntel
cpu family  : 6
model   : 42
model name  : Intel(R) Core(TM) i3-2350M CPU @ 2.30GHz
stepping  : 7
microcode : 0x1b
cpu MHz   : 800.000
cache size  : 3072 KB
physical id : 0
siblings  : 4
core id   : 0
cpu cores : 2
apicid    : 0
initial apicid  : 0
fpu   : yes
fpu_exception : yes
cpuid level : 13
wp    : yes
flags   : fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush dts acpi mmx fxsr sse sse2 ss ht tm pbe syscall nx rdtscp lm constant_tsc arch_perfmon pebs bts rep_good nopl xtopology nonstop_tsc aperfmperf eagerfpu pni pclmulqdq dtes64 monitor ds_cpl vmx est tm2 ssse3 cx16 xtpr pdcm pcid sse4_1 sse4_2 x2apic popcnt tsc_deadline_timer xsave avx lahf_lm arat epb xsaveopt pln pts dtherm tpr_shadow vnmi flexpriority ept vpid
bogomips  : 4589.39
clflush size  : 64
cache_alignment : 64
address sizes : 36 bits physical, 48 bits virtual
power management:

processor : 1
vendor_id : GenuineIntel
cpu family  : 6
model   : 42
model name  : Intel(R) Core(TM) i3-2350M CPU @ 2.30GHz
stepping  : 7
microcode : 0x1b
cpu MHz   : 800.000
cache size  : 3072 KB
physical id : 0
siblings  : 4
core id   : 1
cpu cores : 2
apicid    : 2
initial apicid  : 2
fpu   : yes
fpu_exception : yes
cpuid level : 13
wp    : yes
flags   : fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush dts acpi mmx fxsr sse sse2 ss ht tm pbe syscall nx rdtscp lm constant_tsc arch_perfmon pebs bts rep_good nopl xtopology nonstop_tsc aperfmperf eagerfpu pni pclmulqdq dtes64 monitor ds_cpl vmx est tm2 ssse3 cx16 xtpr pdcm pcid sse4_1 sse4_2 x2apic popcnt tsc_deadline_timer xsave avx lahf_lm arat epb xsaveopt pln pts dtherm tpr_shadow vnmi flexpriority ept vpid
bogomips  : 4589.39
clflush size  : 64
cache_alignment : 64
address sizes : 36 bits physical, 48 bits virtual
power management:

processor : 2
vendor_id : GenuineIntel
cpu family  : 6
model   : 42
model name  : Intel(R) Core(TM) i3-2350M CPU @ 2.30GHz
stepping  : 7
microcode : 0x1b
cpu MHz   : 800.000
cache size  : 3072 KB
physical id : 0
siblings  : 4
core id   : 0
cpu cores : 2
apicid    : 1
initial apicid  : 1
fpu   : yes
fpu_exception : yes
cpuid level : 13
wp    : yes
flags   : fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush dts acpi mmx fxsr sse sse2 ss ht tm pbe syscall nx rdtscp lm constant_tsc arch_perfmon pebs bts rep_good nopl xtopology nonstop_tsc aperfmperf eagerfpu pni pclmulqdq dtes64 monitor ds_cpl vmx est tm2 ssse3 cx16 xtpr pdcm pcid sse4_1 sse4_2 x2apic popcnt tsc_deadline_timer xsave avx lahf_lm arat epb xsaveopt pln pts dtherm tpr_shadow vnmi flexpriority ept vpid
bogomips  : 4589.39
clflush size  : 64
cache_alignment : 64
address sizes : 36 bits physical, 48 bits virtual
power management:

processor : 3
vendor_id : GenuineIntel
cpu family  : 6
model   : 42
model name  : Intel(R) Core(TM) i3-2350M CPU @ 2.30GHz
stepping  : 7
microcode : 0x1b
cpu MHz   : 800.000
cache size  : 3072 KB
physical id : 0
siblings  : 4
core id   : 1
cpu cores : 2
apicid    : 3
initial apicid  : 3
fpu   : yes
fpu_exception : yes
cpuid level : 13
wp    : yes
flags   : fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush dts acpi mmx fxsr sse sse2 ss ht tm pbe syscall nx rdtscp lm constant_tsc arch_perfmon pebs bts rep_good nopl xtopology nonstop_tsc aperfmperf eagerfpu pni pclmulqdq dtes64 monitor ds_cpl vmx est tm2 ssse3 cx16 xtpr pdcm pcid sse4_1 sse4_2 x2apic popcnt tsc_deadline_timer xsave avx lahf_lm arat epb xsaveopt pln pts dtherm tpr_shadow vnmi flexpriority ept vpid
bogomips  : 4589.39
clflush size  : 64
cache_alignment : 64
address sizes : 36 bits physical, 48 bits virtual
power management:
```
