# 概要

## システム概要

ステムの全体構成図を {numref}`uml_birdview` に示す。

```{uml}
---
name: uml_birdview
caption: 全体システム構成図
---
package 全体 {
    actor 利用者 as user
    package システム as sys {
        cloud "クラウドサービス" as cloud
        package スマホ as phone {
            component App as app
        }
        component パソコン as pc
    }
}
```

{numref}`uml_birdview` 中の各要素は {numref}`uml_birdview_table` の通りである。


```{table} システム構成要素
:name: uml_birdview_table
:width: 65
:widths: auto
:align: center

|図中表記     |図中表記                |
|-----------|-----------------------|
|利用者      |通りすがりの利用者        |
|スマホ      |利用者のスマートフォン     |
|パソコン     |管理者のパソコン         |
```


```{raw} latex

   \clearpage
```
