Due to comprehensive manual code review between team members, sticked to CIBox Development Workflow this should be a place for gathering best practices for the code, been written during development.
This article should be as main document for reference during code review.
For adding a rule - please fill the issue https://github.com/propeoplemd/cibox/issues/new with a text for review.

PHP
=====

Return early
====

To keep readability in functions and methods, it is wise to return early if simple conditions apply that can be checked at the beginning of a method:

```php
<?php

function foo($bar, $baz)
{
    if ($foo) {
        //assume
        //that
        //here
        //is
        //the
        //whole
        //logic
        //of
        //this
        //method
        return $calculated_value;
    } else {
        return null;
    }
}
?>
```
It's better to return early, keeping indentation and brain power needed to follow the code low.

```php
<?php

function foo($bar, $baz)
{
    if (!$foo) {
        return null;
    }

    //assume
    //that
    //here
    //is
    //the
    //whole
    //logic
    //of
    //this
    //method
    return $calculated_value;
}
?>
```

Drupal Features Revert
=====

When you following hook_update_N path and need to revert feature, never use ```feature_revert_module()``` function, because it is slow and there is more faster solution - ```feature_revert()``` for reverting only particular component of the feature to be reverted.

Example:
```php
  features_revert(
    array(
      'gc_user_feature' => array(
        'field_base',
        'field_instance',
      ),
    )
  );
```


Javascript
=====

SCSS/SASS
=====