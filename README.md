# Allure Environment builder

Библиотека для создания файла с переменными окружения для allure-report-service

## Установка

```shell
pip install allure-env-builder
```

## Использование

В библиотеке есть единственный класс `AllureEnvironmentsBuilder`,
с помощью которого можно
создать [файлик с переменными окружения](https://allurereport.org/docs/how-it-works/environment-file/) для
сервиса [Allure Report](https://allurereport.org/)

```python
from allure_env_builder import AllureEnvironmentsBuilder

if __name__ == '__main__':
    output = (
        AllureEnvironmentsBuilder()
        .add('key_1', 'value_1')
        .add('key_2', 'value_2')
        .build()
    )
    print(output)
```

данный код выведет:

```properties
key_1=value_1
key_2=value_2
```

Для того чтобы сохранить данные переменные в файл, необходимо методу `build` передать путь до директории, где будет
создан файл с названием `environment.properties`

