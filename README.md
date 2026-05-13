# devops-netology
HW directory
First line

## .gitignore

В репозитории игнорируются:
- локальные Terraform-директории (.terraform/)
- файлы состояния Terraform (*.tfstate)
- crash-логи Terraform
- файлы переменных (*.tfvars, *.tfvars.json)
- локальные override-конфигурации
- lock-файлы Terraform
- локальные CLI-конфиги Terraform (.terraformrc, terraform.rc)

Это позволяет не хранить в Git временные файлы, чувствительные данные и локальные настройки окружения.

## .gitignore rules description

- .terraform/ - игнорирование директории .terraform и всего её содержимого
- *.tfstate - игнорирование всех файлов с расширением .tfstate
- *.tfstate.* - игнорирование файлов, содержащих .tfstate. в имени
- crash.log - игнорирование файла crash.log
- crash.*.log - игнорирование файлов вида crash.<что-угодно>.log
- *.tfvars - игнорирование всех файлов с расширением .tfvars
- *.tfvars.json - игнорирование всех файлов с расширением .tfvars.json
- override.tf - игнорирование файла override.tf
- override.tf.json - игнорирование файла override.tf.json
- *_override.tf - игнорирование файлов, оканчивающихся на _override.tf
- *_override.tf.json - игнорирование файлов, оканчивающихся на _override.tf.json
- .terraform.tfstate.lock.info - игнорирование файла .terraform.tfstate.lock.info
- !example_override.tf - исключение файла example_override.tf из ignore
- .terraformrc - игнорирование файла .terraformrc
- terraform.rc - игнорирование файла terraform.rc
- # - комментарии, не применяются Git
