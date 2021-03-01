# Lab assignment 03- Vivado

Link to my repository: [tmarcak/Digital-electronics-1](https://github.com/tmarcak/Digital-electronics-1)

## 1. Preparation task

### Table  

| **LED** | **Connection** | **Switch** | **Connection** | 
| :-: | :-: | :-: | :-: |
| LED0 | H17 | SW0 | J15 |
| LED1 | K15 | SW1 | L16 |
| LED2 | J13 | SW2 | M13 |
| LED3 | N14 | SW3 | R15 |
| LED4 | R18 | SW4 | R17 |
| LED5 | V17 | SW5 | T18 |
| LED6 | U17 | SW6 | U18 |
| LED7 | U16 | SW7 | R13 |
| LED8 | V16 | SW8 | T8 |
| LED9 | T15 | SW9 | U8 |
| LED10 | U14 | SW10 | R16 |
| LED11 | T16 | SW11 | T13 |
| LED12 | V15 | SW12 | H6 |
| LED13 | V14 | SW13 | U12 |
| LED14 | V12 | SW14 | U11 |
| LED15 | V11 | SW15 | V10 |

## 2. Multiplexer

### Architecture (`mux_2bit_4to1.vhd`)

```vhdl
architecture Behavioral of mux_2bit_4to1 is
begin
    f_o   <= a_i when (sel_i = "00") else 
             b_i when (sel_i = "01") else
             c_i when (sel_i = "10") else
             d_i;
	
end architecture Behavioral;
```

### Stimulus process (`tb_mux_2bit_4to1.vhd`)

```vhdl
 p_stimulus : process
    begin
        
        report "Stimulus process started!" severity note;

        s_a <= "00"; s_b <= "00"; s_c <= "00"; s_d <= "00"; 
        s_sel <= "00"; wait for 100 ns;
        
        s_a <= "00"; s_b <= "01"; s_c <= "01"; s_d <= "10"; 
        s_sel <= "00"; wait for 100 ns;
        
        s_a <= "11"; s_b <= "01"; s_c <= "01"; s_d <= "10"; 
        s_sel <= "00"; wait for 100 ns;
        
        s_a <= "00"; s_b <= "01"; s_c <= "01"; s_d <= "10"; 
        s_sel <= "01"; wait for 100 ns;
        
        s_a <= "00"; s_b <= "11"; s_c <= "01"; s_d <= "10"; 
        s_sel <= "01"; wait for 100 ns;
        
        s_a <= "00"; s_b <= "11"; s_c <= "01"; s_d <= "10"; 
        s_sel <= "10"; wait for 100 ns;
        
        s_a <= "00"; s_b <= "11"; s_c <= "01"; s_d <= "10"; 
        s_sel <= "11"; wait for 100 ns;
        
        
        report "Stimulus process finished!" severity note;
        wait;
    end process p_stimulus;
```


### Simulated Time Waveforms

![](Images/waveforms1.png)


## 3. A Vivado Tutorial

### Create a new project 

1. Open Vivado 2020.2

2. Create a project 
![](Images/screen_1.png)

3. Create a new project -> Next
![](Images/screen_1.1.png)

4. Fulfill project name and project location -> Next
![](Images/screen_1.2.png)

5. Check RTL Project -> Next
![](Images/screen_1.3.png)

6. In Add Sources click on "Create file"
![](Images/screen_1.4.png)

7. Create source file, fulfill File type (VHDL) and project name -> OK
![](Images/screen_1.5.png) 

8. Target language and Simulator laguage (VHDL) -> Next
![](Images/screen_1.6.png)

9. Add Constraints is optional -> Next
![](Images/screen_1.7.png)

10. In default part we click on boards and pick Nexys A7-50T -> Next
![](Images/screen_1.8.png)

11. We can see our New Project summary -> Finish
![](Images/screen_1.9.png)

12. Define module -> OK
![](Images/screen_1.10.png)

13. In Design Sources we can see our design "comparator_2bit.vhd" 
![](Images/screen_1.11.png)

### Creation of Simulation Sources 

1. File -> Add Sources
![](Images/screen_1.12.png)

2. Check Simulation sources -> Next
![](Images/screen_1.13.png)

3. Create File -> Fulfill File Type (VHDL) and File Name
![](Images/screen_1.14.png)

4. Finish
![](Images/screen_1.15.png)

5. Define Module -> OK
![](Images/screen_1.16.png)

6. We can see our file in Simulation Sources -> Open 
![](Images/screen_1.17.png)

![](Images/screen_1.18.png)

### Simulation

1. Click on Flow -> Run Simulation -> Run Behavioral Simulation
![](Images/screen_1.19.png)

2. Wait 
![](Images/screen_1.20.png)

3. Example of simulation 
![](Images/screen_1.21.png)



