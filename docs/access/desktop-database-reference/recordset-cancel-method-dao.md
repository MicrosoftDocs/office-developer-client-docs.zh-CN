---
title: Recordset.Cancel Method (DAO)
TOCTitle: Cancel Method
ms:assetid: 89acfbf1-b937-dc19-ada1-6f8f50489147
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197080(v=office.15)
ms:contentKeyID: 48546169
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1d7e77bd844385b9400449027312dacc02940e58
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466236"
---
# <a name="recordsetcancel-method-dao"></a>Recordset.Cancel Method (DAO)


**适用于**： Access 2013 |Office 2013

## <a name="syntax"></a>语法

*表达式*。取消

*表达式*一个表示**Recordset**对象的变量。

## <a name="remarks"></a>说明

使用**Cancel**方法可以终止执行异步**Execute**或**OpenConnection**方法调用 （即，该方法使用 dbRunAsync 选项调用）。 如果您正在尝试进行终止的方法中未使用 dbRunAsync，则**取消**将返回一个运行时错误。

