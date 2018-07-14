
# Answer

1. `sort -urg /opt/CECM00201/input/colon_delimited.txt > /opt/CECM00201/output/colon_delimited.txt`
2. `cut -d',' -f2-3 /opt/CECM00201/input/comma_delimited.txt | sed 's/\(.*\),\(.*\)/\2,\1/' | sort -g | sed 's/\(.*\),\(.*\)/\2,\1/' > /opt/CECM00201/output/comma_delimited.txt`
3. `egrep -w 'root|user' /opt/CECM00201/input/user_rows.txt > /opt/CECM00201/output/user_rows.txt`
4. Pythonで頑張って。

