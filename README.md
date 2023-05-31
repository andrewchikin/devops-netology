# devops-netology
первая запись

#В каталоге Terraform в файле .gitignore добавлены следующие исключения:

# - локальные каталоги .terraform
**/.terraform/*

# - все файлы с расширением 
*.tfstate
*.tfvars
.terraformrc

# - файлы
terraform.rc
override.tf
override.tf.json

# - все файлы содержащие в названии .tfstate.
*.tfstate.*

# - все файлы оканчивающиеся
*_override.tf
*_override.tf.json

