---
title: Recordset2 方法 (DAO)
TOCTitle: Cancel Method
ms:assetid: cae49f36-3aad-80d8-c15f-a7a584aa2e9b
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834366(v=office.15)
ms:contentKeyID: 48547703
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d203d1f1888539a4907da246e20ed711e61ee51f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307411"
---
# <a name="recordset2cancel-method-dao"></a>Recordset2 方法 (DAO)


**适用于**：Access 2013、Office 2013

## <a name="syntax"></a>语法

*表达式*。取消

*表达式*一个返回**Recordset2**对象的表达式。

## <a name="remarks"></a>注解

使用**Cancel**方法可以终止执行异步**Execute**或**OpenConnection**方法调用 (即, 使用即用 dbrunasync 选项调用方法)。 如果在尝试终止的方法中未使用即用 dbrunasync, 则 "**取消**" 将返回运行时错误。

