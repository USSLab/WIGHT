# What is WIGHT?
Capacitive touchscreens have become essential interfaces for humans to interact with a variety of consumer electronics, e.g., smartphones, tablets, and even vehicles, reliable touch operation becomes critical for usability and security. “Ghost Touch” indicates the phenomena that a touchscreen outputs fake touches and starts to control the device by itself yet users impose no physical contacts on the screen at all. Unlike existing work that injects ghost touches by conducting radiated EMI over the air or employing a malicious software, we propose WIGHT that can induce malicious touches on the touchscreen by injecting conducted EMI into the charging cable without accessing the USB data line.

# Overview of the principle of WIGHT

WIGHT first injects a crafted common-mode signal into the GND line of the charging cable, and then the common-mode signal will be converterd into a differential-mode signal due to the asymmetric circuits in the touch controller. Then, the differential-mode signal will interfere with the capaitance measurement. Once the output signal of the sensing circuit exceeds the threshold, ghost touches will be detected.

# How dose human touch work?
When a human touches a touchscreen, the capacitance of the touchscreen will be changed due to finger contacts, and then the output voltage of the sensing circuit will change and it is proportional to the capacitance variation. Once the output voltage exceeds the threshold, a finger touch will be detected.

# How does WIGHT Work?
* How can conducted EMI trigger ghost touches?


* How to inject controlled ghost touches? 

# Demo Videos
The full demo videos can be found at WIGHT Demo Link
* Controlling devices: Pick up an eavesdropping phone call

* Misdirecting options: Change user's original touch operation and open an unintended website

* Blocking operations:Disable smartphone's touch services

# Evaluation of WIGHT
We validated the effectiveness of WIGHT on 9 commercial touchscreen devices, 13 charging cables, and 6 power adapters.
* Physical implementation of WIGHT
* Overall performance

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
|Ubiquitous System Security Laboratory (USSLab)|Zhejiang University|Technical University of Darmstadt|
|:---|:---|:---|
|列1的内容1|列2的内容1|列2的内容1|




