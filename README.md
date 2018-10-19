# shared-config-files

This repository contains files shared between several JobTeaser project. It can be config for linter, quality, security static analysis tools or anything you need.

## Rubocop usage

Create a `.rubocop.yml` with the following directives:

```
inherit_from:
  - https://raw.githubusercontent.com/jobteaser/shared-config-files/master/ruby/rubocop/default.yml
```

Now, run:

```
$ bundle exec rubocop
```

For Code Climate usage, add in your `.code_climate.yml` config file the following lines:

```
version: "2"
prepare:
  fetch:
    - url: https://raw.githubusercontent.com/jobteaser/shared-config-files/master/ruby/rubocop/default.yml
      path: .rubocop-https---raw-githubusercontent-com-jobteaser-shared-config-files-master-ruby-rubocop-default-yml
```

## Reek usage

Reek does not support remote config file. Clone the repository and run the following command with the path to the config file:

```
$ bundle exec reek -c <path_to_shared-config-files>/ruby/reek/default.yml
```

For Code Climate usage, add in your `.code_climate.yml` config file the following lines:

```
version: "2"
prepare:
  fetch:
    - url: https://raw.githubusercontent.com/jobteaser/code_climate_ruby/master/lib/reek/default.yml
      path: .reek.yml
```