## Guide to Yaml

이 리포지토리는 Yaml의 기본적인 사용법에 대해 기술한 리포지토리입니다. <br />

<a href="https://github.com/devncore/devncore"><strong>더 알아보기 »</strong></a>
 
| Star | License | Activity |
|:----:|:-------:|:--------:|
| <a href="https://github.com/devncore/the-easiest-yaml/stargazers"><img src="https://img.shields.io/github/stars/devncore/the-easiest-yaml" alt="Github Stars"></a> | <img src="https://img.shields.io/github/license/devncore/the-easiest-yaml" alt="License"> | <a href="https://github.com/devncore/the-easiest-yaml/pulse"><img src="https://img.shields.io/github/commit-activity/m/devncore/the-easiest-yaml" alt="Commits-per-month"></a> |

<br />
  
## Overview
- [What is the Yaml?](#what-is-the-yaml)
- [What is different from other serialization formats?](#what-is-different-from-other-serialization-formats)
- [How to use Yaml?](#how-to-use-yaml)
- [YamlDotNet](#yamldotnet)
- [Yaml File C# 변환](#yaml파일-csharp변환)

<br />

## _What is the Yaml?_
<img src="https://user-images.githubusercontent.com/74305823/118442059-09bd3580-b725-11eb-92b7-4e435714bcca.png" width="180"/>  

**Yaml** is a human-readable data-serialization language. And it is commonly used for configuration files and in applications where data is being stored or transmitted. YAML was originally an acronym for '_Yet Another Markup Language_', but is now more commonly referred to as '**_YAML Ain't Markup Language_**'. 

Visit the [official YAML website](http://yaml.org/) for more information.

<br/>

## _What is different from other serialization formats?_

<table>
  <thead>
    <th>JSON</th>
    <th>TOML</th>
    <th>XML</th>
  </thead>
  <tbody>
    <tr>
      <td align="center">JavaScript Object Notation</td>
      <td align="center">Tom's Obvious, Minimal Language</td>
      <td align="center">Extensible Markup Language</td>
    </tr>
    <tr>
      <td align="center"><img src="https://user-images.githubusercontent.com/74305823/118442487-9e279800-b725-11eb-99e5-e6b9925adbf9.png"/></td>
      <td align="center"><img src="https://user-images.githubusercontent.com/74305823/118442671-d7600800-b725-11eb-813a-d1bc832b763e.png" width="100"/></td>
      <td align="center"><img src="https://user-images.githubusercontent.com/74305823/118442721-ea72d800-b725-11eb-936c-bb407435f36e.png" width="150"/></td>
    </tr>
    <tr>
      <td>
        YAML has many additional features lacking in JSON, including comments, extensible data types, relational anchors, strings without quotation marks, and mapping types preserving key order.
      </td>
      <td>
        YAML is much more complex compared to TOML - the YAML specification was pointed out to have 23,449 words, while the TOML specification had only 3,339 words.
      </td>
      <td>
        YAML lacks the notion of tag attributes that are found in XML. And YAML itself does not have XML's language-defined document schema descriptors that allow, for example, a document to self-validate. 
      </td>
    </tr>
  </tbody>
</table>

<br />

## _How to use Yaml?_
- [Basic Syntax](#basic-syntax)
- [Advanced Features](#advanced-features)

### Basic Syntax
#### `String`
```yaml
# string without quotes
title : The Easiest YAML

# string with quotes
title : 'The Easiest YAML'

# multiline string
Demons : |
    When the days are cold
    And the cards all fold
    And the saints we see
    Are all made of gold
```

#### `Numbers`
```yaml
# integer
count: 7

# float
price: 32.05

# scientific notation
total: 4.5e+4
```

#### `Boolean`
```yaml
isDarkMode: false
isDarkMode: False
isDarkMode: FALSE
```
> **true**: &nbsp; `y`, `Y`, `Yes`, `YES`, `true`, `True`, `TRUE`, `on`, `On`, `ON`  
> **false**: &nbsp; `n`, `N`, `No`, `NO`, `false`, `False`, `FALSE`, `off`, `Off`, `OFF`

#### `Null`
```yaml
username: 
username: ~
username: null
username: Null
username: NULL
```

#### `Date & Timestamp`
```yaml
date: 2021-05-24
canonical: 2021-05-24T02:59:43.1Z
valid iso8601: 2021-05-24t21:59:43.10-05:00
space separated: 2021-05-24 21:59:43.10 -5
```

#### `Sequence`
```yaml
# using hyphens
people:
    - Elena
    - James
    - Olivia

# inline
people: [Elena, James, Olivia]
```

#### `Nested Value`
```yaml
Black Widow:
    director: Cate Shortland
    release-date: 2021-07-09
    cast: [Scarlett Johansson, David Harbour, Florence Pugh, O-T Fagbenle, and Rachel Weisz]
    overview: |
        In Marvel Studios’ action-packed spy thriller “Black Widow,” Natasha Romanoff aka Black Widow confronts the darker parts of her ledger when a dangerous conspiracy with ties to her past arises. 
        Pursued by a force that will stop at nothing to bring her down, Natasha must deal with her history as a spy and the broken relationships left in her wake long before she became an Avenger.
```

#### `List of Objects`
```yaml
- Black Widow:
    director: Cate Shortland
    release-date: 2021-07-09
    cast: [Scarlett Johansson, David Harbour, Florence Pugh, O-T Fagbenle, and Rachel Weisz]
    overview: |
        In Marvel Studios’ action-packed spy thriller “Black Widow,” Natasha Romanoff aka Black Widow confronts the darker parts of her ledger when a dangerous conspiracy with ties to her past arises. 
        Pursued by a force that will stop at nothing to bring her down, Natasha must deal with her history as a spy and the broken relationships left in her wake long before she became an Avenger.
        
- Shang-Chi:
    director: Destin Daniel Cretton
    release-date: 2021-09-03
    cast: [Simu Liu, Awkwafina, Tony Leung, Michelle Yeoh, Fala Chen, Meng’er Zhang, Florian Munteanu and Ronny Chieng]
    overview: |
        Marvel Studios' "Shang-Chi and The Legend of The Ten Rings" stars Simu Liu as Shang-Chi, who must confront the past he thought he left behind when he is drawn into the web of the mysterious Ten Rings organization. 
        The film also stars Tony Leung as Wenwu, Awkwafina as Shang-Chi's friend Katy and Michelle Yeoh as Jiang Nan, as well as Fala Chen, Meng'er Zhang, Florian Munteanu and Ronny Chieng.
```
<br />

### Advanced Features
#### `Indented delimiting`
> Because YAML primarily relies on outline indentation for structure, it is especially resistant to delimiter collision. YAML's insensitivity to quotation marks and braces in scalar values means one may embed XML, JSON or even YAML documents inside a YAML document by simply indenting it in a block literal (using `|` or `>`).
```yaml
message: |

        <blockquote style="font: italic 1em serif">
        <p>"Three is always greater than two,
           even for large values of two"</p>
        <p>--Author Unknown</p>
        </blockquote>
```

#### `Comments`
```yaml
# whole line comment
Item # inline comment
```

#### `Anchor and Alias`
> Node anchors mark a node for future reference, which allow us to reuse the node. To mark a node we use the `&` character, and to reference it we use `*`.
```yaml
people:
    - first: &Elena
        name: Elena
        last-name: Kim
        age: 25
    - second: &James
        name: James
        last-name: Lee
        age: 35
        
one: *Elena
two: *James
```

#### `Explicit type`
> YAML autodetects the datatype of the entity, but sometimes we can cast the datatype explicitly by including the type before the value preceded by `!!`.
```yaml
explicit-int: !!int 3.2    # an integer
explicit-str: !!str 30.25  # a string
explicit-bool: !!bool yes  # a boolean
```
<br />

## _YamlDotNet_
YamlDotNet is a YAML library for netstandard and other .NET runtimes.

YamlDotNet provides low level parsing and emitting of YAML as well as a high level object model similar to XmlDocument. A serialization library is also included that allows to read and write objects from and to YAML streams.

### Installing
Just install the [YamlDotNet NuGet package](https://www.nuget.org/packages/YamlDotNet/):
```
PM> Install-Package YamlDotNet
```
You can also install YamlDotNet at Nuget Package Manager.   

<img src="https://user-images.githubusercontent.com/74305823/123741413-fafd9d00-d8e4-11eb-943b-8daac56b28cb.png" width="500"/>

<br />

### _YAML파일 Csharp변환_

#### `Nuget 패키지 설치 및 Using 정보`
- YamlDotNet Nuget 설치
- using YamlDotNet.Serialization;
- using YamlDotNet.Serialization.NamingConventions;

| Nuget 설치 | Yaml Using |
|:----------:|:----------:|
| ![image](https://user-images.githubusercontent.com/76234292/148646402-19d302c2-30ce-47e7-9c31-1da014fc550e.png) | ![yamlusing](https://user-images.githubusercontent.com/76234292/148657700-34fc264c-61e9-479c-b334-78d426375542.PNG)

<br />

#### Yaml 파일 C# 변환하기
```
var deserializer = new DeserializerBuilder()
           .WithNamingConvention(CamelCaseNamingConvention.Instance)
           .Build();

var result = deserializer.Deserialize<List<ArticleMenuModel>>(strContent);

```

#### C# List Yaml 변환하기

```C#
string yaml;
List<Model> datas;

var serializer1 = new SerializerBuilder()
    .WithNamingConvention(CamelCaseNamingConvention.Instance)
    .Build();

yaml = serializer1.Serialize(datas);

```

<br />

***

## References
📑 **CODE PROJECT** &nbsp; [YAML Parser in C#][1]  
📑 **C# Corner** &nbsp; [The Basics Of YAML In 5 Minutes Or Less!][2]   
📑 **DEV Community** &nbsp; [Introduction to YAML][3]  
📑 **YamlDotNet** &nbsp; [GitHub][4]    
📑 **WIKIPEDIA** &nbsp; [YAML][5]  

[1]: https://www.codeproject.com/Articles/28720/YAML-Parser-in-C
[2]: https://www.c-sharpcorner.com/article/the-basics-of-yaml-in-5-minutes-or-less/
[3]: https://dev.to/paulasantamaria/introduction-to-yaml-125f
[4]: https://github.com/aaubry/YamlDotNet/
[5]: https://en.wikipedia.org/wiki/YAML
