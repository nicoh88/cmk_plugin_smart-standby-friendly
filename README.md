# cmk_plugin_smart-standby-friendly

ORIGINAL: https://github.com/tribe29/checkmk/blob/master/agents/plugins/smart

Das Check_MK Agent-Plugin wurde von mir stark vereinfacht und es funktioniert mit normalen SATA Festplatten. Die S.M.A.R.T Werte werden unter `/tmp` zwischengespeichert und wenn sich die besagte Festplatte im Standby befindet, werden diese Werte ausgelesen und somit wird die Festplatte nicht ständig durch ein `smartctl -a` aus dem Standby geweckt.

Über den Befehl `hdparm` wird, wenn sich die Festplatte im Standby befindet, die aktuelle Temperatur ausgelesen und der zwischengespeicherte S.M.A.R.T Wert `Temperature_Celsius` angepasst.