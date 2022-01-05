# YAML文件
* 大小写敏感
* 缩进只能空格
* 注释用#
* 支持三种数据结构：对象，数组，纯量(单个不可再分的值)
## 对象
* animal:pets  对象：{ animal: 'pets' }
* hash: { name: Steve, foo: bar } 对象{ hash: { name: 'Steve', foo: 'bar' } }
## 数组
```
- Cat
- Dog
- Goldfish
数组：[ 'Cat', 'Dog', 'Goldfish' ]

-
 - Cat
 - Dog
 - Goldfish
数组：[ [ 'Cat', 'Dog', 'Goldfish' ] ]

animal: [Cat, Dog]
数组：{ animal: [ 'Cat', 'Dog' ] }
```
```
示例：
languages:
 - Ruby
 - Perl
 - Python 
websites:
 YAML: yaml.org 
 Ruby: ruby-lang.org 
 Python: python.org 
 Perl: use.perl.org

{ languages: [ 'Ruby', 'Perl', 'Python' ],
  websites: 
   { YAML: 'yaml.org',
     Ruby: 'ruby-lang.org',
     Python: 'python.org',
     Perl: 'use.perl.org' } }
```
## 锚点&和别名*，可以用来引用
```
示例：
defaults: &defaults
  adapter:  postgres
  host:     localhost

development:
  database: myapp_development
  <<: *defaults

test:
  database: myapp_test
  <<: *defaults

等同：
defaults:
  adapter:  postgres
  host:     localhost

development:
  database: myapp_development
  adapter:  postgres
  host:     localhost

test:
  database: myapp_test
  adapter:  postgres
  host:     localhost

&用来建立锚点（defaults），<<表示合并到当前数据，*用来引用锚点。
```