## Coding guide
### General styles
* Follow [psr-1](http://www.php-fig.org/psr/psr-1/) and [psr-2](http://www.php-fig.org/psr/psr-2/) standards.
* Use curly brackets for all of the conditions even one line condition ex:

```
if (true) {
    do();
}
```
* Add phpdoc to all methods that you add
* Add @var marks for objects variables ex:
```
/**
 * @var Model $model
 */
$model = Model::find()->one();
```
## Yii
* You should use migrations for any database structure changes
* You should use scheme builder in migrations (http://www.yiiframework.com/news/88/yii-2-0-6-is-released/)
* Model class names should be in singular form
* Relation names should be named reasonably ex:
tables: user, user_profile; relation name in user model: profile
* View names should be in dash notation, and should be same as controller url name ex: some-file-name.php
* If some extra logic is required to extract some ui data, make it via widget

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