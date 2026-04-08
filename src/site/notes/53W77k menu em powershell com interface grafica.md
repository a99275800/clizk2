---
{"dg-publish":true,"permalink":"/53-w77k-menu-em-powershell-com-interface-grafica/","dg-note-properties":{}}
---


<!--tiddlyhead title: 53W77k      
tags: #tech #powershell   
tiddlyhead-->

## 53W77k menu em powershell com interface gráfica 
function show-menu { 
[void][reflection.assembly]::Load('System.Windows.Forms, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089')␀ 㴀  ✀✀
$combobox1 = New-Object 'System.Windows.Forms.ComboBox' 
 ␀ 㴀 笀
$script:var = $combobox1.SelectedItem␀⠀
} 
 ␀⠀␀
$formShowmenu.AutoScaleDimensions = '6, 13'␀ 㴀 ✀✀
$formShowmenu.ClientSize = '284, 70' 
# add array of items嬀␀⠀  　
 ℀  
![void]$combobox1.Items.Add('Single Item') 
$combobox1.Location = '45, 25'␀ 㴀 ✀ ✀
$combobox1.add_SelectedIndexChanged($combobox1_SelectedIndexChanged) 
$formShowmenu.ShowDialog() | out-null 
write-output $var紀
show-menu
