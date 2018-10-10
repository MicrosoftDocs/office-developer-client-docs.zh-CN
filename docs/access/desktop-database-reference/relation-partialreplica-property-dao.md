---
title: Relation.PartialReplica Property (DAO)
TOCTitle: PartialReplica Property
ms:assetid: 3cb15639-371e-06e3-e2ba-30466ce09a72
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192692(v=office.15)
ms:contentKeyID: 48544324
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053557
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 4b1768b61dcb6b14bc5d67e945379c5ebb5c399a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25468038"
---
# <a name="relationpartialreplica-property-dao"></a>Relation.PartialReplica Property (DAO)


**适用于**： Access 2013 |Office 2013

设置或返回 **Relation** 对象的值，用于指示从完全副本填充部分副本时是否应当考虑关系。（仅适用于 Microsoft Access 数据库引擎数据库）。可读写 **Boolean**。

## <a name="syntax"></a>语法

*表达式*。PartialReplica

*表达式*一个返回**Relation**对象的表达式。

## <a name="remarks"></a>注解

设置或返回值属于 Boolean 数据类型，如果同步期间应当实施关系，则为 **True**。

该属性使您可以基于表之间的关系将完全副本中的数据复制到部分副本中。如果单独设置 **ReplicaFilter** 属性无法准确指定应当复制到部分副本的数据，则可以使用 **PartialReplica** 属性。例如，假设您有一个数据库，其中的“客户”表与“订单”表具有一对多关系，您想要配置只从加利福尼亚地区复制订单（而不是复制所有订单）的部分副本。由于“地区”字段位于“客户”表而不是“订单”表中，因此无法将“订单”表中的 **ReplicaFilter** 属性设置为 Region = 'CA'。

若要从加利福尼亚地区复制所有订单，必须指明在复制期间"订单"与"客户"表之间的关系将是活动的。一旦创建了部分副本，以下步骤将使用加利福尼亚地区的所有订单填充该副本：

1.  设置客户**TableDef**对象的**ReplicaFilter**属性"区域 = 'CA'"。

2.  对于对应于"订单"与"客户"之间的关系的 **Relation** 对象，将 **PartialReplica** 属性设置为 **True**。

3.  调用 **PopulatePartial** 方法。
    

> [!NOTE]
> <P>当设置副本筛选器或副本关系时，一定要注意，不满足限制条件的部分副本中的记录将会从部分副本中删除，而不是从完全副本中删除。例如，假设您将部分副本中“客户”表的 <STRONG>TableDef</STRONG> 的 <STRONG>ReplicaFilter</STRONG> 属性设置为 "Region = 'CA'"，然后重新填充数据库。此操作将会插入或更新加利福尼亚客户的所有记录。之后，如果您将 <STRONG>ReplicaFilter</STRONG> 属性设置为 "Region = 'FL'" 并重新填充数据库，则部分副本中的所有加利福尼亚地区的记录都将被删除，将从完全副本中插入佛罗里达客户的所有记录。不会删除完全副本中的任何记录。在设置 <STRONG>ReplicaFilter</STRONG> 或 <STRONG>PartialReplica</STRONG> 属性之前，最好将设置这些属性的部分副本与完全副本同步。这可以确保在部分副本中删除任何记录之前，部分副本中的挂起更改合并到完全副本中。</P>


