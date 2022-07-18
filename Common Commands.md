

#Finding Files with names:

#find -type f -iname *recipe* -a -iname *peanut*


#Finding Content in files:

#grep -il slugworth email/* | wc -l >> slugworth_email_evidence


#Counting:

#wc -w *

#Install:

#sudo apt install -y cowsay fortune emacs tree

#sudo apt-update

#sudo apt-upgrade


#Replacing text:

#sed 's/]/] /' > filtered_logs1.txt


#Arraying text and pulling values with awk:

#cat access_denied.txt | awk -F' ' '{print $4$6}' > filtered_logs.txt

#Removing files:

#rm -rfd ./TempFiles

#Changing permissions
#1 execute
#2 write
#4 read

#chmod +x - gives execute

#chmod $NUM
#600 - root read/write
#070 - owner read/write/execute
#001 - group execute

#d designation at front of permissions indicates directory. - indicates file.


