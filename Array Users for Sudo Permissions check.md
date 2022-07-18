#Get Home UserNames
ls ~/../ -l | awk -F' ' '{print $4}' > ~/research/John/names

#For all machine users!
awk -F':' '{ print $1}' /etc/passwd > ~/research/John/names

#Script:

#!/bin/bash

Username="$HOME/research/John/names"
declare -a array
array=(`cat "Username"`)

for i in "${array[@]}"; do sudo -lU $i; done

#End Script

./Script.sh > $HOME/research/John/Sudo_Permissions