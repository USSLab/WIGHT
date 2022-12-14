# What is WIGHT?
Capacitive touchscreens have become essential interfaces for humans to interact with a variety of consumer electronics, e.g., smartphones, tablets, and even vehicles, reliable touch operation becomes critical for usability and security. “Ghost Touch” indicates the phenomena that a touchscreen outputs fake touches and starts to control the device by itself yet users impose no physical contacts on the screen at all. Unlike existing work that injects ghost touches by conducting radiated EMI over the air or employing a malicious software, we propose WIGHT that can induce malicious touches on the touchscreen by injecting conducted EMI into the charging cable without accessing the USB data line. WIGHT can achieve three types of attacks: injection attacks that create ghost touches without users touching the screen, alteration attacks that change the detected legitimate touch position, and Denial-ofService attacks that prevent the device from identifying legitimate touches.

# Overview of the principle of WIGHT
WIGHT first injects a crafted common-mode signal into the GND line of the charging cable, and then the common-mode signal will be converterd into a differential-mode signal due to the asymmetric circuits in the touch controller. Then, the differential-mode signal will interfere with the capaitance measurement. Once the output signal of the sensing circuit exceeds the threshold, ghost touches will be detected.
<img src="https://github.com/yanjiang98/WIGHT/blob/main/images/overview.png" width="800px">

# How dose human touch work?
When a human touches a touchscreen, the capacitance of the touchscreen will be changed due to finger contacts, and then the output voltage of the sensing circuit will change and it is proportional to the capacitance variation. Once the output voltage exceeds the threshold, a finger touch will be detected. To comparison, WIGHT cannot touch the screen and cannot change the screen capacitance. Instead, she can change the output voltage by disturbing the excitation signals and affecting how the sensing circuit measures the capacitance changes.
<img src="https://github.com/yanjiang98/WIGHT/blob/main/images/touchscreenwork.jpg" width="600px">

# How does WIGHT Work?
## How can conducted EMI trigger ghost touches?
#### 1. CM-DM conversion in asymmetric circuits
CM-DM conversion strategy indicates that a common-mode signal converts into a differential-mode signal or vice versa in asymmetric circuits. Due to the non-linear characteristics of the RLC series circuit, a CM signal flowing into a circuit with non-linear hardware components will have different phase delay and magnitude decay rate. WIGHT injects CM signal and disturbs the capacitance measurement by utilizing the asymmetric circuit in the touch controller and adding a DM signal at the excitation signal.

#### 2. Signal enhancement

(1) Signal frequency: By sweeping the attack signal in different frequencies with the same magnitude, the frequency of the attack signal closes to the excitation signal, the changes of capacitance can reach the maximum value, which is named the vulnerable frequency.
 
(2) Signal type: As a square-wave consists of multiple harmonics /hɑrˈmɑnɪks/ while a sine-wave only consists of a single frequency, the energy of the sine-wave is more concentrated at the vulnerable frequency. so WIGHT suggests using sine-wave as the attack signal.

(3) Signal magnitude: WIGHT recommends selecting stronger attack signals within the power limitation of attack devices.
<img src="https://github.com/yanjiang98/WIGHT/blob/main/images/enhance.jpg" width="600px">


## How to inject controlled ghost touches? 
#### 1. Signal synchronization
(1) Active synchronization: If the smart device can adaptively adjust its refresh rate, WIGHT can inject an activation signal to let the smart device rescan the touchscreen such that she can actively obtain the timing information of the excitation signal.

(2) Ppassive synchronization: Otherwise, WIGHT can passively extract the synchronization signal from the radiated EMI or conducted EMI of the touchscreen.

<img src="https://github.com/yanjiang98/WIGHT/blob/main/images/synchronization.jpg" width="600px">


#### 2. Touch Event Generation
To create desired touch event, WIGHT needs to know where the target positions of touches are and when to inject attack signals. For instance, if WIGHT wants to create fake touches to click the "YES" button, WIGHT first needs to estimate the position of the button and calculate which TX should be attacked, and then WIGHT can inject the attack signal when the target TX is excited.

<img src="https://github.com/yanjiang98/WIGHT/blob/main/images/toucheventcreation.jpg" width="600px">




# Demo Videos
The full demo videos can be found at [WIGHT Demo Link](https://sites.google.com/view/jytest2022/%E9%A6%96%E9%A1%B5).
* Controlling devices: Pick up an eavesdropping phone call
* Controlling devices: Connect an AirPods
* Misdirecting options: Change user's original touch operation and open an unintended website
* Blocking operations: Disable smartphone's touch services



# Evaluation of WIGHT
We validated the effectiveness of WIGHT on 9 commercial touchscreen devices, 13 charging cables, and 6 power adapters.
* Physical implementation of WIGHT
<img src="https://github.com/yanjiang98/WIGHT/blob/main/images/physical setup.png" width="600px">

* Overall performance
<img src="https://github.com/yanjiang98/WIGHT/blob/main/images/overallperformance.jpg" width="600px">


# Contact
* Prof. Wenyuan Xu (wyxu@zju.edu.cn)
* Prof. Xiaoyu Ji (xji@zju.edu.cn)
* Prof. Ahmad-Reza Sadeghi (ahmad.sadeghi@trust.tu-darmstadt.de)
* Ms.Yan Jiang (yj98@zju.edu.cn)


# Citation
```
@inproceedings{jiang2022wight,
  title={WIGHT: Wired Ghost Touch Attack on Capacitive Touchscreens},
  author={Jiang, Yan and Ji, Xiaoyu and Wang, Kai and Yan, Chen and Mitev, Richard and Sadeghi, Ahmad-Reza and Xu, Wenyuan},
  booktitle={2022 IEEE Symposium on Security and Privacy (SP)},
  pages={1537--1537},
  year={2022},
  organization={IEEE Computer Society}
}
```

# Powered by
| [Ubiquitous System Security Laboratory (USSLab)](http://usslab.org/) | [System Security Lab](https://www.informatik.tu-darmstadt.de/systemsecurity/system_security_lab_sys/index.en.jsp) |
| :----: | :----: |
| <img src="https://github.com/yanjiang98/WIGHT/blob/main/images/usslab.png" width="250px"> | <img src="https://github.com/yanjiang98/WIGHT/blob/main/images/ssl.jpg" width="200px"> | 
| Zhejiang University | Technical University of Darmstadt | 
| <img src="https://github.com/yanjiang98/WIGHT/blob/main/images/zju.jpg" width="220px"> | <img src="https://github.com/yanjiang98/WIGHT/blob/main/images/Technical University of Darmstadt.jpg" width="200px"> |

# Paper download
[WIGHT: Wired Ghost Touch Attack on Capacitive Touchscreens](https://ieeexplore.ieee.org/document/9833740)
