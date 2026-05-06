#Task 1: Basic Function
    #!/bin/bash

    greet(){
            echo "Hello, $1"        
    }

    $greet anshu

#Task 2: Function with Return Values
    #!/bin/bash

    check_disk(){
            total=$(df -h | awk  '/nvme0n1p6/ {print "Total storage: "$2
            print "Used storage: " $3 
            print "Free storage: " $4
    }')
    echo $total
    }

    check_disk
    
    #!/bin/bash
    check_disk(){
            total=$(df -h | awk  '/nvme0n1p6/ {print "Total storage: "$2
            print "Used storage: " $3 
            print "Free storage: " $4
    }')
    echo $total
    }

    check_memory(){
            memory=$(free -h | awk '/Mem:/ {print}')
            echo $memory
    }

    check_disk
    check_memory

#Task 3: Strict Mode --- `set -euo pipefail`
    Q1. Try using an undefined variable --- what happens with set -u?
    Ans. If we use variable that is not define, the script will exit with an error.
    Q2. try a comman that fails what happend with set -e?
    Ans. If any line of code give error of fails it excution of script imidiatly stop and code exit.
    Q3. try a pipe command where one part fails ---- what happen dwith set -o pipefail?
    Ans. Usually in a pipe (|), only the last command status is checked, but with pipefail the pipeline fa    ils if any command fails

#Task 4: Local Variables
    #!/bin/bash

    find_avg(){
            local sum=0
            local len="$#"

            for i in "$@"
            do
                    sum=$((sum+i))
            done
            echo $((sum/len))
    }
    AVG=$(find_avg 30 40 50 60)

    echo "$AVG"

#Task 5: Build a Script — System Info Reporter 
    #!/bin/bash

    info(){

            echo $(hostname)
            echo $(hostnamectl | awk 'NR == 6 {print}')
    }

    Uptime(){
            echo $(uptime -p)
    }

    Disk_usage(){
            echo $(df -h | awk 'NR>1 {print $1,$2,$3,$4}' | sort -hr -k3 | head -n 5)
    }

    Memory_usage(){
            echo $(free -h)
    }

    Cpu_use(){
            ps -eo pid,comm,%cpu --sort=-%cpu | head -n 6
    }


    Cpu_use

