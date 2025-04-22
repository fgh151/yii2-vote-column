Vote column
===========
Vote column for grid view

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
composer require --prefer-dist fgh151/yii2-vote-column "*"
```

or add

```
"fgh151/yii2-vote-column": "*"
```

to the require section of your `composer.json` file.


Usage
-----

Once the extension is installed, simply use it in your code by  :

```php
<?php
use yii\grid\GridView;

echo  GridView::widget([
         'dataProvider' => $dataProvider,
         'filterModel' => $searchModel,
         'columns' => [
             ['class' => 'yii\grid\SerialColumn'],
             [
                 'class' => fgh151\vote\VoteColumn::class,
                 'attribute' => 'vote',
                 'onText' => 'Approve',
                 'offText' => 'Not approve',
                 'action' => 'controller/ajax-vote',
                 'filterInputOptions' => [
                     'class' => 'form-control'
                 ]
             ],
         ],
     ]);
 ?>
```
 
Params
------

* attribute - boolean model attribute to store vote
* action - action to switch vote example see in phpdoc comments
* filterInputOptions - see in ```yii\grid\DataColumn.php```
* prompt - Grid view filter prompt