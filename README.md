# GooglyPuff_Part_2
**Part2，很長篇幅都是講最佳化你的App(提升User Experience;UX)**  
For more detail, see the website:
<a href="https://www.raywenderlich.com/63338/grand-central-dispatch-in-depth-part-2">Grand Central Dispatch In-Depth: Part 2</a>


技術重點如下：  
* 如何掌控多個非同步的事件？  
在此範例中，當按下"＋"選擇從網路上下載圖片，應該等所有圖片都下載完才彈出通出視窗告知user.  
GCD API提供dispatch_group_wait來解決這個問題；  
dispatch_group_wait：Returns zero on success (all blocks associated with the group completed before the specified timeout) or non-zero on error (timeout occurred).
<div align="center">
  <img src="https://github.com/jhsiao21/GooglyPuff_Part_2/blob/master/pic.png"> 
  </div>
其他dispatch group資源：<a href="http://www.jianshu.com/p/5617ad407678">使用使用Dispatch Groups来管理多个Web Services请求</a>

* dispatch_apply: Submits a block to a dispatch queue for multiple invocations. To execute block concurrently or serially depends on dispatch queue you give.
```
dispatch_apply有點像是for loop的併行版本
```
* Dispatch Source:A particularly interesting feature of GCD is Dispatch Sources, which are basically a grab-bag of low-level functionality helping you to respond to or monitor Unix signals, file descriptors, Mach ports, VFS Nodes, and other obscure stuff. All of this is far beyond the scope of this tutorial, but you’ll get a small taste of it by implementing a dispatch source object and using it in a rather peculiar way. 
```
這邊使dispatch source來更新UI、查詢類的屬性，甚至執行方法—而且不需要重啟App並到達某個特定的工作狀態．
```


