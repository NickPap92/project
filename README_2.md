# Architecture Lab, Project 2

## Detailed Report

## Step 1. 

&nbsp;

### 1.

&nbsp;

#### Options.py
#### Path: ~/my_gem5/configs/common

##### Here we can see the basic CPU parameters that Gem5 is emulating regarding memory.
##### Variables

#### L1
- l1d_size=64kB [//]: # (L1 data cache size of 64kB)
- l1i_size=32kB [//]: # (L1 instruction cache size of 32kB)
- l1d_assoc=2 [//]: # (L1 data cache associativity of 2)
- l1i_assoc=2 [//]: # (L1 instruction cache associativity of 2)

#### L2
- l2_size= 2MB [//]: # (L2 cache size of 2MB)
- l2_assoc=8 [//]: # (L2 cache associativity of 8)

&nbsp;

&nbsp;
- cacheline_size=64 [//]: # (Cache line size of 64)

&nbsp;

### 2.

### Benchmark Results

&nbsp;
### Bzip

> - sim_seconds= 0.083982
> - system.cpu.cpi= 1.679650
> - system.cpu.dcache.overall_miss_rate::total= 0.014798 [//]: # (Miss rate for overall accesses for L1 data cache)
> - system.cpu.icache.overall_miss_rate::total= 0.000077 [//]: # (Miss rate for overall accesses for L1 instruction cache)
> - system.l2.overall_miss_rate::total= 0.282163 [//]: # (Miss rate for overall accesses for L2)

&nbsp;

### Mcf

> - sim_seconds= 0.064955
> - system.cpu.cpi= 1.299095
> - system.cpu.dcache.overall_miss_rate::total= 0.002108
> - system.cpu.icache.overall_miss_rate::total= 0.023612
> - system.l2.overall_miss_rate::total= 0.055046

&nbsp;

### Hmmer

> - sim_seconds= 0.059396
> - system.cpu.cpi= 1.187917
> - system.cpu.dcache.overall_miss_rate::total= 0.001637
> - system.cpu.icache.overall_miss_rate::total= 0.000221
> - system.l2.overall_miss_rate::total= 0.077760

&nbsp;

### Sjeng

> - sim_seconds= 0.513528
> - system.cpu.cpi= 10.270554
> - system.cpu.dcache.overall_miss_rate::total= 0.121831
> - system.cpu.icache.overall_miss_rate::total= 0.000020
> - system.l2.overall_miss_rate::total= 0.999972

&nbsp;

### Libm

> - sim_seconds= 0.174671
> - system.cpu.cpi= 3.493415
> - system.cpu.dcache.overall_miss_rate::total= 0.060972
> - system.cpu.icache.overall_miss_rate::total= 0.000094
> - system.l2.overall_miss_rate::total= 0.999944

&nbsp;

### Benchmark results in graphs

![Simulation duration](https://i.imgur.com/5KMeM3l.png)

![CPI](https://i.imgur.com/7wOhwxB.png)

![L1 data cache miss rate](https://i.imgur.com/5hYz4uq.png)

![L1 instr cache miss rate](https://i.imgur.com/n6i06RV.png)

![L2 cache miss rate](https://i.imgur.com/RKwU9AW.png)

These graphs show that the emulation duration is proportional to CPI, the shorter the duration the closer CPI to the absolute 1.0 is. We can see a similar trend with the L1 data cache miss rate, the longer the emulation lasted, the higher the miss rate for that portion of the memory is. 

Interestingly enough, Mcf was the only benchmark which had a vast difference in the L1 instruction cache miss rate of 0.023612 while the other benchmarks were hanging bellow the 0.0002 mark. 
Sjeng and Libm benchmarks, have a L2 cache miss rate of ~1.0 (0.999972 and 0.999944 respectively)

&nbsp;

### 3.

Default frequency the benchmarks were run at was 2GHz.

Emulating with a frequency of 4GHz yields these results:

### Bzip

> - (2GHz) system.clk_domain.clock= 1000 [//]: # (Clock period in ticks)
> - (4GHz) system.clk_domain.clock= 1000 [//]: # (Clock period in ticks)
> 
> &nbsp;
>
> - (2GHz) system.cpu_clk_domain.clock= 500 [//]: # (Clock period in ticks)
> - (4GHz) system.cpu_clk_domain.clock= 250 [//]: # (Clock period in ticks)

&nbsp;

### Mcf

> - (2GHz) system.clk_domain.clock= 1000 [//]: # (Clock period in ticks)
> - (4GHz) system.clk_domain.clock= 1000 [//]: # (Clock period in ticks)
> 
> &nbsp;
>
> - (2GHz) system.cpu_clk_domain.clock= 500 [//]: # (Clock period in ticks)
> - (4GHz) system.cpu_clk_domain.clock= 250 [//]: # (Clock period in ticks)

&nbsp;

This applies to the rest of the benchmarks.

&nbsp;

Regarding the system.clk_domain.clock, the system has a system clock which is needed to synchronize all components on the motherboard and our emulator is using a 1GHz frequency clock. As for system.cpu_clk_domain.clock, the CPU just takes the system clock and multiplies it by a number, which is either fixed or unlocked. 

In the first instance of 2GHz, the cpu_clk_domain.clock has a period of 500ns, resulting in a frequency F= 1/T= 1/500ns= 2000Hz= 2GHz.
Accordingly for the second simulation, we have a frequency of F= 1/250ns= 4000Hz= 4GHz.

By looking at the corresponding config.json files, we also see that the system clock domain (clk_domain) is set at 1000Hz and the cpu clock domain (cpu\_clk_domain) at 250 as observed above.

&nbsp;

We are now going to focus on the simulation duration of each benchmark run on the default 2GHz vs 4GHz, and see if there is a 1:1 linear scaling between frequency and sim duration. 

#### Bzip
- 2GHz: 0.083982
- 4GHz: 0.045678
The second test while having double the frequency, finished the test in 54.39% of the first benchmark. There is a 4.39% deviation from having perfect 1:1 scaling.

#### Mcf
- 2GHz: 0.064955
- 4GHz: 0.033496
>> 51.57% of 2GHz benchmark. 1.57% deviation from 1:1

#### Hmmer
- 2GHz: 0.059396
- 4GHz: 0.029829
>> 50.22% of 2Ghz benchmark. 0.22% deviation from 1:1

#### Sjeng
- 2GHz: 0.513528
- 4GHz: 0.417558
>> 81.31% of 2GHz benchmark. 31.31% deviation from 1:1

#### Libm
- 2GHz: 0.174671
- 4GHz: 0.131829
>> 75.47% of 2GHz benchmark. 25.47% deviation from 1:1

&nbsp;

As seen, Hmmer scales the best from CPU frequency while Sjeng's scaling is poor. A great explanation for why frequency increase doesn't always result in perfect scaling can be read here: [Why has CPU frequency ceased to grow?](https://software.intel.com/en-us/blogs/2014/02/19/why-has-cpu-frequency-ceased-to-grow). If we add one more CPU to this, it would have the default CPU clock frequency of 2GHz and a system clock frequency of 1GHz.

&nbsp;

&nbsp;

## Step 2.

&nbsp;

### 1.

For each benchmarks we performed 8 runs with a mixture of settings too see which of them will yield the best CPI. Further info can be found here [Benchmarks configurations](https://pastebin.com/UKf5t6j3)

&nbsp;
End results:

&nbsp;
#### Bzip

Best run with ./build/ARM/gem5.opt -d spec_results/specbzipTEST5 configs/example/se.py --cpu-type=MinorCPU --caches --l2cache --l1d_size=128kB --l1i_size=32kB --l2_size=4MB --l1i_assoc=1 --l1d_assoc=4 --l2_assoc=4 --cacheline_size=256 --cpu-clock=2GHz -c spec_cpu2006/401.bzip2/src/specbzip -o "spec_cpu2006/401.bzip2/data/input.program 10" -I 100000000

&nbsp; 
CPI is 1.600465, while default CPI is 1.679650. We see an improvement of 4.714375%. The aim was to improve L1data and L2 hit rate.

&nbsp;
#### Mcf

Best run with ./build/ARM/gem5.opt -d spec_results/specmcfTEST4 configs/example/se.py --cpu-type=MinorCPU --caches --l2cache --l1d_size=32kB --l1i_size=128kB --l2_size=2MB --l1i_assoc=1 --l1d_assoc=4 --l2_assoc=2 --cacheline_size=128 --cpu-clock=2GHz -c spec_cpu2006/429.mcf/src/specmcf -o "spec_cpu2006/429.mcf/data/inp.in" -I 100000000

&nbsp;
CPI is 1.125518, while default CPI is 1.299095. 13.361378% improvement. The aim was to mainly improve L1instruction hit rate.

&nbsp;
#### Hmmer

Best run with ./build/ARM/gem5.opt -d spec_results/spechmmerTEST7 configs/example/se.py --cpu-type=MinorCPU --caches --l2cache --l1d_size=128kB --l1i_size=64kB --l2_size=4MB --l1i_assoc=2 --l1d_assoc=4 --l2_assoc=4 --cacheline_size=128 --cpu-clock=2GHz -c spec_cpu2006/456.hmmer/src/spechmmer -o "--fixed 0 --mean 325 --num 45000 --sd 200 --seed 0 spec_cpu2006/456.hmmer/data/bombesin.hmm" -I 100000000

&nbsp;
CPI is 1.179809, default CPI is 1.187917. 0.682539% improvement. This benchmark on the default configuration is close enough to the theoretical ideal 1.0 that we would not see tremendous differences in any case.

&nbsp;
#### Sjeng

Best run with ./build/ARM/gem5.opt -d spec_results/specsjengTEST3 configs/example/se.py --cpu-type=MinorCPU --caches --l2cache --l1d_size=128kB --l1i_size=32kB --l2_size=4MB --l1i_assoc=2 --l1d_assoc=4 --l2_assoc=8 --cacheline_size=256 --cpu-clock=2GHz  -c spec_cpu2006/458.sjeng/src/specsjeng -o "spec_cpu2006/458.sjeng/data/test.txt" -I 100000000

&nbsp;
CPI is 5.171443, default being 10.270554. We see a huge 49.647867% improvement over original. Focused on the L1d and L2 and slightly on the L1i. Different variations of L2 did not improve the L2 hit rate at all.

&nbsp;
#### Libm

Best run with ./build/ARM/gem5.opt -d spec_results/speclibmTEST6 configs/example/se.py --cpu-type=MinorCPU --caches --l2cache --l1d_size=128kB --l1i_size=64kB --l2_size=4MB --l1i_assoc=1 --l1d_assoc=2 --l2_assoc=4 --cacheline_size=256 --cpu-clock=2GHz -c spec_cpu2006/470.lbm/src/speclibm -o "20 spec_cpu2006/470.lbm/data/lbm.in 0 1 spec_cpu2006/470.lbm/data/100_100_130_cf_a.of" -I 100000000

&nbsp;
CPI is 1.989308, default being 3.493415. 43.055491% improvement. Focused on L1d and L2.

&nbsp;

&nbsp;

### 2.

We will now present some graphs on how L1 data size, L1 instruction size, L2 size, L1 data associativity, L1 instruction associativity, L2 associativity and cache line size individually affect each benchmark.

&nbsp;

![Bzip2 CPI](https://i.imgur.com/0cn1pGj.png)

![Mcf CPI](https://i.imgur.com/RXyPfZw.png)

![Hmmer CPI](https://i.imgur.com/xjadnH9.png)

![Sjeng CPI](https://i.imgur.com/pgxmipy.png)

![Libm CPI](https://i.imgur.com/9qjuwoN.png)

&nbsp;

&nbsp; 
These graphs show that when a benchmark is slow due to a single variable, increasing the size or complexity of it will also improve CPI significantly, such as changing the cache_line_size of Sjeng and Libm. A combination of everything is needed to achieve max efficiency though.

&nbsp;

&nbsp;

## Step 3.

&nbsp;

Manufacturers always need to compromise on cache specifications. The most important reason being architectural limitations. A huge number of transistors is needed to build a cache and it is also one of the main energy demanding elements. Therefore, we need to balance out the performance, power consumption and the surface of the core, thus the cost of production. Finally, more cache means a larger area of memory we need to "search" through and access times can become longer.

&nbsp;
Static RAM, which is what L1 and L2 caches are made of, require 6 transistors per bit whilst Dynamic RAM requires only one transistor per bit. Also, L1 cache is physically very close to the CPU so as to maximize the speed in comparison to L2. On top of that, increasing the associativity of the L1 cache or the size of the cache, can only be done if taken into account the architecture changes that need to be done to accommodate such an increase.

&nbsp;
Typically, R&D (Research and Development) costs of a new CPU architecture are very expensive in the numbers of millions and together with physical limitations, as in a chip needs to be adequately cooled or it will melt and we can dissipate so much heat else fail-safe mechanisms shut the system down, have kept the L1 size in the numbers of up to 512kB (Data and Instruction cache) and L2 up to 8MB. In this specific scenario, our CPU has a L1 cache of 96kB (64kB Data and 32kB Instruction cache) and an L2 cache of 2MB.

&nbsp;
Based on the number of transistors needed for L1 cache vs L2 cache (6 vs 1), we can assume that 
1kB of L1d/L1i silicon cache is roughly the same as 6kB of L2 silicon. 
Regarding associativity, L1 associativity is more complex to increase as the L1 cache silicon is integrated
inside the CPU silicon and the area available is limited. We can also assume that to increase the associativity 
of L1 data cache from 2 to 4 is 6 times more expensive compared to increasing the L2a from 2 to 4.
The scaling should not be linear as the complexity increases, so an increase from 2 to 8 could lead to
L1da/L1ia costing 6^2 36 times more than L2a.

Given 1kBL1d=1kBL1i=6kBL2

cacheline*( (2\*32\*6\*L1d\*L1da\*(6^(|L1da-3|))) +(32\*6\*L1i\*L1ia\*(6^(|L1da-3|))) + (2048\*L2\*L2a) ) = X

cacheline*(384\*(2\*L1d\*L1da\*(6^(|L1da-3|)) + (L1i\*L1ia\*(6^(|L1da-3|)) + (2048\*L2\*L2a)) = X

Cost of the default proccessor: 64\*((384\*((2\*32\*2\*6) + (32\*2\*6)) + (2048\*8))) = X
X = 458.752

### Bzip

&nbsp;
For the Bzip benchmark, we notice that the L1d, L2, L1da and Cache_line yield the best immediate results
of increasing run time. From the graphs we can see that decreasing L2a drops performance by going from 8 down to 2
but not by that much. We could drop down to 4 without noticeable performance drops. Also the L1da increase from 2 to 4 doesn't justify the huge cost
it requires so we will keep the default value of 2. Increasing the Cache_line to 128 will double the cost, we will see if that's worth considering.

&nbsp;
So for the Bzip benchmark, we opt for increasing the L1d to 128kB, increase the L2 to 4MB and reduce L2a to 4. 

Bzip VFM cost: 64\*((384\*(2\*128\*2\*6) + (32\*2\*6))+(4096\*4))) = 1.196.416 . An increase of Cache_line would not justify doubling the cost for the performance gains.

&nbsp;

### Mcf

&nbsp;
Mcf benefits from increasing the L1i and the L1ia. L2a also seems to have a no impact on performance so we can drop that down to 2 and L2 down to 1MB.
We are also dropping L1d to 32kB and increasing L1i to 64kB.

Mcf VFM cost: 64\*((384\*(2\*32\*2\*6) + (64\*2\*6))+(1024\*2))) = 297.728. 

&nbsp;

### Hmmer

&nbsp;
Hmmer only benefits much from increasing Cache_line from 64 to 128. We can also decrease the L2a to 4, L1d to 32kB and L2 to 1MB.

Hmmer VFM cost: 128\*((384\*(2\*32\*2\*6) + (32\*2\*6))+(1024\*4))) = 299.392.

&nbsp;

### Sjeng

&nbsp;
Similarly this benchmark benefits from Cache_line. We will keep everything at the minimum cost value and increase only this.

Sjeng VFM cost: 128\*((384\*(2\*32\*2\*6) + (32\*2\*6)) + (1024\*2))) = 297.344.

&nbsp;

### Libm

&nbsp;
We notice a similar trend here, so the Libm VFM cost will be same as Sjeng, at 297.344.

&nbsp;

Besides Bzip benchmark, all of them can be optimized with a CPU costing less than the default configuration so that they have a higher CPI.

&nbsp;

Comparing the VFM costs vs the best performance costs for each benchmark that we found previously, we have:

- Bzip: VFM = 1.196.416, Perf = 169.886.080
- Mcf: VFM = 297.728, Perf = 3.544.576‬‬
- Hmmer: VFM = 299.392 Perf = 14.172.928‬
- Sjeng: VFM = 297.344 Perf = 14.188.928‬
- Libm: VFM = 297.344 Perf = 1.196.800‬

We can see that cost is easily reduced by a lot if we choose to go for a value for money route rather than a full performance one. By doing so, we get more than 85% of the performance route by only speding a fraction of the cost to manufacture such a CPU.

&nbsp;
Choosing which configuration better fits for each application, we need to take into account a lot of variables such as physical limitations, decide which components we need to better focus on, as in the ones that yield the best increase in performance as shown in the graphs of Step 2\_2, and decide on a cost that would make sense for the target group. It's a very hard and complex equation to be answered and this second Lab successfully managed to make us think as engineers instead of consumers. The possibilities of improving a CPU architecture compared to cost seem endless and it takes both intuition and carefully planning the design in order to get the best results. Overall the project made us dig into the associativity of the caches, the complexicity that arises by increasing them, predictive caching, the cost of having to search through different types of L caches, code locality and sparsity and that it's not always efficient or clever to try and go bigger and bigger on sizes, it's practically impossible and R&D money thrown into new CPU architectures is the key to moving forward as we demand more and more proccessing power from our central units.


&nbsp;
Bibliography used:
- [Modeling and Optimization of Parallel and Distributed Embedded Systems](https://books.google.gr/books?id=aEpICgAAQBAJ&pg=PA136&lpg=PA136&dq=mm2+size+of+L1+cache&source=bl&ots=EpnXWUnnuM&sig=ACfU3U1aTvVXukW3rGH0Sf_9yP-CDPfYgg&hl=en&sa=X&ved=2ahUKEwiImaS1wbjmAhXJb5oKHQHUA6wQ6AEwDHoECAoQAQ#v=onepage&q=mm2%20size%20of%20L1%20cache&f=false)
- [A look into CPU Cache](https://courses.cs.washington.edu/courses/cse378/09au/lectures/cse378au09-20.pdf)
- [Zen 2 Architecture](https://www.anandtech.com/show/14525/amd-zen-2-microarchitecture-analysis-ryzen-3000-and-epyc-rome/5)
- [Why is the L1 cache always smaller than the L2 cache](https://www.researchgate.net/post/Why_is_the_L1_cache_always_smaller_than_the_L2_cache_and_if_there_is_an_L3_why_is_the_L2_smaller_than_the_L3)
- [What is the Cost of an L1 Cache Miss?](https://stackoverflow.com/questions/1126529/what-is-the-cost-of-an-l1-cache-miss)
- [Opteron Architecture](https://en.wikipedia.org/wiki/Opteron)
- [Sram vs Dram](https://www.diffen.com/difference/Dynamic_random-access_memory_vs_Static_random-access_memory)
