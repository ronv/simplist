---
date: 2019-12-26
description: Tips to improve Photoshop performance
summary: Tips to improve Photoshop performance
categories:
- article
tags:
- photoshop
title: Speed up Photoshop
---
Photoshop was running a bit sluggish on my Mac recently, luckily there are several settings you can tweak to get the best performance on your machine without compromising too much in terms of usage.

### Memory

You can improve performance by increasing the amount of memory allocated to Photoshop. The Memory Usage area of the Performance preferences screen tells you how much RAM is available to Photoshop. It also shows the ideal Photoshop memory allocation range for your system. By default, Photoshop uses 70% of available RAM. To change the amount of allocated memory go to (Windows) Edit > Preferences > Performance or (Mac OS) Menu Photoshop > Preferences > Performance. If possible, you should use 64-bit Photoshop version, which allows allocating up to 100% of memory for your work.

### Page file

The best option is to use a separate disk as a page file. The ideal variant is to use SSD disks, which are much faster than their HDD prototypes. However, even the usage of general HDD will reload the primary drive, which will be busy only with OC work. You can choose the hard drive for the page file in the same menu (Windows) Edit > Preferences > Performance or (Mac OS) Menu Photoshop > Preferences > Performance.

### Limit history states

Photoshop can save up to 1,000 history states; the default number is 20. To reduce that number, go to the Performance preference dialog box, choose History & Cache > History States. In the History States pop-up menu, if necessary, drag the setting to a lower value.

### Cache size

Increasing cache levels improves Photoshop’s responsiveness while you work, although images may take longer to load. The cache tile size determines the amount of data on which Photoshop operates at a time. Adjust the following setting according to your use. History & cache size allows you to undo the changes for images. 

### Purge history

You can quickly purge all the history states and any information you have on your clipboard by going to Edit > Purge > All (Hold down Option (Mac OS) or Alt (Windows) and choose About Photoshop). It is especially useful if you use lots of history states and you copy large images. If you want Photoshop to always use less memory, choose Edit > Preferences > Performance (Windows) or Photoshop > Preferences > Performance (Mac OS) and move the Memory Usage slider to the left.

### Turn off panel previews

Turning off the thumbnail previews will accelerate Photoshop, but might make it more difficult to find layers if you are not organised. If you are regularly naming and grouping your layers you shouldn't find it difficult to find them even without seeing the thumbnail previews. To minimize or disable these thumbnail previews, click the Panel menu and choose Panel Options. Select a smaller thumbnail size or select None, and then click OK.

### Close unused document windows

If you have several windows open, try closing some of them. Each open file can take up a significant amount of memory, which can quickly lead to slow downs. If you receive an “out of RAM” error message or if Photoshop is running slowly, it could be caused by having too many open images. 

### Efficiency Indicator

You can keep an eye on the efficiency level of Photoshop if you choose Efficiencyfrom the status bar options at the bottom of the document window. The efficiency indicator can help you determine whether getting a faster hard disk or solid-state disk would improve your performance. If the efficiency number is usually above 95%, spending money on a faster scratch disk has little benefit. 

### GPU settings

Photoshop can really take advantage of GPU accelerated features for improved processing and you can adjust your setup considerably in the preference settings. The best way to optimize GPU acceleration, which speeds up screen redraws, is to keep your video adapter driver up to date.

### Turn off font preview

To speed font processing in Photoshop, turn off the WYSIWYG font preview list by choosing Type > Font Preview Size > None.

### 8-bit image mode

Photoshop can perform many operations on 16-bit and 32-bit images. For tasks that are not related to professional photo correction and preparation for print, it's enough to work with 8-bit images. To convert your image to 8 bits per channel, choose Image > Mode > 8 Bits/Channel.
