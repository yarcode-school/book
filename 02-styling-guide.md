## Coding guide
### Стилевые особенности написания кода
* Следуйте стандартам [psr-1](http://www.php-fig.org/psr/psr-1/) и [psr-2](http://www.php-fig.org/psr/psr-2/).
* Используйте фигурные скобки во всех условных выражениях и циклах, даже если выполняется всего одна строка кода:

```
if (true) {
    do();
}
```
* Добавляйте phpdoc нотации для всех методов, которые вы создаете.
* Используйте @var нотации там, где тип объекта не определяется явно.
```
/**
 * @var Model $model
 */
$model = Model::find()->one();
```
## Yii
* Используйте миграции для любых изменений структуры БД
* Используйте построитель схемы в своих миграциях (http://www.yiiframework.com/news/88/yii-2-0-6-is-released/)
* Имя класса модели и имя таблицы должны быть в единственном числе. Например: таблица *user_account*, класс модели *UserAccount*.
* Именуйте поля и связи не используя излишних префиксов, например:
у вас есть модели: User, UserProfile; название связи в модели User должно быть: profile
* Именуйте view файлы в нижнем регистре с дефисами, они должны совпадать с action url контроллера. Например:
Действие some-controller/some-action. Название view файла: some-action.php
* Не стесняйтесь использовать виджеты

### Attribute labels
Please follow this coding style when using attribute labels in model. This allows you to use statusLabel as attribute in grids, you can also set getStatusLabels() as source of data for filters

    public function getStatusLabel($default = null)
    {
        return ArrayHelper::getValue(static::getStatusLabels(), $this->status, $default);
    }

    public static function getStatusLabels()
    {
        return [
            static::STATUS_NEW => \Yii::t('app', 'New'),
            static::STATUS_CANCELLED => \Yii::t('app', 'Cancelled'),
            static::STATUS_PAID => \Yii::t('app', 'Paid'),
        ];
    }
    
Also check status trait: https://gist.github.com/russianlagman/815ee61e3a8190d1b59b

### Translation categories
For translation categories keep structure clean and readable, please follow this structure:
* models attributes: models/{modelName} category ex: models/Invoice
* models validation: models/validation for common validation messages
* backend / frontend messages should have categories like:
  * backend/{controllername}/{viewname},
  * backend/{controllername},

## Database
* You should use utf8 and InnoDb

### Naming
* Table names should be in singular form ex: user_profile
* Table fields names should be in snake_case notation
* Timestamp fields should be named as: created_at, updated_at, and must be datetime type
* Relation fields should end with Id, ex: related_table_id
* Foreign Key name should looks like this, FK_table_name_relation_field_name
* Status fields must be not null integers
* Type fields must be not null integers 
