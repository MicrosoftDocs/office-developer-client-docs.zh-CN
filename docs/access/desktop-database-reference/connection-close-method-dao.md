---
title: Connection 方法 (DAO)
TOCTitle: Close Method
ms:assetid: 9b1a77cb-da12-24d6-892f-a56be103d51d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198015(v=office.15)
ms:contentKeyID: 48546559
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: bf99abf97a2eb1b88e7056a36c160eb774959719
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295959"
---
# <a name="connectionclose-method-dao"></a>Connection 方法 (DAO)


**适用于**：Access 2013、Office 2013

关闭已打开的 **Connection**。

## <a name="syntax"></a>语法

*表达式*。关闭

*表达式*一个代表**Connection**对象的变量。

## <a name="remarks"></a>注解

如果使用 **Close** 时 **Recordset** 对象已被关闭，将发生运行时错误。

如果尝试关闭的 **Connection** 对象具有任何打开的 **Recordset** 对象，则会关闭 **Recordset** 对象，同时取消任何待定的更新或编辑。同样，如果尝试关闭的 **Workspace** 对象具有任何打开的 **Connection** 对象，则会关闭那些 **Connection** 对象，这样就可以关闭它们的 **Recordset** 对象。

**Close**方法的替代方法是将对象变量的值设置为**nothing** (set dbsTemp = Nothing)。

