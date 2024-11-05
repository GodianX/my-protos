# my-protos


Protoc

https://grpc.io/docs/languages/go/quickstart/

генерируем через

```bash
task generate
```
или
```bash
protoc -I proto proto/sso/sso.proto --go_out=./gen/go --go_opt=paths=source_relative --go-grpc_out=./gen/go/ --go-grpc_opt=paths=source_relative
```
-I proto - это общая папка где лежат протофайлы

proto/sso/sso.proto - указываем какой протофайл

—go_out=./gen/go - куда

—go_opt=paths=source_relati сгененрированные файлы будут использовать тот же формат что и протофайлы

—go-grpc_out=./gen/go/ - куда складывать сгенерированный grpc код

--go-grpc_opt=paths=source_relative формат сгенерированных файлов

протофайлы могут быть как отлдельный проект
который мы можем подключать как отдельную библиотеку

## У проекта обятельно должен быть тег

```bash
git tag v0.0.1
```

```bash
git push origin v0.0.1
```

## Добавляем в зависимость других проектов

репозиторий должен быть public иначе нужно использовать переменную GOPRIVATE
```bash
 go get github.com/GodianX/my-protos
```