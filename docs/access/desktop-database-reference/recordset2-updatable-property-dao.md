---
title: Recordset2 属性 (DAO)
TOCTitle: Updatable Property
ms:assetid: ad8184b6-ffe3-dde6-ddee-4b23cdaa9c59
ms:mtpsurl: https://msdn.microsoft.com/library/Ff821726(v=office.15)
ms:contentKeyID: 48547041
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 5b6e6f2a20b4779259b80eff1fc152abe3698217
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309322"
---
# <a name="recordset2updatable-property-dao"></a>Recordset2 属性 (DAO)


**适用于**：Access 2013、Office 2013

返回一个值，该值指示是否可以更改 DAO 对象。 只读 **Boolean** 类型。

## <a name="syntax"></a>语法

*表达式*。更新

*表达式*一个代表**Recordset2**对象的变量。

## <a name="remarks"></a>注解

快照类型和仅向前类型的 Recordset 对象始终返回 **False**。

许多对象类型可以包含不能更新的字段。例如，您可以创建动态集类型的 **Recordset** 对象，在该对象中只能更改某些字段。这些字段可能是固定的或包含自动增长的数据，或者动态集可以由合并可更新表和不可更新表的查询产生。

如果该对象仅包含只读字段，则 **Updatable** 属性的值为 **False**。当一个或多个字段可更新时，属性的值为 **True**。您只能编辑可更新的字段。如果尝试向只读字段分配新值，则会发生可捕获的错误。

由于可更新的对象可以包含只读字段，因此请在编辑记录之前检查 **Recordset** 对象的 **Fields** 集合中每个字段的 **DataUpdatable** 属性。

