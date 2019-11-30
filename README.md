# Architecture Lab, Project 1

## Detailed Report
&nbsp;
## 1. 

&nbsp;

### starter_se.py
>  **Basic parameters input** &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  
> **Variables** &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 
> &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  
> **cpu**, type=str, value="atomic" [//]: # (Cpu type="atomic") &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  
> **cpu-freq**, type=int, value=1 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: # (Cpu frequency=4GHz) &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  
> **mem-type**, type=str, value="DDR3\_1600_8x8 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: # (DDR3, 1600 MT/s, Parameter: 256 Meg x 8, Configuration: 32 Meg x 8 x 8 banks) &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  
> **mem-channels**, type=int, value=2 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # (Running on dual channel, NorthBridge Frequency=800MHz) &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 
> **mem-ranks**, type=int, value=None &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: # (Memory Rank - nT) &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 
> **mem-size**, type=str, value="2GB", action="store" &nbsp; &nbsp; &nbsp; &nbsp; [//]: # (Capacity: 2GB) &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 
> **cache\_line_size**, type=int, value=64 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; [//]: # (Cache size=64 bytes) &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  
> **voltage_domain**, type=str, value="3.3V" &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # (Each core can be implemented in a separate voltage domain. This is set at 3.3V) &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 
> **clk_domain**, type=str, value="1GHz" &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; [//]: # (Each core can be implemented in a separate clock domain. This is set at 1GHz)
> &nbsp;
> Note: The code line *__"self.cpu_cluster = devices.CpuCluster(self,args.num_cores,args.cpu_freq, "1.2V",\*cpu_types[args.cpu])"__*
> implies that there is a variable that takes a string value of "1.2V", presumably to be called **cpu_voltage**, type=str, value="1.2V".
> *__"devices.CpuCluster( )"__* is a method, and "self" is used to pass the variable *__"cpu_cluster"__* in this method as the first argument.

&nbsp;

&nbsp;

&nbsp;

## 2.

&nbsp;

### config.ini
> **Variables**
> &nbsp;
> **cache\_line_size**=64, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Ln: 15 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # (As expected according to starter_se.py)
> **numThreads**=1, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 72 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # (Implies that this is a 1c/1T CPU)
> **clk_domain**=1000, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 44, 57, 210, 223 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: # (This variable was a string with a value of "1GHz" which got converted to int=1000)
> **ranks\_per_channel**=2, &nbsp; &nbsp; Ln: 345 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: # (Command Rate= 2T, probably defaulted to 2T when value None is given. Sounds reasonable as 1T is more demanding to achieve opposed to 2T, although it's faster)
> **voltage_domain**=1.0, &nbsp; &nbsp; &nbsp; &nbsp;Ln; 432 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: # (Default value is 1.0 integer, it was called with the value of "3.3V", string)

&nbsp;
&nbsp;
### config.json
> **Variables**
> &nbsp;
> **clk_domain**=1000, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 117&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;   [//]: # (Clock domain set to 1GHz)
> **voltage_domain**=1.0, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 148&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: #  (Default value is 1.0 integer, it was called with the value of “3.3V”, string)
> **numThreads**=1, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 189&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # (Implies that this is a 1c/1T CPU)
> **multi_thread**=false, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Ln: 450&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: # (Not multithreaded, running on 1 thread) 
> **VDD**=1.5, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Ln: 489&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: # (The nominal (drain) supply voltage, usually 1.5V for DDR3 modules and 1.35V for low powered DDR3)
> **ranks\_per_channel**=2, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 522&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # (Command Rate= 2T)
> **devices_per_rank**=8, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Ln: 526&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # ( 32 Meg x 8 x 8 banks configuration, 256 Meg per chip module)

&nbsp;
&nbsp;
### stats.txt
> **Variables**
> &nbsp;
> **voltage_domain**=1.0, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Ln: 246
> **clk_domain**=1000, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 247

&nbsp;
###### **Bibliography**
&nbsp;
    - [JEDEC - Nominal power supply voltage (VDD)](https://www.jedec.org/standards-documents/dictionary/terms/nominal-power-supply-voltage-vdd)
    - [DDR2 And DDR3 Memory Systems Power Solutions](https://www.electronicdesign.com/power/ddr2-and-ddr3-memory-systems-require-new-power-and-termination-solutions)
    - [DDR3 SDRAM 1.35V-to-1.5V Compatibility](https://www.micron.com/-/media/client/global/documents/products/technical-note/dram/tn4114_ddr3_1_35v_1_5v_compat.pdf)
    - [2Gb: x4, x8, x16 DDR3 SDRAM - Micron Technology, Inc.](https://www.micron.com/-/media/documents/products/data%20sheet/dram/ddr3/2gb_ddr3_sdram.pdf)
    - [Arm DynamIQ Shared Unit Technical Reference Manual Revision r4p0, Clock, voltage, and power domains](https://developer.arm.com/ja/docs/100453/latest/functional-description/power-management/clock-voltage-and-power-domains)
    - [The self variable in python explained](https://pythontips.com/2013/08/07/the-self-variable-in-python-explained/)
    - [Understanding self and __init__ method in python Class](https://micropyramid.com/blog/understand-self-and-__init__-method-in-python-class/)
    - [Why explicit self has to stay, by Guido van Rossum](http://neopythonic.blogspot.com/2008/10/why-explicit-self-has-to-stay.html)

&nbsp;

&nbsp;

&nbsp;

## 3.

&nbsp;

### **Gem5 _in-order_&nbsp; CPUs model types**

&nbsp;

 **AtomicSimpleCPU**
> The AtomicSimpleCPU uses Atomic memory accesses. In gem5, the AtomicSimpleCPU performs all
> operations for an instruction on every CPU tick() and it can get a rough estimation of overall cache access time using the
> latency estimates from the atomic accesses [1]. Naturally, AtomicSimpleCPU provides the fastest functional simulation, and
> is used for fast-forwarding to get to a Region Of Interest (ROI) in gem5.

&nbsp;

**TimingSimpleCPU**

> The TimingSimpleCPU adopted Timing memory access instead of the simple Atomic one. This means that it waits until
> memory access returns before proceeding, therefore it provides some level of timing. TimingSimpleCPU is also a fast-to-run
> model, since it simplifies some aspects including pipelining, which means that only a single instruction is being processed
> at any time. Each arithmetic instruction is executed by TimingSimpleCPU in a single cycle, while memory accesses require
> multiple cycles.

&nbsp;

**MinorCPU**

> The MinorCPU is a flexible in-order processor model which was originally developed to support the Arm ISA, and is
> applicable to other ISAs as well. As shown in Fig 3, MinorCPU has a fixed four-stage in-order execution pipeline, while
> having configurable data structures and execute behavior; therefore it can be configured at the micro-architecture level to
> model a specific processor.
> The four-stage pipeline implemented by MinorCPU includes fetching lines, decomposition into macro-ops, decomposition of macro-ops into micro-ops and execute. 
> These stages are named Fetch1, Fetch2, Decode and Execute, respectively. The pipeline class controls the cyclic tick event and the idling (cycle skipping).

&nbsp;

&nbsp;

### a.

**This code sample is used to generated n numbers from a range of zero to 100 using the rand() function.**


    #include <stdio.h>
    #include <stdlib.h>
    #include <time.h>
    #define MAX 5
    #define seedx 3
    
    int *mem;
     
     
    int * arrayCreator()
    {
    int i, d, *array;
 	array=(int*)malloc(sizeof(MAX));
 	for (i=0; i<MAX; i++)
 	{
 	    d=(rand()%(101)); // rand()%(limit+1) to get number between 0-limit
 		array[i]=d;
 	}
 	mem= &array[0];
 	return(array);
    }
 
 
    int main()
    {
 	int i, *vec;
 	
 	srand ( seedx );
 	printf("Random number sequence has started..\n");
 	printf("%d random numbers will be generated via rand() between 0-100\n", MAX);
    vec=arrayCreator();	

 	for (i=0; i<MAX; i++)
	{
		printf("Number %d: %d\n", i, vec[i]);
	}
	free(mem);
	//free(&randinit[0]);
	return(1);
    }

&nbsp;

### b.

### MinorCPU
&nbsp;
### config.json
> **Variables**
> &nbsp;
> **clk_domain**=1000, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 117&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;   [//]: # (Clock domain set to 1GHz)
> **voltage_domain**=1.0, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 148&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: #  (Default value is 1.0 integer, it was called with the value of “3.3V”, string)
> **numThreads**=1, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 189&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # (Implies that this is a 1c/1T CPU)
> **multi_thread**=false, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Ln: 450&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: # (Not multithreaded, running on 1 thread) 
> **VDD**=1.5, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Ln: 489&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: # (The nominal (drain) supply voltage, usually 1.5V for DDR3 modules and 1.35V for low powered DDR3)
> **ranks\_per_channel**=2, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 522&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # (Command Rate= 2T)
> **devices_per_rank**=8, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Ln: 526&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # ( 32 Meg x 8 x 8 banks configuration, 256 Meg per chip module)

**As seen the config.json remains the same for those variables with the hello_world example**

&nbsp;

### config.ini
> **Variables**
> &nbsp;
> **cache\_line_size**=64, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Ln: 15 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # (As expected according to starter_se.py)
> **numThreads**=1, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 72 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # (Implies that this is a 1c/1T CPU)
> **clk_domain**=1000, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 44, 57, 210, 223 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: # (This variable was a string with a value of "1GHz" which got converted to int=1000)
> **ranks\_per_channel**=2, &nbsp; &nbsp; Ln: 345 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: # (Command Rate= 2T, probably defaulted to 2T when value None is given. Sounds reasonable as 1T is more demanding to achieve opposed to 2T, although it's faster)
> **voltage_domain**=1.0, &nbsp; &nbsp; &nbsp; &nbsp;Ln; 432 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: # (Default value is 1.0 integer, it was called with the value of "3.3V", string)

**Same applies for the config.ini file**

&nbsp;
### stats.txt
> **Variables**
> &nbsp;
> **host_seconds**=0.09seconds &nbsp; - **was 0.03s for hello_world example**
> **sim_insts**=28357 &nbsp; - **was 5027** &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # number of instructions simulated
> **system.cpu.numCycles***=107294 &nbsp; - **96348** &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # number of cpu cycles stimulated
> **system.clk_domain.clock**=1000 &nbsp; -**same as hello_world**
> **system.cpu.workload.numSyscalls**=17 &nbsp; -**13 for hello_world** &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # number of system calls

**As seen, this specific program is 3 times slower than the hello_world example**

For MinorCPU configuration, our program has a **CPI** of **3.783687** (CPI: cycles per instruction) and an **IPC** of **0.264293** (IPC: instructions per cycle - Not all GHz are created equally @(O_O)@ )

&nbsp;

### TimingSimpleCPU
&nbsp;
The config.json and config.ini files are identical to the MinorCPU simulation.
### stats.txt
> **Variables**
> &nbsp;
> **host_seconds**=0.05seconds &nbsp; - **was 0.09s for MinorCPU**
> **sim_insts**=28268 &nbsp; - **was 28357** &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # number of instructions simulated
> **system.cpu.numCycles***=145488 &nbsp; - **107294** &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: # number of cpu cycles stimulated
> **system.clk_domain.clock**=1000 &nbsp; -**same as MinorCPU**
> **system.cpu.workload.numSyscalls**=17 &nbsp; -**Same system calls as MinorCPU** &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: # number of system calls

We described the TimingSimpleCPU as "_TimingSimpleCPU is also a fast-to-run
model, since it simplifies some aspects including pipelining, which means that only a single instruction is being processed
at any time._" 
Given that our program is simple and lightweight enough to run, TimingSimpleCPU is 0.04s faster than the MinorCPU and it's logical. As a program gets more complex, MinorCPU method that has a fixed four-stage in-order execution pipeline, multiple execution is expected to become faster, thus giving MinorCPU an edge.

&nbsp;

### MinorCPU w/ 500Mhz system clock

Now let's run our program as **./build/ARM/gem5.opt -d project_results configs/example/se.py --cpu-type=MinorCPU --sys-clock=500000000 --caches -c /home/nick/project/project_arm** to simulate 500MHz system clock compared to 1GHz default.

### config.json
> **Variables**
> &nbsp;
> **clk_domain**=2000, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 117
> **voltage_domain**=1.0, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 148&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: #  (Default value is 1.0 integer, it was called with the value of “3.3V”, string)
> **numThreads**=1, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 189&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # (Implies that this is a 1c/1T CPU)
> **multi_thread**=false, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Ln: 450&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: # (Not multithreaded, running on 1 thread) 
> **VDD**=1.5, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Ln: 489&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: # (The nominal (drain) supply voltage, usually 1.5V for DDR3 modules and 1.35V for low powered DDR3)
> **ranks\_per_channel**=2, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 522&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # (Command Rate= 2T)
> **devices_per_rank**=8, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Ln: 526&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # ( 32 Meg x 8 x 8 banks configuration, 256 Meg per chip module)


### config.ini
> **Variables**
> &nbsp;
> **cache\_line_size**=64, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Ln: 15 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # (As expected according to starter_se.py)
> **numThreads**=1, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 72 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # (Implies that this is a 1c/1T CPU)
> **clk_domain**=2000, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 44, 57, 210, 223 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;
> **ranks\_per_channel**=2, &nbsp; &nbsp; Ln: 345 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: # (Command Rate= 2T, probably defaulted to 2T when value None is given. Sounds reasonable as 1T is more demanding to achieve opposed to 2T, although it's faster)
> **voltage_domain**=1.0, &nbsp; &nbsp; &nbsp; &nbsp;Ln; 432 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: # (Default value is 1.0 integer, it was called with the value of "3.3V", string)

### stats.txt
> **Variables**
> &nbsp;
> **host_seconds**=0.09seconds &nbsp; - **same as before**
> **sim_insts**=28357 &nbsp; - **same instructions** &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # number of instructions simulated
> **system.cpu.numCycles***=124320 &nbsp; - **was 107294** &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # number of cpu cycles stimulated
> **system.clk_domain.clock**=2000 &nbsp; -**was 1000**
> **system.cpu.workload.numSyscalls**=17 &nbsp; -**same as before** &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # number of system calls

The MinorCPU with a system clock of 0.5GHz instead of 1GHz, needs to simulate more instructions to achieve the same results, albeit doing this in the same time frame.

### TimingSimpleCPU w/ 500Mhz system clock

### config.json
> **Variables**
> &nbsp;
> **clk_domain**=2000, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 117
> **voltage_domain**=1.0, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 148&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: #  (Default value is 1.0 integer, it was called with the value of “3.3V”, string)
> **numThreads**=1, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 189&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # (Implies that this is a 1c/1T CPU)
> **multi_thread**=false, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Ln: 450&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: # (Not multithreaded, running on 1 thread) 
> **VDD**=1.5, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Ln: 489&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: # (The nominal (drain) supply voltage, usually 1.5V for DDR3 modules and 1.35V for low powered DDR3)
> **ranks\_per_channel**=2, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 522&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # (Command Rate= 2T)
> **devices_per_rank**=8, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Ln: 526&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # ( 32 Meg x 8 x 8 banks configuration, 256 Meg per chip module)


### config.ini
> **Variables**
> &nbsp;
> **cache\_line_size**=64, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Ln: 15 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # (As expected according to starter_se.py)
> **numThreads**=1, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 72 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # (Implies that this is a 1c/1T CPU)
> **clk_domain**=2000, &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; Ln: 44, 57, 210, 223 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;
> **ranks\_per_channel**=2, &nbsp; &nbsp; Ln: 345 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: # (Command Rate= 2T, probably defaulted to 2T when value None is given. Sounds reasonable as 1T is more demanding to achieve opposed to 2T, although it's faster)
> **voltage_domain**=1.0, &nbsp; &nbsp; &nbsp; &nbsp;Ln; 432 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;[//]: # (Default value is 1.0 integer, it was called with the value of "3.3V", string)

### stats.txt
> **Variables**
> &nbsp;
> **host_seconds**=0.03seconds &nbsp; - **was 0.05s before**
> **sim_insts**=28268 &nbsp; - **28357** &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # number of instructions simulated
> **system.cpu.numCycles***=159904 &nbsp; - **was 124320** &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # number of cpu cycles stimulated
> **system.clk_domain.clock**=2000 &nbsp; -**was 1000**
> **system.cpu.workload.numSyscalls**=17 &nbsp; -**same as before** &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # number of system calls

The TimingSimpleCPU with a system clock of 0.5GHz instead of 1GHz, simulated a bit less instructions than sys-clock 1GHz, required way more cpu cycles, as expected but stayed less time on the host (0.02s difference).

&nbsp;

### MinorCPU w/ HBM\_1000\_4H\_1x128 memory type

### stats.txt
> **Variables**
> &nbsp;
> **host_seconds**=0.09seconds &nbsp; - **same as default memory type**
> **sim_insts**=28357 &nbsp; - **same** &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # number of instructions simulated
> **system.cpu.numCycles***=111974 &nbsp; - **107294** &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # number of cpu cycles stimulated
> **system.clk_domain.clock**=1000 &nbsp; -**not changed**
> **system.cpu.workload.numSyscalls**=17 &nbsp; -**same as before** &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # number of system calls

As expected, stepping up memory from DDR3\_1600 to HBM\_1000 hardly did anything to improve the execution of the program. It is simple enough that it won't change the execution time of it.

### TimingSimpleCPU w/ HBM\_1000\_4H\_1x128 memory type

### stats.txt
> **Variables**
> &nbsp;
> **host_seconds**=0.03seconds &nbsp; - **same as before**
> **sim_insts**=28268 &nbsp; - **28356** &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # number of instructions simulated
> **system.cpu.numCycles***=150404 &nbsp; - **124320** &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # number of cpu cycles stimulated
> **system.clk_domain.clock**=1000 &nbsp; -**not changed**
> **system.cpu.workload.numSyscalls**=17 &nbsp; -**same as before** &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; [//]: # number of system calls

While it simulated more cpu cycles, again the memory type doesn't play a crucial role in the execution of this specific program.

&nbsp;

&nbsp;

In conclusion, this was a great entry to simulating an ARM CPU. 
Food for thought:
> The rand() function will keep giving us the same 5 numbers because the seed is the same that's used in srand(seed). This can be somehow aleviated, by using srand(time(NULL)) or by having a counter that will keep changing every time the program runs and thus the srand(counter) will always be different. 
The first itteration of this project was a user input 0-limit as to where the rand was supposed to find numbers in, using (rand()%(lim+1)) and also user decides how many numbers we will get. This lead to some issues where the terminal would not wait for user input at all and would ignore any fgets(), getchar(), scanf(" %c") etc thus leading to the program not running. The function getch() can force the terminal to wait for user input, which resides in the curses.h library, although this has to be linked before building with gem5. 
This can be done with **gcc -static code.c -o curses -lncurses -ltinfo** but was omitted for the shake of simplicity in this project. 




