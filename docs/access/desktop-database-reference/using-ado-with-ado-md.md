---
title: 将 ADO 与 ADO MD 结合使用
TOCTitle: Using ADO with ADO MD
ms:assetid: 93d1d270-b8d0-4489-d441-11a61887291c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249655(v=office.15)
ms:contentKeyID: 48546405
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 80c87f57a96f98de704e3cfa9b7689a522e4a7af
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32312745"
---
# <a name="using-ado-with-ado-md"></a>将 ADO 与 ADO MD 结合使用


**适用于**：Access 2013、Office 2013

ADO 和 ADO MD 是两种既相关又独立的对象模型。ADO 提供的对象用于连接数据源、执行命令、检索表格式数据和表格式架构元数据，以及查看提供程序错误信息。ADO MD 提供的对象则用于检索多维数据以及查看多维架构元数据。

使用 MDP 时，您可以选择将 ADO、ADO MD 或者两者同时用于您的应用程序。通过在项目中引用这两个库，您将可以使用 MDP 提供的全部功能。

多维数据集的平面表格视图通常对用户很有用。 使用 ADO [Recordset](recordset-object-ado.md) 对象可做到这一点。 此时，请将 [Cellset](cellset-object-ado-md.md) 的源指定为 ***Recordset*** 的 Open 方法的 **[Source](open-method-ado-recordset.md)** 参数，而不是 ADO MD **Cellset** 的源。

以表格式视图而不是作为对象层次结构来查看架构元数据，可能也很有用。 ADO [Connection](connection-object-ado.md) 对象的 [OpenSchema](openschema-method-ado.md) 方法使用户可以打开包含架构信息的 **Recordset**。 ***OpenSchema*** 方法的 **QueryType** 参数有多个专门与 MDP 关联的 [SchemaEnum](schemaenum.md) 值。 这些值是：

  - **adSchemaCubes**

  - **adSchemaDimensions**

  - **adSchemaHierarchies**

  - **adSchemaLevels**

  - **adSchemaMeasures**

  - **adSchemaMembers**

若要将 ADO 枚举值与 ADO MD 属性或方法一起使用，您的项目必须同时引用 ADO 和 ADO MD 库。例如，可将 ADO **adState** 枚举值与 ADO MD [State](state-property-ado-md.md) 属性一起使用。有关如何建立库引用的更多信息，请参阅您的开发工具文档。

有关 ADO 对象和方法的更多信息，请参阅 [ADO API 参考](ado-api-reference.md)。

