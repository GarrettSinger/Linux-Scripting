#Use Cat and a holder to escape the command and write it as is to file
cat <<"EOT" >> roulette_dealer_finder_by_time.sh
grep -i "$2 $3" ./$1* | awk -F" " '{print $1, $2, $5, $6}'
EOT
​