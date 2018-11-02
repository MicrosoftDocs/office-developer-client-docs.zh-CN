---
title: NextRecordset 方法 (ADO)
TOCTitle: NextRecordset method (ADO)
ms:assetid: d2776dd5-d521-c57f-dbe5-e02ee238104d
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250051(v=office.15)
ms:contentKeyID: 48547887
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: da7e23974b9541a29aa78ba9d7de22e76102971b
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25929550"
---
# <a name="nextrecordset-method-ado"></a>NextRecordset 方法 (ADO)


**适用于**： Access 2013、 Office 2013
 

用于通过执行一系列命令，清除当前 [Recordset](recordset-object-ado.md) 对象并返回下一个 **Recordset** 。

## <a name="syntax"></a>语法

设置*recordset2* = *recordset1*。NextRecordset (*RecordsAffected* )

## <a name="return-value"></a>返回值

返回一个 **Recordset** 对象。在语法模型中，*recordset1* 和 *recordset2* 可以是相同的 **Recordset** 对象，也可以是不同的对象。使用不同的 **Recordset** 对象时，在调用 **NextRecordset** 之后重置原始 **Recordset** (*recordset1*) 的 **ActiveConnection** 属性将生成错误。

## <a name="parameters"></a>参数

- *RecordsAffected*

- 可选。 **长整型** 变量，提供程序将受当前操作影响的记录数返回到该变量。


> [!NOTE]
> <P>[!注释] 该参数仅返回受操作影响的记录数；它并不返回来自选择语句（用于生成 <STRONG>Recordset</STRONG> ）的记录计数。</P>



## <a name="remarks"></a>备注

使用 **NextRecordset** 方法可以返回复合命令语句中下一个命令的结果，或可返回多个结果的存储过程的结果。 如果您打开一个基于复合命令语句的**Recordset**对象 (例如，"选择\*TABLE1;选择\*从 table2") 上的[命令](command-object-ado.md)或[Open](open-method-ado-recordset.md)方法在**Recordset**上的使用[Execute](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/execute-method-ado-command)方法，ADO 执行仅的第一个命令，并将结果返回到*recordset*。 若要访问语句中后续命令的结果，请调用 **NextRecordset** 方法。

只要存在其他结果，且包含复合语句的 **Recordset** 未断开连接或跨进程边界封送，则 **NextRecordset** 方法将继续返回 **Recordset** 对象。 如果返回行的命令成功执行但未返回记录，则返回的 **Recordset** 对象将打开，但为空。 可通过验证 [BOF](bof-eof-properties-ado.md) 和 [EOF](bof-eof-properties-ado.md) 属性是否都为 **True** 来测试该情况。 如果非行返回命令执行成功，返回的**Recordset**对象将关闭，这可以验证通过测试在**Recordset**上的[状态](state-property-ado.md)属性。 当没有更多结果时， *recordset*将设置为*Nothing*。

**NextRecordset** 方法对于断开连接的 **Recordset** 对象不可用，在该对象中， [ActiveConnection](activeconnection-property-ado.md) 已设置为 **Nothing** （用 Microsoft Visual Basic）或 NULL（用其他语言）。

如果正在进行编辑，且正处于即时更新模式下，则调用 **NextRecordset** 方法会生成错误；应首先调用 [Update](update-method-ado.md) 或 [CancelUpdate](cancelupdate-method-ado.md) 方法。

若要通过填充 [Parameters](parameters-collection-ado.md) 集合或通过使用原始的 **Open** 或 **Execute** 调用传递数组，在复合语句中传递多个命令的参数，这些参数在集合或数组中的顺序必须与它们各自的命令在命令系列中的顺序相同。读取输出参数值之前，必须完成所有结果的读取。

OLE DB 提供程序确定什么时候执行复合语句中的每个命令。例如，[Microsoft OLE DB Provider for SQL Server](microsoft-ole-db-provider-for-sql-server.md) 在收到复合语句时执行一批中的所有命令。调用 **NextRecordset** 时，将仅返回生成的 **Recordset** 。

但是，其他提供程序可能只有在调用 NextRecordset 之后才能执行语句中的下一个命令。对于这些提供程序，如果在单步执行整个命令语句之前显式关闭 **Recordset** 对象，ADO 将永远不会执行剩余的语句。

