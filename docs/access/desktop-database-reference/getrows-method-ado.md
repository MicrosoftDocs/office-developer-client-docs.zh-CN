---
title: GetRows 方法 (ADO)
TOCTitle: GetRows method (ADO)
ms:assetid: 570e6f1c-c17a-7d9a-c172-387894a3a1f1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249292(v=office.15)
ms:contentKeyID: 48544963
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 853f971f68bb0ec4069ba58e04b7cf9d231c6467
ms.sourcegitcommit: 980a96cf444882d3d34cecb5faac8f8a7b7c4b57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25949857"
---
# <a name="getrows-method-ado"></a>GetRows 方法 (ADO)

**适用于**： Access 2013、 Office 2013

用于将 [Recordset](recordset-object-ado.md) 对象的多个记录检索到数组中。

## <a name="syntax"></a>语法

*数组* = *recordset*。GetRows （*行*，*启动*，*字段*）

## <a name="return-value"></a>返回值

返回一个 **变量** ，其值是二维数组。

## <a name="parameters"></a>参数

|参数|说明|
|:--------|:----------|
|*Rows* |可选。[GetRowsOptionEnum](getrowsoptionenum.md) 值，指示要检索的记录数。默认值为 **adGetRowsRest** 。|
|*Start* |可选。 **字符串型** 值或 **变量** ，变量计算得出的值为应从该处开始 **GetRows** 操作的记录的书签。也可以使用 [BookmarkEnum](bookmarkenum.md) 值。|
|*Fields* |可选。 **变量** ，代表单个字段名或序号位置，或一个含一些字段名或序号位置编号的数组。ADO 仅返回这些字段中的数据。|

## <a name="remarks"></a>备注

使用 **GetRows** 方法可以将 **Recordset** 中的记录复制到一个二维数组中。 第一个下标标识字段，第二个下标标识记录号。 **GetRows**方法返回的数据时，*数组*变量是自动尺寸到正确的大小。

如果不指定*行*参数的值， **GetRows**方法将自动检索**Recordset**对象中的所有记录。 如果请求的记录数大于可用记录数，则 **GetRows** 仅返回可用数目的记录。

如果**Recordset**对象支持书签，则可以指定在哪些记录， **GetRows**方法应开始通过将该记录的[Bookmark](bookmark-property-ado.md)属性的值传递*Start*参数中检索数据。

如果您想要限制**GetRows**调用返回的字段，则可以在*Fields*参数中传递的单个字段名/编号或字段名/编号的数组。

调用 **GetRows** 之后，下一个未读取的记录成为当前记录，如果没有更多记录，则 [EOF](bof-eof-properties-ado.md) 属性设置为 **True** 。

