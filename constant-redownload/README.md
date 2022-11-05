To reproduce the issue in this reposity:

``` bash
$ pdm lock
$ pdm sync -v
$ pdm sync -v
```

Note that torch and pdm-pep517 both get redownload twice.
