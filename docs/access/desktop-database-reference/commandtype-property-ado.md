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
# <a name="commandtype-property-ado"></a><span data-ttu-id="8332d-102">CommandType 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="8332d-102">CommandType Property (ADO)</span></span>


<span data-ttu-id="8332d-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="8332d-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="8332d-104">指示 [Command](command-object-ado.md) 对象的类型。</span><span class="sxs-lookup"><span data-stu-id="8332d-104">Indicates the type of a [Command](command-object-ado.md) object.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="8332d-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="8332d-105">Settings and Return Values</span></span>

<span data-ttu-id="8332d-106">设置或返回一个或多个 [CommandTypeEnum](commandtypeenum.md) 值。</span><span class="sxs-lookup"><span data-stu-id="8332d-106">Sets or returns one or more [CommandTypeEnum](commandtypeenum.md) values.</span></span>


> [!NOTE]
> <P><span data-ttu-id="8332d-p101">[!注释] 不要将 <STRONG>adCmdFile</STRONG> 或 <STRONG>adCmdTableDirect</STRONG> 的 <STRONG>CommandTypeEnum</STRONG> 值与 <STRONG>CommandType</STRONG> 一起使用。这些值仅可作为 <A href="open-method-ado-recordset.md">Recordset</A> 的 <A href="requery-method-ado.md">Open</A> 和 <A href="recordset-object-ado.md">Requery</A> 方法的选项使用。</span><span class="sxs-lookup"><span data-stu-id="8332d-p101">Do not use the <STRONG>CommandTypeEnum</STRONG> values of <STRONG>adCmdFile</STRONG> or <STRONG>adCmdTableDirect</STRONG> with <STRONG>CommandType</STRONG>. These values can only be used as options with the <A href="open-method-ado-recordset.md">Open</A> and <A href="requery-method-ado.md">Requery</A> methods of a <A href="recordset-object-ado.md">Recordset</A>.</span></span></P>



## <a name="remarks"></a><span data-ttu-id="8332d-109">备注</span><span class="sxs-lookup"><span data-stu-id="8332d-109">Remarks</span></span>

<span data-ttu-id="8332d-110">使用 **CommandType** 属性可以优化 [CommandText](commandtext-property-ado.md) 属性的求值过程。</span><span class="sxs-lookup"><span data-stu-id="8332d-110">Use the **CommandType** property to optimize evaluation of the [CommandText](commandtext-property-ado.md) property.</span></span>

<span data-ttu-id="8332d-p102">如果 **CommandType** 属性值等于 **adCmdUnknown** （默认值），则可能会导致性能下降，因为 ADO 必须调用提供程序，以确定 **CommandText** 属性是 SQL 语句、存储过程还是表名称。如果知道所使用的命令类型，通过设置 **CommandType** 属性，可以指示 ADO 直接转到相关代码。如果 **CommandType** 属性与 **CommandText** 属性中的命令类型不匹配，调用 [Execute](https://msdn.microsoft.com/library/jj248785\(v=office.15\)) 方法时将发生错误。</span><span class="sxs-lookup"><span data-stu-id="8332d-p102">If the **CommandType** property value equals **adCmdUnknown** (the default value), you may experience diminished performance because ADO must make calls to the provider to determine if the **CommandText** property is an SQL statement, a stored procedure, or a table name. If you know what type of command you're using, setting the **CommandType** property instructs ADO to go directly to the relevant code. If the **CommandType** property does not match the type of command in the **CommandText** property, an error occurs when you call the [Execute](https://msdn.microsoft.com/library/jj248785\(v=office.15\)) method.</span></span>

