faker-bin
=========

**This is a [feature proposal](https://github.com/fzaninotto/Faker/issues/240#issuecomment-33380648) stub**

Faker-bin is a CLI utility wrapping [Faker](https://github.com/fzaninotto/Faker/).

It is implemented as executable PHAR using [Symfony Console](http://symfony.com/doc/current/components/console/introduction.html) for CLI and [Composer](https://getcomposer.org/) for dependency management.

**Intended usage example**

```
# call provider uuid on default method (uuid.uuid)
~/vendor/bin$ faker uuid
1fa3293b-3491-4c18-b3f8-4a7aae8e1f36

# give uuid.uuid a seed
~/vendor/bin$ faker uuid -s=1234
2049a963-8c87-4e3c-8d48-488f2ef95e11

# get person.name
~/vendor/bin$ faker person.name
Dr. Zane Stroman

# pass arguments to method
~/vendor/bin$ faker base.random-number --from=1 --to=100
42
```

**Issues**

* not yet sure how to handle non-scalar arguments (json?)
* not yet sure whether to name arguments or just read them one-by-one from $args
* not yet sure how to handle configuration (`-s`for seeds, `-n[0-9]+` to give more than 1, `-q` to surpress trailing line feed, `-v` for debug notices, `-h`for help)
* temporarily opting to use short names (like `-h`) for utility options and long names (like `--from`) for method arguments
* temporarily opting for dashes to handle camel case names on CLI
