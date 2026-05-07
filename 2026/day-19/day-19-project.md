#Task 1: Log Rotation Script
#!/bin/bash

declare -a my_array
date=$(date +%F)
for i in "$1"/*.log; do
        if [[ -f "$i" ]]; then
                if find "$i" -mtime +7 | grep -q .;then
                        my_array+=("$i")
                fi
        fi
done

if [[ ${#my_array[@]} -gt 0 ]]; then
        gzip -c "${my_array[@]}" > "${date}.gz"
        echo "compress file into this"
else
        echo "no old log file around"
fi
          

#Task 2: Server Backup Script 

    #!/bin/bash

    <<readme
    This is a script for backup with 5 day rotation

    Useage:
    ./backup.sh <path to your source> <pth to backup folder>
    readme

    function display_usage {
        echo "Useage: ./backup.sh <path to your source> <path to backup folder>"
    }

    if [ $# -eq 0 ]; then 
        display_usage
    fi

    source_dir=$1
    timestamp=$(date '+%Y-%m-%d-%H-%M-%S')
    backup_dir=$2

    create_backup(){

        zip -r "${backup_dir}/backup_${timestamp}.zip" "${source_dir}" > /dev/null
        if [[ $? -eq 0]]; then
        echo "backup generated successfully for ${timestamp}"
        fi
    }

    perform_rotation {
        backups=($(ls -t "${backup_dir}/backup_"*.zip 2>/dev/null))

        if [[ "${#backups[@]}" -gt 5 ]]; then
            echo "Performing rotation for 5 days"
            del_backup=("${backups[@]:5}")
            echo "$()"
            for backup in "${del_backup[@]}";
            do
                rm -f ${backup}
            done
        fi
    }

    create_backup

    perform_rotation

