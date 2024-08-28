# CS2 一鍵靜走 cfg
實現按一次靜走鍵可保持靜走，按開火或蹲鍵可解除，靜走時放大雷達，解除時恢復雷達，可用來辨識目前處於何種狀態

2024/08/28   紀錄一下 好久沒摸CFC了

//Walk MODE  

alias walktoggle "walk" 

alias run "-sprint; cl_radar_scale 0.3; enable_strafe; bind mouse1 +enable_rf_v5; RF_READY; alias walktoggle walk; developer 1; echo --==RUN==--; developer 0 ; say_team "

alias walk "+sprint; cl_radar_scale 1; disable_strafe; bind mouse1 +wakeup; bind SHIFT +duckup; restore_hud_color cl_hud_color 0; cl_hud_color 0; alias walktoggle run; developer 1; echo --==WALK==--; developer 0 ; say_team "

alias +wakeup "-sprint;cl_radar_scale 0.3; enable_strafe; developer 1; echo --==RUN==--; developer 0 ; say_team "

alias -wakeup "bind mouse1 +enable_rf_v5; RF_READY; alias walktoggle walk"

alias +duckup "-sprint;cl_radar_scale 0.3; enable_strafe; developer 1; echo --==RUN==--; developer 0 ; say_team "

alias -duckup "bind SHIFT +duck; alias walktoggle walk"



實現按一次靜走鍵可保持靜走，按開火或蹲鍵可解除，靜走時放大雷達，解除時恢復雷達，可用來辨識目前處於何種狀態



以上內容調用上課上課下課下課up主的小槍cfg，單獨使用可能導致無效

以知bug 按開火鍵解除後會有一個指令差的延遲，正尋求上課上課下課下課up主指導中
