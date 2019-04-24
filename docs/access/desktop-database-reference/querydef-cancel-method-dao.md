---
title: QueryDef. Cancel 方法 (DAO)
TOCTitle: Cancel Method
ms:assetid: 91e61012-c01c-4c24-185c-bdadb7f33a58
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197642(v=office.15)
ms:contentKeyID: 48546364
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1055470
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 56a4ba804dba25eb0b4722bcf5396229ee003f43
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301118"
---
# <a name="querydefcancel-method-dao"></a>QueryDef. Cancel 方法 (DAO)


**适用于**：Access 2013、Office 2013

## <a name="syntax"></a>语法

*表达式*。取消

*表达式*一个代表**QueryDef**对象的变量。

## <a name="remarks"></a>注解

使用**Cancel**方法可以终止执行异步**Execute**或**OpenConnection**方法调用 (即, 使用即用 dbrunasync 选项调用方法)。 如果在尝试终止的方法中未使用即用 dbrunasync, 则 "**取消**" 将返回运行时错误。

