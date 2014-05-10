#This is a Proxy Toggle bulit by applescript for Mac 10.7.5 to switch on and off the GAE proxy. Thanks to Kacey Coughlin for your guidence!
#这是一个用AppleScript做的GAE翻墙软件的开关。适用于Mac 10.7.5 软件会自动勾选系统设置的代理开关，运行Terminal来执行Proxy.py


tell application "System Preferences"
	activate
	set the current pane to pane id "com.apple.preference.network"
	reveal anchor "Proxies" of pane id "com.apple.preference.network"
end tell

tell application "System Events"
	tell table 1 of scroll area 1 of group 1 of tab group 1 of sheet 1 of window "Network" of process "System Preferences"
		delay 0.05
		select row 3
		tell row 3
			click checkbox 1
		end tell
		select row 4
		tell row 4
			click checkbox 1
			set isTure to value of checkbox 1
		end tell
	end tell
	click button "OK" of sheet 1 of window "Network" of process "System Preferences"
	click button "Apply" of window "Network" of process "System Preferences"
end tell

ignoring application responses
	tell application "System Preferences" to quit
end ignoring

if isTure is 1 then
	tell application "Terminal"
		do script "cd ~/goagent/local;python proxy.py"
	end tell
else
	tell application "Terminal"
		do script "killall 'Terminal'"
	end tell
end if
