#Task 1: For Loop

    # forloop.sh
    #/bin/bash
    for a in 1 2 3 4 5 6 7 8 9 10
    do
        # if a = 5 then continue the loop and 
        # don't move to line 8
        if [ $a == 5 ]
        then 
            continue
        fi
        echo "Iteration no $a"
    done  
    
    #count.sh
    #!/bin/bash
    a=0
    while [ $a -lt 10 ]
    do
        echo $a
        a= `expr $a + 1`
    done

#Task 2: While Loop
    # CountDown.sh
    #/bin/bash
    for a in 1 2 3 4 5 6 7 8 9 10
    do
        # if a = 5 then continue the loop and 
        # don't move to line 8
        if [ $a == 5 ]
        then 
            continue
        fi
        echo "Iteration no $a"
    done

#Task 3: Command-Line Arguments
    #/bin/bash
    for a in 1 2 3 4 5 6 7 8 9 10
    do
        # if a = 5 then continue the loop and 
        # don't move to line 8
        if [ $a == 5 ]
        then 
            continue
        fi
        echo "Iteration no $a"
    done

    #/bin/bash
    for a in 1 2 3 4 5 6 7 8 9 10
    do
        # if a = 5 then continue the loop and 
        # don't move to line 8
        if [ $a == 5 ]
        then 
            continue
        fi
        echo "Iteration no $a"
    done

#Task 4: Install Packages Via Scripts
    #!/bin/bash 
     
     
    for arg in $@ 
    do 
            if [[ $(dpkg -s $arg | awk '/Status/ {print $3}') == "ok" ]]; then 
                    echo "$arg is already installed" 
            else 
                    sudo apt install $arg -y > /dev/null             
                    echo "package is installed $arg" 
            fi  
    done 

#Task 5: Error Handling
    #!/bin/bash

    set -e

    mkdir -p /tmp/devops-test

    cd /tmp/devops-test 

    touch first-file 

