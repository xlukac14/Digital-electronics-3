# Lab assignment 08- Traffic light controller

Link to my repository: [tmarcak/Digital-electronics-1](https://github.com/tmarcak/Digital-electronics-1)

## 1. Preparation tasks

### State table  

| **Input P** | `0` | `0` | `1` | `1` | `0` | `1` | `0` | `1` | `1` | `1` | `1` | `0` | `0` | `1` | `1` | `1` |
| :-- | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| **Clock** | ![](Images/eq_uparrow.png) | ![](Images/eq_uparrow.png) | ![](Images/eq_uparrow.png) | ![](Images/eq_uparrow.png) | ![](Images/eq_uparrow.png) | ![](Images/eq_uparrow.png) | ![](Images/eq_uparrow.png) | ![](Images/eq_uparrow.png) | ![](Images/eq_uparrow.png) | ![](Images/eq_uparrow.png) | ![](Images/eq_uparrow.png) | ![](Images/eq_uparrow.png) | ![](Images/eq_uparrow.png) | ![](Images/eq_uparrow.png) | ![](Images/eq_uparrow.png) | ![](Images/eq_uparrow.png) |
| **State** | A | A | B | C | C | D | A | B | C | D | B | B | B | C | D | B |
| **Output R** | `0` | `0` | `0` | `0` | `0` | `1` | `0` | `0` | `0` | `1` | `1` | `0` | `0` | `0` | `0` | `1` |

### Figure with connection of RGB LEDs on Nexys A7 board

![](Images/figure_board.png)

### Table with color settings

| **RGB LED** | **Artix-7 pin names** | **Red** | **Yellow** | **Green** |
| :-: | :-: | :-: | :-: | :-: |
| LD16 | N15, M16, R12 | `1,0,0` | `1,1,0` | `0,1,0` |
| LD17 | N16, R11, G14 | `1,0,0` | `1,1,0` | `0,1,0` |

### 2. Traffic light controller

