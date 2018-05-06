### How To Update and modify

In your composer.json, add the repo in your `repositories` key:

https://getcomposer.org/doc/05-repositories.md#vcs

```
    "repositories": [
        {
            "type": "vcs",
            "url": "git@github.com:Hellocasa/expression-language.git"
        }
    ],
```

```
composer require hellocasa/expression-language:dev-hellocasa
```

Add it in AppKernel

```
   ...
   new Hellocasa\Component\ExpressionLanguage\ExpressionLanguageBundle(),
   ...
```

Work like Symfony ExpressionLanguage but it throw an SyntaxError when variables into the expression is wrong https://symfony.com/doc/current/components/expression_language.html#passing-in-variables

### Exemple:

```
$expressionLanguage->evaluate(
    'quantities[1]+quantities[3]',
    array(
        'quantities' => [1 => 30, 2 => 50],
    )
);
```

Here quantity 3 not exist and throw ContextErrorException: Undefined offset, with this bundle now it throw an SyntaxError

# ExpressionLanguage Component

The ExpressionLanguage component provides an engine that can compile and
evaluate expressions. An expression is a one-liner that returns a value
(mostly, but not limited to, Booleans).

## Resources

* [Documentation](https://symfony.com/doc/current/components/expression_language/introduction.html)
* [Contributing](https://symfony.com/doc/current/contributing/index.html)
* [Report issues](https://github.com/symfony/symfony/issues) and
  [send Pull Requests](https://github.com/symfony/symfony/pulls)
  in the [main Symfony repository](https://github.com/symfony/symfony)
