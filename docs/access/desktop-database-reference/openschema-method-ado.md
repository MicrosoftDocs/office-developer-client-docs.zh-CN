---
title: OpenSchema 方法 (ADO)
TOCTitle: OpenSchema method (ADO)
ms:assetid: 57771163-a14e-207a-2942-849acb79a9a1
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249294(v=office.15)
ms:contentKeyID: 48544970
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 43ca69b9d761629d42138780517f8de806ed7e8c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288334"
---
# <a name="openschema-method-ado"></a>OpenSchema 方法 (ADO)

**适用于**：Access 2013、Office 2013

用于从提供程序获取数据库架构信息。

## <a name="syntax"></a>语法

**Set * * * recordset* = *连接*。OpenSchema (* QueryType *, *Criteria*, *SchemaID*)

## <a name="return-values"></a>返回值

返回包含架构信息的 [Recordset](recordset-object-ado.md) 对象。 **Recordset** 将作为只读的静态游标打开。 *QueryType* 确定哪些列显示在 **Recordset** 中。

## <a name="parameters"></a>参数

|参数|描述|
|:--------|:----------|
|*QueryType* |任何 [SchemaEnum](schemaenum.md) 值，表示要运行的架构查询类型。|
|*Criteria* |可选。 针对每个 *QueryType* 选项的查询约束的数组，如 **SchemaEnum** 中所列。|
|*SchemaID* |提供程序架构查询的 GUID 不是由 OLE DB 规范定义的。如果 *QueryType* 设置为 **adSchemaProviderSpecific**，则该参数是必需的；否则，不使用该参数。|

## <a name="remarks"></a>注解

**OpenSchema** 方法返回有关数据源的自描述信息，例如数据源中有哪些表、表中有哪些列以及支持哪些数据类型。

*QueryType* 参数是一个 GUID，用于指示返回的列（架构）。OLE DB 规范具有架构的完整列表。

*Criteria* 参数限制架构查询的结果。*Criteria* 指定生成的 **Recordset** 中相应的列子集（称为*约束列*）中必须出现的值数组。

如果提供程序自己定义的非标准架构查询在前面没有列出，则常量 **adSchemaProviderSpecific** 用于 *QueryType* 参数。使用该常量时，必须使用 *SchemaID* 参数才能传递要执行的架构查询的 GUID。如果 *QueryType* 设置为 **adSchemaProviderSpecific** 但未提供 *SchemaID*，将生成错误。

提供程序不需要支持所有 OLE DB 标准架构查询。具体来说，只有 **adSchemaTables**、**adSchemaColumns** 和 **adSchemaProviderTypes** 是 OLE DB 规范所必需的。但是，对于这些架构查询，提供程序不需要支持上面所列的 *Criteria* 约束。

**远程数据服务使用情况****OpenSchema**方法在客户端[Connection](connection-object-ado.md)对象上不可用。

> [!NOTE]
> 在 Visual Basic 中，从 **Connection** 对象的 **OpenSchema** 方法返回的 **Recordset** 中具有四字节无符号整数 (DBTYPE UI4) 的列不能与其他变量进行比较。有关 OLE DB 数据类型的详细信息，请参阅 *《Microsoft OLE DB 程序员参考》* 的第 13 章和附录 A。


