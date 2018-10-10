---
title: Refresh 方法 (ADO)
TOCTitle: Refresh Method (ADO)
ms:assetid: f1c8829f-9c7d-12b6-7470-727ff38d663e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250227(v=office.15)
ms:contentKeyID: 48548631
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1ea277f83c39bde4b5309a26b87961ff2325b145
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25465763"
---
# <a name="refresh-method-ado"></a>Refresh 方法 (ADO)


**适用于**： Access 2013 |Office 2013

更新集合中的对象，以反映提供程序特定的可用对象。

## <a name="syntax"></a>语法

*集合*。刷新

## <a name="remarks"></a>说明

**Refresh** 方法用于完成各种不同的任务，具体取决于从中调用该方法的集合。

## <a name="parameters"></a>Parameters

如果对 **Command** 对象的 [Parameters](command-object-ado.md) 集合使用 [Refresh](parameters-collection-ado.md) 方法，则会检索在 **Command** 对象中指定的存储过程或参数化查询的提供程序端参数信息。对于不支持存储过程调用或参数化查询的提供程序，该集合将为空。

在调用 [Refresh](activeconnection-property-ado.md) 方法之前，应当将 **Command** 对象的 [ActiveConnection](connection-object-ado.md) 属性设置为有效的 [Connection](commandtext-property-ado.md) 对象，将 [CommandText](commandtype-property-ado.md) 属性设置为有效的命令，并将 **CommandType** 属性设置为 **adCmdStoredProc** 。

如果在调用 **Refresh** 方法之前访问 **Parameters** 集合，则 ADO 将为您自动调用方法并填充集合。


> [!NOTE]
> <P>[!注释] 如果使用 <STRONG>Refresh</STRONG> 方法获取提供程序的参数信息，且该方法返回一个或多个可变长度数据类型 <A href="parameter-object-ado.md">Parameter</A> 对象，那么 ADO 会根据参数的最大潜在大小为参数分配内存，这将在执行过程中引发错误。在调用 <A href="size-property-ado.md">Execute</A> 方法以防止出错之前，应当显式设置这些参数的 <A href="https://msdn.microsoft.com/library/jj248785(v=office.15)">Size</A> 属性。</P>



**Fields**

对 **Fields** 集合使用 **Refresh** 方法没有明显的效果。若要检索基础数据库结构的更改，必须使用 [Requery](requery-method-ado.md) 方法或 [MoveFirst](recordset-object-ado.md) 方法（如果 [Recordset](movefirst-movelast-movenext-and-moveprevious-methods-ado.md) 对象不支持书签）。

**Properties**

如果对某些对象的 **Properties** 集合使用 **Refresh** 方法，则会用提供程序公开的动态属性来填充该集合。除 ADO 支持的内置属性之外，这些属性提供了有关提供程序特定功能的信息。

