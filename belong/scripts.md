echo "start reload cct ..."
set tomcat_home=D:\devTools\apache-tomcat-7.0.63
cd /d %tomcat_home%\bin
call %tomcat_home%\bin\shutdown.bat
echo "shutdown complete ..."
echo "start update from svn"
set code_home=D:\SVN
cd /d %code_home%\CCTDB
start TortoiseProc.exe /command:update /path:%code_home%\CCTDB /closeonend:1 
echo "begin to build cctdb"
call mvn clean install
cd /d %code_home%\CCTPlatform2.1
start TortoiseProc.exe /command:update /path:%code_home%\CCTPlatform2.1 /closeonend:1 
echo "begin to build CCTPlatform2.1"
call mvn clean package
echo "begin to delete old cct ..."
del /f/s/q %tomcat_home%\webapps\cct.war
rd /s/q %tomcat_home%\webapps\cct
rd /s/q %tomcat_home%\work
echo "begin to copy new cct ..."
xcopy %code_home%\CCTPlatform2.1\target\cct.war %tomcat_home%\webapps\  /s /h /d /f /y
cd /d %tomcat_home%\bin
call %tomcat_home%\bin\startup.bat