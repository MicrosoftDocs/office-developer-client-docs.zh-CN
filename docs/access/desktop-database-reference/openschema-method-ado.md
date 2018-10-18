---
title: OpenSchema 方法 (ADO)
TOCTitle: OpenSchema Method (ADO)
ms:assetid: 57771163-a14e-207a-2942-849acb79a9a1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249294(v=office.15)
ms:contentKeyID: 48544970
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ddd823baf153ebc78fc34ca838184f415edd29ef
ms.sourcegitcommit: a49b77f4c8cec69f90656a86f0872cf34c35968e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "25605917"
---
# <a name="openschema-method-ado"></a>OpenSchema 方法 (ADO)


**适用于**： Access 2013 |Office 2013


用于从提供程序获取数据库架构信息。

## <a name="syntax"></a>语法

**设置 *** recordset* = *连接*。OpenSchema (* QueryType *，*条件*， *SchemaID*)

<<<<<<< 标头
## <a name="return-values"></a>返回值
=======
## <a name="return-values"></a>返回值
>>>>>>> master

返回包含架构信息的 [Recordset](recordset-object-ado.md) 对象。 **Recordset** 将作为只读的静态游标打开。 *QueryType*确定**Recordset**中显示的列。

## <a name="parameters"></a>参数

  - *QueryType*

  - 任何 [SchemaEnum](schemaenum.md) 值，表示要运行的架构查询类型。

  - *Criteria*

  - 可选。 每个*QueryType*选项，如**SchemaEnum**中列出的查询约束数组。

  - *SchemaID*

  - 提供程序架构查询的 GUID 不是由 OLE DB 规范定义的。 此参数是必需的如果*QueryType*设置为**adSchemaProviderSpecific**;否则，它将不使用。

## <a name="remarks"></a>备注

**OpenSchema** 方法返回有关数据源的自描述信息，例如数据源中有哪些表、表中有哪些列以及支持哪些数据类型。

*QueryType*参数是表示的列 （架构） 返回的 GUID。 OLE DB 规范具有架构的完整列表。

*Criteria* 参数限制架构查询的结果。*Criteria* 指定生成的 **Recordset** 中相应的列子集（称为*约束列*）中必须出现的值数组。

如果提供程序定义自己的非标准架构查询外部上面列出的那些常量**adSchemaProviderSpecific**用于*QueryType*参数。 使用此常量时， *SchemaID*参数必须通过执行架构查询的 GUID。 如果设置为**adSchemaProviderSpecific** *QueryType*但未提供*SchemaID* ，将导致错误。

提供程序不需要支持所有 OLE DB 标准架构查询。 具体来说，只有 **adSchemaTables** 、 **adSchemaColumns** 和 **adSchemaProviderTypes** 是 OLE DB 规范所必需的。 但是，提供程序不需要支持这些架构查询上面列出的*条件*约束。

**远程数据服务用法****OpenSchema**方法不可用在客户端[Connection](connection-object-ado.md)对象上。


> [!NOTE]
> <P>在 Visual Basic 中，从 <STRONG>Connection</STRONG> 对象的 <STRONG>OpenSchema</STRONG> 方法返回的 <STRONG>Recordset</STRONG> 中具有四字节无符号整数 (DBTYPE UI4) 的列不能与其他变量进行比较。有关 OLE DB 数据类型的详细信息，请参阅<EM>《Microsoft OLE DB 程序员参考》</EM>的第 13 章和附录 A。</P>


