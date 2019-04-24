---
title: GetRows 方法 (ADO)
TOCTitle: GetRows method (ADO)
ms:assetid: 570e6f1c-c17a-7d9a-c172-387894a3a1f1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249292(v=office.15)
ms:contentKeyID: 48544963
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 61f7ce441eb837b76e824b55393741e0cf821bb5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32292221"
---
# <a name="getrows-method-ado"></a>GetRows 方法 (ADO)

**适用于**：Access 2013、Office 2013

用于将 [Recordset](recordset-object-ado.md) 对象的多个记录检索到数组中。

## <a name="syntax"></a>语法

*数组* = *recordset*。GetRows (*行*、*开始*、*字段*)

## <a name="return-value"></a>返回值

返回一个**变量**，其值是二维数组。

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*Rows* |可选。[GetRowsOptionEnum](getrowsoptionenum.md) 值，指示要检索的记录数。默认值为 **adGetRowsRest** 。|
|*Start* |可选。 **字符串型** 值或 **变量** ，变量计算得出的值为应从该处开始 **GetRows** 操作的记录的书签。也可以使用 [BookmarkEnum](bookmarkenum.md) 值。|
|*Fields* |可选。 **变量** ，代表单个字段名或序号位置，或一个含一些字段名或序号位置编号的数组。ADO 仅返回这些字段中的数据。|

## <a name="remarks"></a>注解

使用 **GetRows** 方法可以将 **Recordset** 中的记录复制到一个二维数组中。第一个下标标识字段，第二个下标标识记录号。当 **GetRows** 方法返回数据时，*array* 变量的维度将自动设为正确的大小。

如果不指定 *Rows* 参数的值，**GetRows** 方法将自动检索 **Recordset** 对象中的所有记录。如果请求的记录数大于可用记录数，则 **GetRows** 仅返回可用数目的记录。

如果 **Recordset** 对象支持书签，则可以指定 **GetRows** 方法应从哪个记录开始检索数据，方法是在 *Start* 参数中传递该记录的 [Bookmark](bookmark-property-ado.md) 属性的值。

如果要限制 **GetRows** 调用返回的字段数，可以在 *Fields* 参数中传递单个字段名/编号或一个含多个字段名/编号的数组。

调用 **GetRows** 之后，下一个未读取的记录成为当前记录，如果没有更多记录，则 [EOF](bof-eof-properties-ado.md) 属性设置为 **True**。

