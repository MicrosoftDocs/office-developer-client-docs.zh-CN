---
title: Parameters 集合 (ADO)
TOCTitle: Parameters Collection (ADO)
ms:assetid: 554387c3-3572-5391-3b24-c7d3443844cd
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249283(v=office.15)
ms:contentKeyID: 48544923
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- ado210.chm1231103
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 96d2f4094c6b0df43e1579d7d35cbb78c12cc39c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466755"
---
# <a name="parameters-collection-ado"></a>Parameters 集合 (ADO)


**适用于**： Access 2013 |Office 2013

包含 [Command](parameter-object-ado.md) 对象的所有 [Parameter](command-object-ado.md) 对象。

## <a name="remarks"></a>说明

**Command** 对象具有一个由 **Parameter** 对象组成的 **Parameters** 集合。

如果对 [Command](refresh-method-ado.md) 对象的 **Parameters** 集合使用 **Refresh** 方法，则会检索在 **Command** 对象中指定的存储过程或参数化查询的提供程序参数信息。某些提供程序不支持存储过程调用或参数化查询；使用这种提供程序时，对 **Parameters** 集合调用 **Refresh** 方法将返回错误。

如果尚未定义自己的 **Parameter** 对象，当您在调用 **Refresh** 方法之前访问 **Parameters** 集合时，ADO 将为您自动调用该方法并填充集合。

如果您知道与要调用的存储过程或参数化查询关联的参数的属性，可以最大限度地减少对提供程序的调用以改进性能。可以使用 [CreateParameter](createparameter-method-ado.md) 方法创建具适当属性设置的 **Parameter** 对象，并用 [Append](append-method-ado.md) 方法将对象添加到 **Parameters** 集合。这样一来，无需调用参数信息的提供程序，即可设置和返回参数值。如果正在写入不提供参数信息的提供程序，则必须使用此方法手动填充 **Parameters** 集合，才能使用参数。如果必要，可使用 [Delete](delete-method-ado-parameters-collection.md) 方法从 **Parameters** 集合中删除 **Parameter** 对象。

**Recordset** 关闭时， **Recordset** 的 **Parameters** 集合中的对象超出范围（不可用）。

