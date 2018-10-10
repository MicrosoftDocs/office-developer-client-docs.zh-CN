---
title: Recordset2.UpdateOptions Property (DAO)
TOCTitle: UpdateOptions Property
ms:assetid: 2692480e-c472-dd8e-f91a-939776822ece
ms:mtpsurl: https://msdn.microsoft.com/library/Ff191899(v=office.15)
ms:contentKeyID: 48543816
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 508727437506e418fa2c8804cc9974f6d3ee7691
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466387"
---
# <a name="recordset2updateoptions-property-dao"></a>Recordset2.UpdateOptions Property (DAO)


**适用于**： Access 2013 |Office 2013

## <a name="syntax"></a>语法

*表达式*。UpdateOptions

*表达式*一个表示**Recordset2**对象的变量。

## <a name="remarks"></a>注解

当执行批处理模式的 **[Update](recordset2-update-method-dao.md)** 时，DAO 和客户端批处理光标库创建一系列 SQL UPDATE 语句，以进行所需的更改。 为每次更新创建了 SQL WHERE 子句，以便隔离被 **[RecordStatus](recordset2-recordstatus-property-dao.md)** 属性标记为已更改的记录。 由于某些远程服务器使用触发器或其他方法实施参照完整性，所以将更新的字段限制为受更改影响的那些记录通常是很有必要的。 

为此，需要将 **UpdateOptions** 属性设置为常量 **dbCriteriaKey**、 **dbCriteriaModValues**、 **dbCriteriaAllCols** 或 **dbCriteriaTimeStamp** 之一。 这样，将只执行触发器代码的最小绝对量。 因此，可以更快速地执行更新操作，潜在错误也会较少。

还可以连接 **dbCriteriaDeleteInsert** 或 **dbCriteriaUpdate**，以确定在将批修改发送回服务器时，对于每次更新是使用 SQL DELETE 和 INSERT 语句集合，还是使用 SQL UPDATE 语句。在前一种情况下，需要两个单独操作才能更新记录。在某些情况下，尤其是远程系统实施 DELETE、INSERT 和 UPDATE 触发器时，选择正确的 **UpdateOptions** 属性设置会显著影响性能。

如果您不指定任何常量，将使用 **dbCriteriaUpdate** 和 **dbCriteriaKey**。

新添加的记录始终生成 INSERT 语句，删除的记录始终生成 DELETE 语句，所以该属性只对光标库如何更新修改的记录适用。

