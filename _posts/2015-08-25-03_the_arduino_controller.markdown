---
layout:     post
title:      "03.Arduino控制器"
subtitle:   "开源硬件，激发创造的热情。"
date:       2015-08-25 12:00:00
author:     "littleJames"
header-img: "img/post-bg-03.jpg"
---

<p>嵌入式开发，是我一直想做的事情。Arduino是一个好的选择，参加几次开发的公开课，就可以上手了。</p>

<span class="caption text-muted">参加公开课的，来自各个行业的不同职业的从业者:中小学生、电气工程师、艺术院校学生、职业经理人、商人... ...</span>

<p>我们的目标：做一个可以同时控制40支泡泡枪的控制器。并采用声控的交互方式。</p>

<span class="caption text-muted">想像一下，站在一面墙前，对着墙大声喊：“出来！”，40支泡泡枪同时响应的情形。Nice!</span>

<h2 class="section-heading">系统原理</h2>

<p> 设计思路：控制器+声控模块+舵机驱动板+泡泡枪（内置舵机）。</p>
<a href="#">
    <img src="{{ site.baseurl }}/img/post-03-the_system_diagram.jpg" alt="Post the system diagram">
</a>
<span class="caption text-muted">图01：控制系统框图</span>

<h3>控制器</h3>
<p>控制器，采用ArduinoUno R3。这是一款成熟的开发板，开发资源丰富。</p>

<a href="#">
    <img src="{{ site.baseurl }}/img/post-03-arduinouno_r3.jpg" alt="Post the arduinoUno r3 board diagram">
</a>

<span class="caption text-muted">图02：ArduinoUno R3开发板的外观图和参数说明</span>

<h3>舵机板</h3>
<p>ArduinoUno R3，仅有6个PWM输出，需要额外扩展舵机控制板。选用PCA9685的芯片方案，一个舵机板可以输出16路PWM，40路PWM需要串连3个舵机板。</p>

<a href="#">
    <img src="{{ site.baseurl }}/img/post-03-arduino+pca9685.jpg" alt="Post the arduino+pca9685 diagram">
</a>

<span class="caption text-muted">图03：ArduinoUno R3与PCA9685舵机板连接。</span>
<span class="caption text-muted">其中，ArduinoUno R3的引脚A4和引脚A5，用作I2C总线的SDA和SCL，与舵机板直接连接。</span>

<h3>声控模块</h3>

<p>采用通用的Arduino声音识别模块。模块连接到Arduino的数字引脚，声音强度超过设定阀值，模块输出高低电平。</p>

<a href="#">
    <img src="{{ site.baseurl }}/img/post-03-sound_sensor.jpg" alt="Post the sound sensor">
</a>

<span class="caption text-muted">图04：Arduino声音识别模块</span>


<h2 class="section-heading">原型实现</h2>

<p>我们用万用板做了一个控制器原型。</p>
<a href="#">
    <img src="{{ site.baseurl }}/img/post-03-the_controller_board.jpg" alt="Post the controller board made by hand">
</a>

<span class="caption text-muted">图05：控制器原型 将ArduinoUno R3与舵机板集成。</span>

<p>加上电源接口板，控制器在系统中运行良好。</p>

<a href="#">
    <img src="{{ site.baseurl }}/img/post-03-the_control_system.jpg" alt="Post the control system">
</a>

<span class="caption text-muted">图06：控制器与系统连接，运行效果良好。</span>

<h2 class="section-heading">小结</h2>

<p>本项目制作的控制器，在工程中使用，每天开机8小时，各项功能运行正常。</p>


<span class="caption text-muted">Perfect Bubble Wall, Made in China. ———— by littleJames, Fukun Wang 2015-08-25</span>
