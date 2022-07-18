
#Static filled arrays:

#!/bin/bash

array=('133.18.55.255' '41.34.55.255' '187.54.23.8')
for i in "${array[@]}"; do /bin/bash ./IP_lookup.sh $i; done


#List of Array:



#Array on the fly:

#Make Temp files with split data: Date and Times in question
awk '{print $1}'  ../Player_Analysis/Dates_and_times > ./TempFiles/Dates
awk '{print $2, $3}'  ../Player_Analysis/Dates_and_times > ./TempFiles/Times
​
#Create columns for the array with files
readarray -t Dates < ./TempFiles/Dates
readarray -t Times < ./TempFiles/Times
​
#count holder
i=0;
​
#Establish count max value and increment through 
for Date in "${Dates[@]}";
​
#Start loop
do
​
#This echo was testing value reflection was working right.
#echo "The date this loss is on is ${Dates[$i]} at ${Times[$i]}";
​
#grep the files to find those working at that time. " is needed to grab full time value or am/pm is ambiguous
#grep -i "${Times[$i]}"  ./${Dates[$i]}*  
​
#Output show Billy Jones in the Roulette collumn for all these times but let's pull that with awk since we know it is a unique column.
#grep "${Times[$i]}"  ./${Dates[$i]}* | awk -F' ' '{print $1, $2, $5, $6}'
​
#Can we add the date back to the start of this output? Yes we can!
Date=`echo ${Dates[$i]}`
​
Evidence=`grep "${Times[$i]}"  ./${Dates[$i]}* | awk -F' ' '{print $1, $2, $5, $6}'`
#Test success output the requested info to file
echo $Date $Evidence >> Dealers_working_during_losses
​
​
#Increment counter
let "i=i+1"
​
#end of loop
done