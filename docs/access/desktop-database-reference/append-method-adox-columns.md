---
title: Append 方法 (ADOX Columns)
TOCTitle: Append Method (ADOX Columns)
ms:assetid: e256a478-abc0-f15b-fc29-1b52e354144a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250152(v=office.15)
ms:contentKeyID: 48548285
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1f64f3b04df989348173ad2fc975dcefbd1114b2
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465992"
---
# <a name="append-method-adox-columns"></a>Append 方法 (ADOX Columns)


**适用于**： Access 2013 |Office 2013

将新的 [Column](column-object-adox.md) 对象添加到 [Columns](columns-collection-adox.md) 集合。

## <a name="syntax"></a>语法

*列*。 追加*列* \[，*键入*\] \[，*DefinedSize*\]

## <a name="parameters"></a>参数

  - *Column*

  - 要追加的 **Column** 对象，或者要创建并追加的列的名称。

  - *Type*

  - 可选。 指定该列的数据类型的 **Long** 值。 *Type*参数对应于一个**Column**对象的[Type](https://msdn.microsoft.com/library/jj249169\(v=office.15\))属性。

  - *DefinedSize*

  - 可选。 指定该列的大小的 **Long** 值。 *DefinedSize*参数对应于一个**Column**对象的[DefinedSize](definedsize-property-adox.md)属性。


> [!NOTE]
> <P>[!注释] 如果追加到 <STRONG>Tables</STRONG> 集合中的 <STRONG>Table</STRONG> 中没有某个 <A href="index-object-adox.md">Column</A> ，则在将该 <STRONG>Column</STRONG> 追加到 <A href="table-object-adox.md">Index</A> 的 <A href="tables-collection-adox.md">Columns</A> 集合时将发生错误。</P>


