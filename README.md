# proc
Управление процессами

## Пишем скрипт для вывода состояния процессов системы из ФС /proc
Показывает имена всех процессов в системе, их текущее состояние, ID процесса и ID процесса родителя: \
root@Ubuntu22:~# grep -h -e Name -e State -e ^Pid -e PPid /proc/*/status | awk '{printf $0; if (NR % 4 == 0) printf "\n"}'

## Скрипт для вывода открытых файлов в системе (lsof)

root@Ubuntu22:~# cat /proc/*/maps | grep -E "\.so" | awk '{print $6}' | uniq
