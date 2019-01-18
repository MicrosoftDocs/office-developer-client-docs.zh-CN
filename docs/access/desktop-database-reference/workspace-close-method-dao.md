---
title: Workspace.Close 方法 (DAO)
TOCTitle: Close Method
ms:assetid: 9b3d28f9-5cde-0dd9-8a4a-d2efaec5fe5d
ms:mtpsurl: https://msdn.microsoft.com/library/Ff198027(v=office.15)
ms:contentKeyID: 48546565
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 0049fb335c869a050a2c20d5740c487413c76786
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28708625"
---
# <a name="workspaceclose-method-dao"></a>Workspace.Close 方法 (DAO)


**适用于**： Access 2013、 Office 2013

关闭已打开的 **Workspace**。

## <a name="syntax"></a>语法

*表达式*。关闭

*表达式*一个代表**Workspace**对象的变量。

## <a name="remarks"></a>注解

如果在使用 **Close** 时 **Workspace** 对象已关闭，将发生运行时错误。

**Close**方法的替代方法是将对象变量的值设置为**Nothing** (Set dbsTemp = Nothing)。

