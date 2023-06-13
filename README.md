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


# - после git push -u origin fix


Домашнее задание к занятию «2.4. Инструменты Git»

1. Найдите полный хеш и комментарий коммита, хеш которого начинается на aefea.
Команда: 
git show aefea
Вывод:
commit aefead2207ef7e2aa5dc81a34aedf0cad4c32545
Author: Alisdair McDiarmid <alisdair@users.noreply.github.com>
Date:   Thu Jun 18 10:29:58 2020 -0400

    Update CHANGELOG.md

diff --git a/CHANGELOG.md b/CHANGELOG.md
index 86d70e3e0d..588d807b17 100644
--- a/CHANGELOG.md
+++ b/CHANGELOG.md
@@ -27,6 +27,7 @@ BUG FIXES:
 * backend/s3: Prefer AWS shared configuration over EC2 metadata credentials by default ([#25134](https://github.com/hashicorp/terraform/issues/25134))
 * backend/s3: Prefer ECS credentials over EC2 metadata credentials by default ([#25134](https://github.com/hashicorp/terraform/issues/25134))
 * backend/s3: Remove hardcoded AWS Provider messaging ([#25134](https://github.com/hashicorp/terraform/issues/25134))
+* command: Fix bug with global `-v`/`-version`/`--version` flags introduced in 0.13.0beta2 [GH-25277]
 * command/0.13upgrade: Fix `0.13upgrade` usage help text to include options ([#25127](https://github.com/hashicorp/terraform/issues/25127))
 * command/0.13upgrade: Do not add source for builtin provider ([#25215](https://github.com/hashicorp/terraform/issues/25215))
 * command/apply: Fix bug which caused Terraform to silently exit on Windows when using absolute plan path ([#25233](https://github.com/hashicorp/terraform/issues/25233))
 
2. Какому тегу соответствует коммит 85024d3?
Команда: 
git show 85024d3
или 
git show -s --oneline 85024d3
Вывод:
tag: v0.12.23

3. Сколько родителей у коммита b8d720? Напишите их хеши.
Команда: 
git show b8d720
или
git show --pretty=%P b8d720
Вывод:
56cd7859e0 9ea88f22fc
или
56cd7859e05c36c06b56d013b55a252d0bb7e158 9ea88f22fc6269854151c571162c5bcf958bee2b

4. Перечислите хеши и комментарии всех коммитов которые были сделаны между тегами v0.12.23 и v0.12.24.
Команда:
git show -s --oneline v0.12.23..v0.12.24
Вывод:
33ff1c03bb (tag: v0.12.24) v0.12.24
b14b74c493 [Website] vmc provider links
3f235065b9 Update CHANGELOG.md
6ae64e247b registry: Fix panic when server is unreachable
5c619ca1ba website: Remove links to the getting started guide's old location
06275647e2 Update CHANGELOG.md
d5f9411f51 command: Fix bug when using terraform login on Windows
4b6d06cc5d Update CHANGELOG.md
dd01a35078 Update CHANGELOG.md
225466bc3e Cleanup after v0.12.23 release
	
	
5. Найдите коммит в котором была создана функция func providerSource, ее определение в коде выглядит так func providerSource(...) (вместо троеточего перечислены аргументы).
Команда:
git log -S"func providerSource(" --oneline
Вывод:
8c928e8358 main: Consult local directories as potential mirrors of providers

6. Найдите все коммиты в которых была изменена функция globalPluginDirs.
Ищем файл, где есть функция
Команда:
git grep "func globalPluginDirs("
Вывод:
plugins.go:func globalPluginDirs() []string {

Ищем коммиты с изменением этой функции в файле plugins.go
Команда:
git log -s -L :globalPluginDirs:plugins.go --oneline
Вывод:
78b1220558 Remove config.go and update things using its aliases
52dbf94834 keep .terraform.d/plugins for discovery
41ab0aef7a Add missing OS_ARCH dir to global plugin paths
66ebff90cd move some more plugin search path logic to command
8364383c35 Push plugin discovery down into command package

7. Кто автор функции synchronizedWriters?
Команда:
git log -S"func synchronizedWriters(" --oneline
Вывод:
bdfea50cc8 remove unused
5ac311e2a9 main: synchronize writes to VT100-faker on Windows

git show bdfea50cc8 - тут функция удалена
git show 5ac311e2a - тут функция добавлена

Автор Martin Atkins <mart@degeneration.co.uk>

