# CS2 一鍵靜走 cfg

實現按一次靜走鍵可保持靜走，按開火或蹲鍵可解除，靜走時放大雷達，解除時恢復雷達，可用來辨識目前處於何種狀態

2024/08/28   紀錄一下 好久沒摸CFC了

///Walk MODE  
alias walktoggle "walk" 

alias +attackaction "alias t +attackaction_t"
alias -attackaction "alias t -attackaction_t"
alias +attackaction_t "-attack; +attack; -attack; -attack2"
alias -attackaction_t ""

alias +duckaction "alias t +duckaction_t"
alias -duckaction "alias t -duckaction_t"
alias +duckaction_t "-duck; +duck; +duck; +duck; -duck;"
alias -duckaction_t "-duck; -duck; -duck;"


alias run "-sprint; cl_radar_scale 0.3; enable_strafe; RF_READY; alias walktoggle walk; developer 1; echo --==RUN==--; developer 0 ; say_team --==RUN==-- "
alias walk "+sprint; cl_radar_scale 1; disable_strafe; bind mouse1 +wakeup; bind SHIFT +duckup; restore_hud_color cl_hud_color 9; cl_hud_color 9; alias walktoggle run; developer 1; echo --==WALK==--; developer 0 ; say_team --==WALK==-- "
alias +wakeup "+attackaction; -sprint; cl_radar_scale 0.3; enable_strafe; developer 1; echo --==RUN==--; developer 0 ; say_team --==RUN==-- "
alias -wakeup "-attackaction; RF_READY; alias walktoggle walk"
alias +duckup "+duckaction; -sprint; cl_radar_scale 0.3; enable_strafe; restore_hud_color; developer 1; echo --==RUN==--; developer 0 ; say_team --==RUN==-- "
alias -duckup "-duckaction; bind SHIFT +duck; alias walktoggle walk"

bind "ANYKEY" "walktoggle"



以上內容調用上課上課下課下課up主的小槍cfg，單獨使用可能導致無效

以知bug 按開火鍵解除後會有一個指令差的延遲

經調用up主的 Async ByPass Tick 成功解決BUG問題 ----08/31--
