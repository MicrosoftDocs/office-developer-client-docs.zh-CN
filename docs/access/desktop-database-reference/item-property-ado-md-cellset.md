---
title: Item 属性（ADO MD 单元格集）
TOCTitle: Item Property (ADO MD Cellset)
ms:assetid: 47510643-47af-0bfd-dc1f-ab984057bcd3
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249220(v=office.15)
ms:contentKeyID: 48544595
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 017b25b164233cb0e16753874e5b898409b5ac5a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466268"
---
# <a name="item-property-ado-md-cellset"></a>Item 属性（ADO MD 单元格集）

**适用于**： Access 2013 |Office 2013

使用单元格的坐标从单元格集中检索单元格。

## <a name="syntax"></a>语法

设置*单元格* = *单元格集*。项目 (*位置*)

## <a name="parameters"></a>参数

- *Positions*

- 一个 **可变的** 值 **数组** ，这些值分别唯一地指定一个单元格。 *位置*可以是下列选项之一：
    
  - 位置号数组
    
  - 成员名称数组
    
  - 序号位置

## <a name="remarks"></a>说明

使用 **Item** 属性可以返回 [Cellset](cell-object-ado-md.md) 对象中的 [Cell](cellset-object-ado-md.md) 对象。 如果**Item**属性找不到单元格对应于*Positions*参数，将发生错误。

**Item** 属性是 **Cellset** 对象的默认属性。以下语法格式可互换：

```vb
    Cellset.Item ( Positions )
    Cellset ( Positions )
```

*位置*参数指定要返回的单元格。 您可以按序号位置或沿每条轴的位置指定单元格。 按沿每条轴的位置指定单元格时，可以指定位置的数值，或者每个位置的成员的名称。

序号位置是唯一标识**单元格集**中每个单元格的数字。从概念上来说，单元格在**单元格集**中进行了编号，就像**单元格集**是一个 *p* 维数组那样（此处 *p* 是轴数目）。单元格按以行为主的顺序进行编号。

如果将成员名称作为字符串传递给 **Item** ，则必须以数值轴标识符的升序列出成员。在一条轴中，成员必须以维嵌套的升序列出，也就是说，最外侧的维的成员最先列出，然后跟随内侧的维的成员。每个维应由单独的字符串表示，且成员字符串列表应由逗号分隔。


> [!NOTE]
> [!注释] 您的数据提供程序可能不支持按成员名称检索单元格。有关详细信息，请参阅您的提供程序文档。


