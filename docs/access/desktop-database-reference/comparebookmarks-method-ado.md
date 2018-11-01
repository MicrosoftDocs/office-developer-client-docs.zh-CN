---
title: CompareBookmarks 方法 (ADO)
TOCTitle: CompareBookmarks Method (ADO)
ms:assetid: 826cb3c7-2f5c-284f-421d-6b7b07f14dec
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249564(v=office.15)
ms:contentKeyID: 48545977
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 26f8cb17473daf21be3769f6f48a3bb368c1d082
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25876972"
---
# <a name="comparebookmarks-method-ado"></a>CompareBookmarks 方法 (ADO)


**适用于**： Access 2013、 Office 2013

用于比较两个书签，并返回其相对值的指示。

## <a name="syntax"></a>语法

*结果* = *recordset*。CompareBookmarks （*Bookmark1*、 *Bookmark2*）

## <a name="return-value"></a>返回值

返回一个 [CompareEnum](compareenum.md) 值，指示用书签所表示的两个记录的行相对位置。

## <a name="parameters"></a>参数

  - *Bookmark1*

  - 第一行的书签。

  - *Bookmark2*

  - 第二行的书签。

## <a name="remarks"></a>备注

书签必须应用于相同的 [Recordset](recordset-object-ado.md) 对象，或 **Recordset** 对象及其 [克隆](clone-method-ado.md)。来自不同 **Recordset** 对象的书签无法进行可靠地比较，即使书签创建自相同的源或命令。如果 **Recordset** 对象的基础提供程序不支持比较，则其书签也无法进行比较。

书签唯一标识 **Recordset** 对象中的行。使用当前行的 [Bookmark](bookmark-property-ado.md) 属性可以获取其书签。

由于书签的数据类型取决于提供程序，ADO 将其公开为变量型。 例如，SQL Server 书签是类型 DBTYPE 的\_R8 (Double)。 ADO 将此类型公开为具双精度子类型的变量型。

在比较书签时，ADO 不会尝试进行任何类型的强制转换。只是在进行比较的地方将值传递给提供程序。如果传递给 **CompareBookmarks** 方法的书签存储在不同类型的变量中，则将产生类型不匹配错误："Arguments are of the wrong type, are out of the acceptable range, or are in conflict with each other"。

无效的书签或格式不正确的书签将引发错误。

