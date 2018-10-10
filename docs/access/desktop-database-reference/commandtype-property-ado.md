---
title: CommandType 属性 (ADO)
TOCTitle: CommandType Property (ADO)
ms:assetid: c8d4fc1c-502b-11f3-af9d-605a03b6f056
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249976(v=office.15)
ms:contentKeyID: 48547663
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- ado210.chm1231125
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 3cff3c3540208b142fc13cd79eb83bd218814873
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468993"
---
# <a name="commandtype-property-ado"></a>CommandType 属性 (ADO)


**适用于**： Access 2013 |Office 2013

指示 [Command](command-object-ado.md) 对象的类型。

## <a name="settings-and-return-values"></a>设置和返回值

设置或返回一个或多个 [CommandTypeEnum](commandtypeenum.md) 值。


> [!NOTE]
> <P>[!注释] 不要将 <STRONG>adCmdFile</STRONG> 或 <STRONG>adCmdTableDirect</STRONG> 的 <STRONG>CommandTypeEnum</STRONG> 值与 <STRONG>CommandType</STRONG> 一起使用。这些值仅可作为 <A href="open-method-ado-recordset.md">Recordset</A> 的 <A href="requery-method-ado.md">Open</A> 和 <A href="recordset-object-ado.md">Requery</A> 方法的选项使用。</P>



## <a name="remarks"></a>备注

使用 **CommandType** 属性可以优化 [CommandText](commandtext-property-ado.md) 属性的求值过程。

如果 **CommandType** 属性值等于 **adCmdUnknown** （默认值），则可能会导致性能下降，因为 ADO 必须调用提供程序，以确定 **CommandText** 属性是 SQL 语句、存储过程还是表名称。如果知道所使用的命令类型，通过设置 **CommandType** 属性，可以指示 ADO 直接转到相关代码。如果 **CommandType** 属性与 **CommandText** 属性中的命令类型不匹配，调用 [Execute](https://msdn.microsoft.com/library/jj248785\(v=office.15\)) 方法时将发生错误。

