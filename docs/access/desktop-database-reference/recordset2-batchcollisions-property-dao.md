---
title: Recordset2.BatchCollisions Property (DAO)
TOCTitle: BatchCollisions Property
ms:assetid: 07d6c25f-baf5-f7d6-d225-0447e0f78fe6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844993(v=office.15)
ms:contentKeyID: 48543085
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1101180
f1_categories:
- Office.Version=v15
ms.openlocfilehash: ee26b84237b1bf4a8603295a6e6d66e6f30303e9
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25885889"
---
# <a name="recordset2batchcollisions-property-dao"></a>Recordset2.BatchCollisions Property (DAO)


**适用于**： Access 2013、 Office 2013

## <a name="syntax"></a>语法

*表达式*。BatchCollisions

*表达式*一个表示**Recordset2**对象的变量。

## <a name="remarks"></a>注解

该属性包含一个书签数组，用于指示上次尝试的批 **[Update](recordset2-update-method-dao.md)** 调用中遇到冲突的行。 **[BatchCollisionCount](recordset2-batchcollisioncount-property-dao.md)** 属性指示该数组中的元素数。

如果将正在工作的 **Recordset** 对象的 **[Bookmark](recordset2-bookmark-property-dao.md)** 属性设置为 **BatchCollisions** 数组中的书签值，则可以移到无法完成最近一次批模式更新操作的每条记录。

更正冲突记录后，可再次调用批模式 **Update** 方法。此时，DAO 将尝试进行另一次批更新，同时 **BatchCollisions** 属性将再次反映第二次尝试失败的记录集。不会在当前尝试中发送上一次尝试成功的任何记录，因为这些记录的 **[RecordStatus](recordset2-recordstatus-property-dao.md)** 属性现在已经为 dbRecordUnmodified。只要发生冲突，此过程就会继续下去，直到您放弃更新并关闭结果集为止。

每次执行批模式的 **Update** 方法时，都会重新创建此数组。

