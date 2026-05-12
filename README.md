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
