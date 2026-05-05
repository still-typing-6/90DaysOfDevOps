#Task 1: Your First Script
    #!/bin/bash

    echo "Hello, DevOps"
    
    #What happens if you remove the shebang line?
    Ans. Nothing happens my file still runs without any error.
#Task 2: Variables
    #!/bin/bash

    NAME=anshu
    ROLE="DevOps Engineer"

    echo "Hello, I am $NAME and I am a $ROLE"
    
    #Try using single quotes vs double quotes --- what's the difference?
    Ans. If we use single quotes the variable inside it does not access by $VAR     sign.
#Task 3: User Input with read
    #!/bin/bash

    read -p "what is your name: " name

    read -p "what is your favourite tool: " tool

    echo "Hello $name, your favourite tool is $tool"
     
#Task 4: If-Else conditions
    #!/bin/bash

    read -p "enter a number: " num

    if [ "$num" -gt 0 ];
    then
        echo "positive"
    elif [ "$num" -lt 0 ];
    then
        echo "negative"
    else
        echo "zero"
    fi
#Task 5: Combine It All
    #!/bin/bash

    service=nginx

    read -p "do you want to check the status?(y/n) " consent

    if [ "$consent" == y ]; then
         systemctl status $service | awk '/Active/ {print $2}' 
    else
        echo	"skipped"
    fi

        
    
     
