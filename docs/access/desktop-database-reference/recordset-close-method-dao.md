---
title: Recordset.Close Method (DAO)
TOCTitle: Close Method
ms:assetid: e76a81c6-ca0d-e310-c1dc-cbc5d6f6248b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836011(v=office.15)
ms:contentKeyID: 48548404
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: b4b008676e9c2836238d146a55a472b8ee0590c3
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25884266"
---
# <a name="recordsetclose-method-dao"></a>Recordset.Close Method (DAO)


**适用于**： Access 2013、 Office 2013

关闭已打开的 **Recordset**。

## <a name="syntax"></a>语法

*表达式*。关闭

*表达式*一个表示**Recordset**对象的变量。

## <a name="remarks"></a>注解

如果使用 **Close** 时 **Recordset** 对象已被关闭，将发生运行时错误。

如果尝试关闭的 **Connection** 对象具有任何打开的 **Recordset** 对象，则会关闭 **Recordset** 对象，同时取消任何待定的更新或编辑。同样，如果尝试关闭的 **Workspace** 对象具有任何打开的 **Connection** 对象，则会关闭那些 **Connection** 对象，这样就可以关闭它们的 **Recordset** 对象。

**Close**方法的替代方法是将对象变量的值设置为**Nothing** (Set dbsTemp = Nothing)。

