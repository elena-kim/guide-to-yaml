## Guide to Yaml

이 리포지토리는 Yaml의 기본적인 문법과 닷넷 환경에서의 사용법에 대해 기술한 리포지토리입니다. <br />

<a href="https://github.com/devncore/devncore"><strong>더 알아보기 »</strong></a>
 
| Star | License | Activity |
|:----:|:-------:|:--------:|
| <a href="https://github.com/devncore/guide-to-yaml/stargazers"><img src="https://img.shields.io/github/stars/devncore/guide-to-yaml" alt="Github Stars"></a> | <img src="https://img.shields.io/github/license/devncore/guide-to-yaml" alt="License"> | <a href="https://github.com/devncore/guide-to-yaml/pulse"><img src="https://img.shields.io/github/commit-activity/m/devncore/guide-to-yaml" alt="Commits-per-month"></a> |

<br />
<br />

<img src="https://user-images.githubusercontent.com/74305823/118442059-09bd3580-b725-11eb-92b7-4e435714bcca.png" width="180"/>  

**Yaml**은 사람이 쉽게 읽을 수 있는 데이터 직렬화 양식으로, 주로 설정 파일과 데이터가 저장 또는 전송되는 응용 프로그램에 사용됩니다. 원래 YAML의 뜻은 **"또 다른 마크업 언어 (Yet Another Markup Language)"** 였으나, 오늘날 **"YAML은 마크업 언어가 아니다 (YAML Ain't Markup Language)"** 라는 뜻으로 더 많이 언급됩니다.

