---
title: StillExecuting 属性 (DAO)
TOCTitle: StillExecuting Property
ms:assetid: 98e85d37-de50-afe1-dcca-01623546e0ad
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197953(v=office.15)
ms:contentKeyID: 48546505
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053584
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 60c0663eaa6857801555c6ce05f4256cfe4c290f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303414"
---
# <a name="querydefstillexecuting-property-dao"></a>StillExecuting 属性 (DAO)


**适用于**：Access 2013、Office 2013

## <a name="syntax"></a>语法

*表达式*。StillExecuting

*表达式*一个代表**QueryDef**对象的变量。

## <a name="remarks"></a>注解

使用 **StillExecuting** 属性可以确定最近调用的异步 **[Execute](querydef-execute-method-dao.md)** 或 **[OpenConnection](dbengine-openconnection-method-dao.md)** 方法（即用 **dbRunAsync** 选项执行的方法）是否已完成。在 **StillExecuting** 属性为 **True** 的情况下，不能访问任何返回的对象。

一旦 **StillExecuting** 属性返回 **False**，在返回相关 [**Connection**](connection-object-dao.md) 对象的 **OpenConnection** 调用之后，即可引用该对象。只要 **StillExecuting** 仍为 **True**，就不能引用该对象，而只能读取 **StillExecuting** 属性。

使用 **[Cancel](connection-cancel-method-dao.md)** 方法可以终止执行正在进行的任务。

