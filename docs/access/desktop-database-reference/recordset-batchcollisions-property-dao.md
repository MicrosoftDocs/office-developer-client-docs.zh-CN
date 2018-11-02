---
title: Recordset.BatchCollisions 属性 (DAO)
TOCTitle: BatchCollisions Property
ms:assetid: 53e5572b-770c-9ea5-31a5-984abdf66faa
ms:mtpsurl: https://msdn.microsoft.com/library/Ff194079(v=office.15)
ms:contentKeyID: 48544881
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c151868e349621d964f61058cfe82458764cf443
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25929088"
---
# <a name="recordsetbatchcollisions-property-dao"></a>Recordset.BatchCollisions 属性 (DAO)


**适用于**： Access 2013、 Office 2013

## <a name="syntax"></a>语法

*表达式*。BatchCollisions

*表达式*一个表示**Recordset**对象的变量。

## <a name="remarks"></a>注解

该属性包含一个书签数组，用于指示上次尝试的批 **[Update](recordset-update-method-dao.md)** 调用中遇到冲突的行。 **[BatchCollisionCount](recordset-batchcollisioncount-property-dao.md)** 属性指示该数组中的元素数。

如果将正在工作的 **[Recordset](recordset-object-dao.md)** 对象的 **[Bookmark](recordset-bookmark-property-dao.md)** 属性设置为 **BatchCollisions** 数组中的书签值，则可以移到无法完成最近一次批模式更新操作的每条记录。

更正冲突记录后，可再次调用批模式 **Update** 方法。此时，DAO 将尝试进行另一次批更新，同时 **BatchCollisions** 属性将再次反映第二次尝试失败的记录集。不会在当前尝试中发送上一次尝试成功的任何记录，因为这些记录的 **[RecordStatus](recordset-recordstatus-property-dao.md)** 属性现在已经为 dbRecordUnmodified。只要发生冲突，此过程就会继续下去，直到您放弃更新并关闭结果集为止。

每次执行批模式的 **Update** 方法时，都会重新创建此数组。

