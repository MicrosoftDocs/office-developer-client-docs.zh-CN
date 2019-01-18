---
title: Shape Append 子句
TOCTitle: Shape Append clause
ms:assetid: 8f29afc3-fb93-4439-b67b-cad0eed0bda9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249633(v=office.15)
ms:contentKeyID: 48546301
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 40c35e8b2c3fb3f0b92bf261b62c252a61a367b4
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2019
ms.locfileid: "28726349"
---
# <a name="shape-append-clause"></a>Shape Append 子句


**适用于**： Access 2013、 Office 2013

shape 命令 APPEND 子句用于将一个或多个列追加到 **Recordset** 中。通常，这些列是章节列，而章节列是对子 **Recordset** 的引用。

## <a name="syntax"></a>语法

```vb 
 
SHAPE [parent-command [[AS] parent-alias]] APPEND column-list
```

## <a name="description"></a>说明

此子句的各部分如下所示：

- *parent-command*

- 零个或者 （可以完全省略*父命令*） 以下一项：
    
  - 返回 {} 对象的提供程序命令，放在大括号（"****"）中。该命令向基础数据提供程序发出，其语法取决于该提供程序的要求。这通常是 SQL 语言，但 ADO 不需要任何特定的查询语言。
    
  - 嵌入在括号中的另一个 Shape 命令。
    
  - TABLE 关键字，后跟数据提供程序中的表的名称。

- *parent-alias*

  - 用于引用父 **Recordset** 的可选别名。

- *column-list*

  - 一个或多个以下项：
    
    - 聚合列。
    
    - 计算列。
    
    - 用 NEW 子句创建的新列。
    
    - 章节列。章节列的定义放在括号（"()"）中。请参阅以下语法：


        ```vb 
        
        SHAPE [parent-command [[AS] parent-alias]] 
        APPEND (child-recordset [ [[AS] child-alias] 
        RELATE parent-column TO child-column | PARAMETER param-number, ... ]) 
        [[AS] chapter-alias] 
        [, ... ] 
        ```

- *child-recordset*

  - 返回 {} 对象的提供程序命令，放在大括号（"****"）中。该命令向基础数据提供程序发出，其语法取决于该提供程序的要求。这通常是 SQL 语言，但 ADO 不需要任何特定的查询语言。
    
  - 嵌入在括号中的另一个 Shape 命令。
    
  - 现有已构形 **Recordset** 的名称。
    
  - TABLE 关键字，后跟数据提供程序中的表的名称。

- *child-alias*

  - 引用子 **Recordset** 的别名。

- *parent-column*

  - 返回**Recordset**中的列*父命令。*

- *child-column*

  - 由 *child-command* 返回的 **Recordset** 中的列。

- *param-number*

  - 请参阅[参数化命令的操作](operation-of-parameterized-commands.md)。

- *chapter-alias*

  - 引用追加到父记录集的章节列的别名。


> [!NOTE]
> - _"父列收件人子-列"_ 子句实际上是一个列表，其中每个关系定义并用逗号分隔。
> - [!注释] APPEND 关键字后面的子句实际上是列表，其中每个子句均以逗号分隔，并且定义了要追加到父记录集的其他列。



## <a name="remarks"></a>说明

利用用户输入来构造提供程序命令以便将其作为 SHAPE 命令的一部分时，SHAPE 会将用户提供的提供程序命令当作不透明的字符串，并如实地传递给提供程序。例如，在以下 SHAPE 命令中，

```vb 
 
SHAPE {select * from t1} APPEND ({select * from t2} RELATE k1 TO k2) 
```

形状将执行两个命令： 选择\*从 t1 和 (选择\*从 t2 建立关系版 k1 收件人 k2)。 如果用户提供了由多个提供程序命令组成并以分号分隔的复合命令，SHAPE 将无法辨别差异。 因此，在以下 SHAPE 命令中，

```vb 
 
SHAPE {select * from t1; drop table t1} APPEND ({select * from t2} RELATE k1 TO k2) 
```

形状执行选择\*从 t1;drop 表 t1 和 (选择\*从 t2 建立关系版 k1 收件人 k2)，未意识到的投递表 t1 单独和在此案例、 危险，提供程序命令。 应用程序必须始终验证用户输入，以防止发生类似潜在黑客攻击。

本节包括下列主题：

- [操作非参数化命令](operation-of-non-parameterized-commands.md)

- [参数化命令的操作](operation-of-parameterized-commands.md)

- [混合命令](hybrid-commands.md)

- [中间 Shape COMPUTE 子句](intervening-shape-compute-clauses.md)
