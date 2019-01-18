---
title: Recordset2.Close 方法 (DAO)
TOCTitle: Close Method
ms:assetid: ef816969-9857-37cf-9562-d5c80d2815ea
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836412(v=office.15)
ms:contentKeyID: 48548584
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 178dec604a185da94493e6d586249bd2a633899c
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28708429"
---
# <a name="recordset2close-method-dao"></a>Recordset2.Close 方法 (DAO)


**适用于**： Access 2013、 Office 2013

关闭已打开的 **Recordset**。

## <a name="syntax"></a>语法

*表达式*。关闭

*表达式*一个表示**Recordset2**对象的变量。

## <a name="remarks"></a>注解

如果使用 **Close** 时 **Recordset** 对象已被关闭，将发生运行时错误。

如果尝试关闭的 **Connection** 对象具有任何打开的 **Recordset** 对象，则会关闭 **Recordset** 对象，同时取消任何待定的更新或编辑。同样，如果尝试关闭的 **Workspace** 对象具有任何打开的 **Connection** 对象，则会关闭那些 **Connection** 对象，这样就可以关闭它们的 **Recordset** 对象。

**Close**方法的替代方法是将对象变量的值设置为**Nothing** (Set dbsTemp = Nothing)。

