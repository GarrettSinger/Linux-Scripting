#Write script
#This grep uses the time and AM/PM as a single variable. Not as flexible Formatting needs to be precise. "00:00:00 AM/PM"
echo '#!/bin/bash' >> roulette_dealer_finder_by_time_and_game.sh
cat <<"EOT" >> roulette_dealer_finder_by_time_and_game.sh
grep -i "$2" ./$1* | awk -F" " '{print $1, $2,'$3','$4' }'
EOT