---
{"dg-publish":true,"permalink":"/53-w77k-menu-em-powershell-com-interface-grafica/","dg-note-properties":{}}
---


<!--tiddlyhead title: 53W77k      
tags: #tech #powershell   
tiddlyhead-->

## 53W77k menu em powershell com interface gráfica 
function show-menu { 
[void][reflection.assembly]::Load('System.Windows.Forms, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089')␀ 㴀  ✀✀
(cifrão)combobox1 = New-Object 'System.Windows.Forms.ComboBox' 
 ␀ 㴀 笀
(cifrão)script:var = (cifrão)combobox1.SelectedItem␀⠀
} 
 ␀⠀␀
(cifrão)formShowmenu.AutoScaleDimensions = '6, 13'␀ 㴀 ✀✀
(cifrão)formShowmenu.ClientSize = '284, 70' 
# add array of items嬀␀⠀  　
 ℀  
![void](cifrão)combobox1.Items.Add('Single Item') 
(cifrão)combobox1.Location = '45, 25'␀ 㴀 ✀ ✀
(cifrão)combobox1.add_SelectedIndexChanged((cifrão)combobox1_SelectedIndexChanged) 
(cifrão)formShowmenu.ShowDialog() | out-null 
write-output (cifrão)var紀
show-menu
