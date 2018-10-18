---
title: GetString 方法 (ADO)
TOCTitle: GetString Method (ADO)
ms:assetid: f496305e-a1f5-7014-7808-7e4961e5f0fa
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250242(v=office.15)
ms:contentKeyID: 48548693
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ba235094aa7f491cbd86bf753713d50f01009d47
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25605399"
---
# <a name="getstring-method-ado"></a>GetString 方法 (ADO)


**适用于**： Access 2013 |Office 2013


将 [Recordset](recordset-object-ado.md) 作为字符串返回。

## <a name="syntax"></a>语法

*Variant* = *recordset*。GetString （*StringFormat*、 *NumRows*、 *ColumnDelimiter*、 *RowDelimiter*、 *NullExpr*）

<<<<<<< 标头
## <a name="return-value"></a>返回值
=======
## <a name="return-value"></a>返回值
>>>>>>> master

将 **Recordset** 作为值为字符串的 **变量型** (BSTR) 返回。

## <a name="parameters"></a>参数

  - *StringFormat*

  - [StringFormatEnum](stringformatenum.md) 值，指定应如何将 **Recordset** 转换为字符串。*RowDelimiter*、*ColumnDelimiter* 和 *NullExpr* 参数仅与 **adClipString** 的 *StringFormat* 一起使用。

  - *NumRows*

  - 可选。 **Recordset** 中要转换的行数。 如果未指定*NumRows* ，或者大于**Recordset**中的行的总数，会转换**Recordset**中的所有行。

  - *ColumnDelimiter*

  - 可选。如果指定，则在列之间使用的分隔符，否则为 TAB 字符。

  - *RowDelimiter*

  - 可选。如果指定，则在行之间使用的分隔符，否则为 CARRIAGE RETURN 字符。

  - *NullExpr*

  - 可选。如果指定，则用表达式替代 Null 值，否则为空字符串。

## <a name="remarks"></a>备注

保存到字符串的是行数据，而不是架构数据。因此，不能使用该字符串重新打开 **Recordset** 。

此方法等效于 RDO 的 **GetClipString** 方法。