더 많은 정보는 [YAML 공식 웹사이트](http://yaml.org/)를 참고하세요.

<br/>

## 다른 직렬화 포맷들과 다른 점은?

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
        YAML에는 주석, 확장 가능한 데이터 유형, 관계형 앵커, 따옴표가 없는 문자열, 키 순서를 유지하는 매핑 유형 등 JSON에 없는 많은 추가 기능이 있습니다. 
      </td>
      <td>
        YAML 설명서는 23,449개의 단어가 있는 반면, TOML 설명서는 3,339개의 단어로 구성되어 있습니다. 이러한 추가적인 설명과 YAML의 들여쓰기 구문 덕분에 TOML에 비해 덜 복잡한 방식으로 작성할 수 있습니다.
      </td>
      <td>
        YAML은 주석 사용이 가능하며 개행, 공백으로 블록을 인식한다는 점에서 XML과 문법적으로 유사한 점이 많습니다. 다만, XML과 달리 태그를 사용하지 않고 공백 위주로 데이터를 구분하므로 한 줄로 작성할 수 없다는 특징이 있습니다.
      </td>
    </tr>
  </tbody>
</table>

<br />

## YAML 사용법

#### 문자열
```yaml
# 따옴표 없는 문자열
title : Guide to YAML

# 따옴표 있는 문자열
title : 'Guide to YAML'

# 여러 줄의 문자열
Demons : |
    When the days are cold
    And the cards all fold
    And the saints we see
    Are all made of gold
```

#### 숫자
```yaml
# 정수형
count: 7

# 실수형
price: 32.05

# 과학적 표기법
total: 4.5e+4
```

#### Boolean
```yaml
isDarkMode: false
isDarkMode: False
isDarkMode: FALSE
```
> **true**: &nbsp; `y`, `Y`, `Yes`, `YES`, `true`, `True`, `TRUE`, `on`, `On`, `ON`  
> **false**: &nbsp; `n`, `N`, `No`, `NO`, `false`, `False`, `FALSE`, `off`, `Off`, `OFF`

#### Null
```yaml
username: 
username: ~
username: null
username: Null
username: NULL
```

#### 날짜 & 시간
```yaml
date: 2021-05-24
canonical: 2021-05-24T02:59:43.1Z
valid iso8601: 2021-05-24t21:59:43.10-05:00
space separated: 2021-05-24 21:59:43.10 -5
```

#### 시퀀스
```yaml
# 하이픈
people:
    - Elena
    - James
    - Olivia

# 인라인 
people: [Elena, James, Olivia]
```

#### 중첩되는 값
```yaml
Black Widow:
    director: Cate Shortland
    release-date: 2021-07-09
    cast: [Scarlett Johansson, David Harbour, Florence Pugh, O-T Fagbenle, and Rachel Weisz]
    overview: |
        In Marvel Studios’ action-packed spy thriller “Black Widow,” Natasha Romanoff aka Black Widow confronts the darker parts of her ledger when a dangerous conspiracy with ties to her past arises. 
        Pursued by a force that will stop at nothing to bring her down, Natasha must deal with her history as a spy and the broken relationships left in her wake long before she became an Avenger.
```

#### 리스트
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

#### 들여쓰기 구분 
YAML은 주로 구조의 들여쓰기에 의존하기 때문에 구분자 충돌 발생이 적습니다. YAML은 따옴표나 중괄호에 민감하지 않기 때문에 XML, JSON 또는 YAML 문서를 블록에 들여쓰기만 하면 YAML 문서 안에 포함할 수 있습니다 (`|` 또는 `>` 사용).
```yaml
message: |

        <blockquote style="font: italic 1em serif">
        <p>"Three is always greater than two,
           even for large values of two"</p>
        <p>--Author Unknown</p>
        </blockquote>
```

#### 주석
```yaml
# whole line comment
Item # inline comment
```

#### 앵커 및 별칭
향후 참조용으로 노드를 표시하여 노드를 재사용할 수 있습니다. 노드를 표시하기 위해 `&` 문자를 사용하고 참조하기 위해 `*`를 사용합니다. 
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

#### 명시적 데이터 유형
YAML은 엔터티의 데이터 형식을 자동으로 검색하지만, 값 앞에 `!!`의 형식을 포함하여 데이터 형식을 명시적으로 캐스트할 수도 있습니다. 
```yaml
explicit-int: !!int 3.2    # an integer
explicit-str: !!str 30.25  # a string
explicit-bool: !!bool yes  # a boolean
```
<br />

## YamlDotNet
YamlDotNet은 닷넷 스탠다드와 기타 닷넷 런타임을 위한 YAML 라이브러리입니다. 

YamlDotNet은 XmlDocument와 유사한 상위 수준의 객체 모델뿐만 아니라 YAML의 하위 수준의 구문 분석 기능을 제공합니다. 또한 개체를 읽고 쓸 수 있는 직렬화 라이브러리도 포함되어 있습니다.

### NuGet 설치
콘솔창에 아래 명령어를 입력하여 패키지를 설치합니다.
```
PM> Install-Package YamlDotNet
```

또는 아래와 같이 Nuget Package Manager를 통해 YamlDotNet 패키지를 설치할 수도 있습니다.   

<img src="https://user-images.githubusercontent.com/74305823/123741413-fafd9d00-d8e4-11eb-943b-8daac56b28cb.png" width="500"/>

### Using 추가
- `using YamlDotNet.Serialization` 
- `using YamlDotNet.Serialization.NamingConventions`

<img src="https://user-images.githubusercontent.com/76234292/148657700-34fc264c-61e9-479c-b334-78d426375542.PNG" width="450"/>

### Yaml 파일 C# 변환하기 (Deserialize)
```C#
var deserializer = new DeserializerBuilder()
           .WithNamingConvention(CamelCaseNamingConvention.Instance)
           .Build();

var result = deserializer.Deserialize<List<ArticleMenuModel>>(strContent);
```

### C# List Yaml 변환하기 (Serialize)

```C#
string yaml;
List<Model> datas;

var mySerializer = new SerializerBuilder()
    .WithNamingConvention(CamelCaseNamingConvention.Instance)
    .Build();

yaml = mySerializer.Serialize(datas);
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
