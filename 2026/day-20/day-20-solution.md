#Task 1,2,3,4,5: The underline code contain all the task solution fined it by yourself, Thank you 
    #!/bin/bash

    #./log_analyzer.sh <log_file_path>

    Date=$(date +%Y-%m-%d)
    $(touch log_reporte_${Date}.txt)

    if [[ $# -lt 1 ]]; then
            echo 'please provide the correct format'
            echo './log_analyzer.sh <log_file_path> <num_lines>'
    fi

    log_file_path=$1

    if [[ -e "$log_file_path" ]]; then
            echo "Exist"
    else
            echo "File does not exist"
    fi

    count=$(grep -c -E "ERROR|Failed" log_file)
    echo "$count" >> log_reporte_${Date}.txt
    echo "Total no of ERROR and Failed are: ${count}"

    echo "---- Critical Events ----"
    echo "$(awk '/CRITICAL/ {print NR, $0}' log_file)" >> log_reporte_${Date}.txt

    #echo $(awk '{c[$4]++} END{for (i in c) print i, c[i]}' log_file) 

    echo "---- Top 5 Error messsages are ----"

    echo "$(awk '$4 == "-" { next } {print $4, $5, $6}' log_file | sort | uniq -c)" >> log_reporte_${Date}.txt
