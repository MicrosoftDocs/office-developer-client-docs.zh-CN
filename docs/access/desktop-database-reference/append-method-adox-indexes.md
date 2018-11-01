---
title: Append 方法 (ADOX Indexes)
TOCTitle: Append Method (ADOX Indexes)
ms:assetid: 015ebab4-5e9d-8777-ac82-4d20e957c274
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248784(v=office.15)
ms:contentKeyID: 48542933
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 2b2786de4d1fde2e67e576c2bc81733b1a877a80
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25875124"
---
# <a name="append-method-adox-indexes"></a>Append 方法 (ADOX Indexes)


**适用于**： Access 2013、 Office 2013



将新的 [Index](index-object-adox.md) 对象添加到 [Indexes](indexes-collection-adox.md) 集合。

## <a name="syntax"></a>语法

*索引*。追加*索引* \[，*列*\]

## <a name="parameters"></a>参数

  - *Index*

  - 要追加的 **Index** 对象，或者要创建并追加的索引的名称。

  - *Columns*

  - 可选。 一个 **Variant** 值，指定要进行索引的列的名称。 *Columns*参数对应于一个[Column](column-object-adox.md)对象或对象的[Name](name-property-adox.md)属性的值。

## <a name="remarks"></a>说明

*Columns*参数可接受的列的名称或列名的数组。

如果提供程序不支持创建索引，则会发生错误。

