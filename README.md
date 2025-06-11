# cs3220-lab-6---on-chip-communication-protocols-solved
**TO GET THIS SOLUTION VISIT:** [CS3220 Lab #6 – On-chip Communication Protocols Solved](https://mantutor.com/product/cs3220-lab-6-on-chip-communication-protocols-solved/)


---

**For Custom/Order Solutions:** **Email:** mantutorcodes@gmail.com  

*We deliver quick, professional, and affordable assignment help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;113820&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;4&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (4 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS3220 Lab #6 - On-chip Communication Protocols Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (4 votes)    </div>
    </div>
Part 1: AXI-Stream FIFO: 40 pts

Part 2: AXI4 RAM: 60 pts + 10 bonus pts

Submission ddl: Nov 19th

In this lab, you will delve into the robust and scalable on-chip communication protocol, AXI4, along with its streaming variant, AXI-Stream. The objective is to design and implement FIFOs/RAMs that leverage these two protocols for content reading and writing. While the previous lab focused on a straightforward register-based communication protocol for data exchange between the CPU and ALU, it lacked the scalability and robustness required for intricate communication scenarios. Such scenarios might involve more advanced modules, like a systolic array. Building on the knowledge gained in this assignment, the subsequent lab will guide you in utilizing the FIFOs/RAMs you’ve crafted to interconnect components within a sophisticated heterogeneous system.

Part 1: AXI-Stream FIFO:

In this section, you’ll finish the implementation of an AXI-Stream FIFO. Please also refer to the FAQ section for more design references.

For the FIFO part, there are two pointers corresponding to the read and write actions, respectively. * Each time the FIFO is read, the read pointer will be incremented by 1. * Each time the FIFO is written, the write pointer will be incremented by 1. * The read and write pointers are intentionally defined one bit wider than the bits needed to represent the FIFO address. * This is to avoid the ambiguous case for empty and full FIFOs. * Thus, when the FIFO is empty, the read pointer will be equal to the write pointer. When the FIFO is full, the 1st bit of the read and write pointers need to be different (They are in different wrap-around positions), while the rest of the bits are the same. * For better robustness, the pointer binary code is converted to gray code: ptr = ptr ^ (ptr &gt;&gt; 1). * The full and empty case will be conditioned on the gray code instead. * Note: Following the above logic, you need to come up with new logic to decide the full and empty case.

The code skeleton is provided in axis_data_fifo.v. Finish all the TODOs in the code.

To test your implementation, run the following command:

make axis_data_fifo

The test script is based on the testbench provided in tb_axis_fifo.v.

Part 2: AXI4 RAM (60 points + 10 bonus pts)

AXI-stream can only support accesses with a set of regular and consecutive addresses, which is limited in many applications. To support more general accesses, we need to use AXI4 protocol. In this section, you’ll finish the implementation of an AXI4 RAM. Please also refer to the FAQ section for more design references. Mostly, you will deal with managing the ready/valid signals and the transition among different read/write states. RAM interfaces have been handled for you.

The code skeleton is provided in axi4_ram.v. Finish all the TODOs in the code.

To test your implementation, run the following command:

make axi4_ram

The test script is based on the testbench provided in tb_axi4_ram.v.

Bonus: AXI4 RAM Burst Mode (10 points)

In this section, you’ll modify the implementation of an AXI4 RAM to supports burst mode. We provide a new code skeleton in axi4_ram_burst.v. Please combine with your previous parts implementation to finish all the TODOs in the code. You code should still pass the previous tests on nonburst mode.

Here are also some useful links for you: + https://www.youtube.com/watch?v=ydSy7uO60Is + https://www.youtube.com/watch?v=_twa6kY-ors + https://www.youtube.com/watch?v=ZDNOezaQ4Fk + https://www.youtube.com/watch?v=lI5Gh-1zk-s

To test your implementation, run the following commands:

make axi4_ram_burst make axi4_ram_burst_on_non_burst

Submission

Provide a zip file containing your source code. Generate the submission.zip file using the command make submit. Avoid manual zip file creation to prevent any issues with the autograding script, which could lead to a 30% score deduction.

FAQ

[Q] Useful links to refer to for AXI4 design? [A] Official AXI4 specification: link1 link2;

Handy timing diagrams from Xilinx: link3;
