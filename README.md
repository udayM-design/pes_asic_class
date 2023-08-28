# pes_asic_class
<details>
<summary>DAY 1</summary>
<br>
	
[](https://github.com/udayM-design/pes_asic_class#links-for-easy-navigaton)
## Day 1 Assignment

### 1. Create a simple C program That calculates sum from 1 to N -> Sum of numbers from 1 to n

```
gcc 1ton.c -o 1ton.o
./1ton.o

```
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/99980318-cea2-436a-8b82-da5ee495e35b)


### compile using riscv compieler and view the output
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/8e1004ca-1d8e-42f8-8f4d-df14c2f88fa4)


### To debug the ALP generated by the compiler
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/295595b7-5c89-4da7-98a9-e70dc1395b21)


### Contents of main when used -O1 optimizer

![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/1766e1a5-266c-4aed-875d-1af09263358f)


### contents of main when used -Ofast optimizer
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/0c8dcd17-a463-49c5-bbc8-e246ff9c260a)

## 2.create a C program that shows the maximum and minimum values of 64bit unsigend and signed numbers
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/270c60de-78c6-478e-8282-e7d284f7a225)

</details>


<details>
<summary>DAY 2</summary>
<br>
	
[](https://github.com/udayM-design/pes_asic_class#links-for-easy-navigaton)
## Day 2 
#### Representation formats of load, add, store etc instructions  
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/08e92535-a42d-488f-9df8-d5f901eee2d3)

### Simulating new C program with function call 
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/f69f4e52-c5fb-4388-9866-4d84ed79c36d)
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/9d48b598-ca70-4c77-b94c-d5f0b2732eb0)

### To run C-program on RISC-V CPU
```
chmod 777 rv32im.sh
./rv32im.sh
```
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/7c83c041-a5fa-4377-b578-8b460208ccd9)


</details>
<details>
<summary>RTL Design Using Verilog With SKY130 Technology</summary>
<br>
	
[](https://github.com/udayM-design/pes_asic_class#links-for-easy-navigaton)
#### DAY 1
<details>
<summary>Labs on Yosys introduction</summary>
<br>
	
[](https://github.com/udayM-design/pes_asic_class#links-for-easy-navigaton)
 Invoking yosys
 ![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/9051e4fc-4438-4a67-a32d-3d98d945af3f)

```
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog good_mux.v
synth -top good_mux.v

```
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/a95f917f-f3c5-423b-b08f-97900ee085da)
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/1c4b517a-ce68-4691-8709-c92c199aa1fb)
```
To synthesis the mosule:synth -top good_mux
```
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/5e352ecb-eade-4b78-a448-7818f80993b2)

```
To generate the netlist:abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

```
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/916136e4-38c3-4257-82d5-f34b977bf99c)
```
To see the logic it has realised : show
```
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/fefa9063-3365-4f5f-abe6-2718d0604865)

</details>
</details>
<details>
<summary>Timing libs, hierarchical vs flat synthesis and efficient flop coding styles</summary>
<br>
	
[](https://github.com/udayM-design/pes_asic_class#links-for-easy-navigaton)
### Introduction to timing.libs (Lab4)
```
gvim ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
```
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/eafd0075-282a-458f-a0a8-9c993f7cc8fa)
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/cbd8c9d3-e0b0-4c08-8cde-4a815e4a9210)
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/8a25284b-2d79-4b1b-9833-b5aab0d9660c)
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/0a496974-d449-4dad-8b88-c704dac01542)

### Hierarchical vs Flat synthesis
```
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files
gvim multiple_modules.v
```
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/f43e2444-9fc9-4ddd-a083-af51cb1cf2c6)

```
yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog multiple_modules.v
synth -top multiple_modules
```
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/d7c27269-274f-4b20-9e1f-3f5cdaf69bc6)
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/b3c60312-1f00-4c1b-bb7d-ccd4e0bf6569)
```
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show multiple_modules
```
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/11648dce-1050-4e91-b440-a0217bcd4260)

```
write_verilog -noattr multiple_modules_hier.v
!gvim multiple_modules_hier.v
```
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/f4efe289-e114-44af-be14-73c4bc83ce96)
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/c47f6c2a-b749-4700-9a9a-2866e216d64d)

### Flat Synthesis
```
yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog multiple_modules.v
synth -top multiple_modules
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
flatten
show
```
![image](https://github.com/udayM-design/pes_asic_class/assets/93391726/cb2a4bcd-2f31-4786-b78f-0dc15501aaed)

</details>
</details>


