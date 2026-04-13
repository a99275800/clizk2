---
{"dg-publish":true,"permalink":"/59-y58j-powershell-to-display-determinadas-linhas-de-um-file/","dg-note-properties":{}}
---


<!--tiddlyhead title: 59Y58j        
tags:  #tech #powershell 
tiddlyhead-->

## 59Y58j powershell to display determinadas linhas de um file 
Display top n lines or last n lines of a file  
These commands are fairly simple in Unix shell programming and most of you must have used Head and Tail commands. Those commands work really fast and accurate.
Keeping these points in mind, I dig something and want to share will all of you.
How to use Head and Tail Commands in Powershell?
To get the top 10 lines - 尀    　
    　  
 尀    　
℀      ℀
  
          

Get-Content ".\file_test.txt" | select -First 3 | select -Last 1
Problem: Write a command to skip 10 lines from top and display rest all lines of file.
Solution: 尀    　
                   
                               

 ℀℀
at February 18, 2015   
BlogThis!  
Share to Facebook  
Labels: Powershell-Tips, Programming-Basics 
 　 　   
This comment has been removed by a blog administrator.
Reply
UnknownMay 27, 2013 at 8:20 AM      

 　 　   
to get last lines of large files use: ␀  

  　   
- tail rockz thx !
Reply
A BoothMay 28, 2015 at 7:19 AM   ␀  
✀    ✀  ℀