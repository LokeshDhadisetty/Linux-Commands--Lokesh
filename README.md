find /sapdb_backups -xdev -size +1G -type f -exec ls -lhtr {} \;
 
free -h;free -m | awk '/Mem/ {print "free memory space ="($4/$2)*100"%"}';date
free -h;free | awk '/Swap/ { print "Swap usage is "($3/$2)* 100 " %"} '; date
 
ps aux --sort -rss | head -2 ; date
 
 
free -h;ps aux| awk '{print $2, $4, $11}'|head -1;ps aux | awk '{print $2, $4, $11}' | sort -k2rn | head -n 10;echo;free|awk '/Swap/ {print "Swap usage is "($3/$2)*100"%"}';date   ----- swap utilization
