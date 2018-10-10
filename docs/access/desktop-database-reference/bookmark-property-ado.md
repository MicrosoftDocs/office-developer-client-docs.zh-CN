---
title: Bookmark 属性 (ADO)
TOCTitle: Bookmark Property (ADO)
ms:assetid: 101b2ce1-21d8-aa79-e530-20f9d1c73fc8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248870(v=office.15)
ms:contentKeyID: 48543287
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: a89be0ad75ea84faa9fe17834260832070dd7578
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467197"
---
# <a name="bookmark-property-ado"></a>Bookmark 属性 (ADO)


**适用于**： Access 2013 |Office 2013

指示在 [Recordset](recordset-object-ado.md) 对象中唯一标识当前记录的书签，或者将 **Recordset** 对象中的当前记录设置为有效书签标识的记录。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个 **Variant** 表达式，该表达式的计算结果为一个有效书签。

## <a name="remarks"></a>备注

使用 **Bookmark** 属性可以保存当前记录的位置并随时返回到该记录处。书签仅在支持书签功能的 **Recordset** 对象中可用。

当打开 **Recordset** 对象时，它的每条记录都有一个唯一的书签。若要保存当前记录的书签，请将 **Bookmark** 属性的值赋给一个变量即可。若要在移动到不同的记录后随时快速返回到该记录，请将 **Recordset** 对象的 **Bookmark** 属性设置为该变量的值。

用户可能无法查看书签的值。另外，用户不应期望可直接对书签进行比较  引用相同记录的两个书签可能具有不同的值。

如果使用 [Clone](clone-method-ado.md) 方法创建 **Recordset** 对象的副本，原始和重复 **Recordset** 对象的 **Bookmark** 属性设置是完全相同的，可以将二者交换使用。不过，无法将不同 **Recordset** 对象的书签交换使用，即使它们使用相同的源或命令创建也不行。

**远程数据服务用法**当客户端**Recordset**对象上使用， **Bookmark**属性始终是可用。

