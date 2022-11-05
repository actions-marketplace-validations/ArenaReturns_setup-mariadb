### This is a fork of ankane's setup-mariadb action tweaked for our needs.

# setup-mariadb

The missing action for MariaDB :tada:

- Simpler than containers
- Works on Linux, Mac, and Windows
- Supports different versions

[![Build Status](https://github.com/arenareturns/setup-mariadb/workflows/build/badge.svg?branch=v1)](https://github.com/arenareturns/setup-mariadb/actions)

## Getting Started

Add it as a step to your workflow

```yml
- uses: arenareturns/setup-mariadb@v1
```

## Versions

Specify a version (defaults to the latest)

```yml
- uses: arenareturns/setup-mariadb@v1
  with:
    mariadb-version: 10.9
```

Currently supports

| Version        | `10.9` | `10.8` | `10.7` | `10.6` | `10.5` | `10.4` | `10.3` |
| -------------- | ------ | ------ | ------ | ------ | ------ | ------ | ------ |
| `ubuntu-22.04` | ?      | ?      | ?      | ?      | ?      | ?      | ?      |
| `ubuntu-20.04` | ✓      | ✓      | ✓      | ✓      | ✓      | ?      | ?      |
| `ubuntu-18.04` | ✓      | ✓      | ✓      | ✓      | ✓      | ✓      | ✓      |
| `macos-12`     | ✖      | ✓      | ✓      | ✓      | ✓      | ✓      | ✓      |
| `macos-11`     | ✖      | ✓      | ✓      | ✓      | ✓      | ✓      | ✓      |
| `macos-10.15`  | ✖      | ✓      | ✓      | ✓      | ✓      | ✓      | ✓      |
| `windows-2022` | ✓      | ✓      | ✓      | ✓      | ✓      | ✓      | ✓      |
| `windows-2019` | ✓      | ✓      | ✓      | ✓      | ✓      | ✓      | ✓      |

Test against multiple versions

```yml
strategy:
  matrix:
    mariadb-version: [10.9, 10.8, 10.7, 10.6, 10.5, 10.4, 10.3]
steps:
  - uses: arenareturns/setup-mariadb@v1
    with:
      mariadb-version: ${{ matrix.mariadb-version }}
```

## Options

Create a database

```yml
- uses: arenareturns/setup-mariadb@v1
  with:
    database: testdb
```

## Extra Steps

Run queries

```yml
- run: mysql -D testdb -e 'SELECT VERSION()'
```

## Related Actions

- [setup-mysql](https://github.com/ankane/setup-mysql)
- [setup-postgres](https://github.com/ankane/setup-postgres)
- [setup-mongodb](https://github.com/ankane/setup-mongodb)
- [setup-elasticsearch](https://github.com/ankane/setup-elasticsearch)
- [setup-opensearch](https://github.com/ankane/setup-opensearch)
- [setup-sqlserver](https://github.com/ankane/setup-sqlserver)

## Contributing

Everyone is encouraged to help improve this project. Here are a few ways you can help:

- [Report bugs](https://github.com/arenareturns/setup-mariadb/issues)
- Fix bugs and [submit pull requests](https://github.com/arenareturns/setup-mariadb/pulls)
- Write, clarify, or fix documentation
- Suggest or add new features
