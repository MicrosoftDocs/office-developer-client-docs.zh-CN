---
title: Recordset2.Close Method (DAO)
TOCTitle: Close Method
ms:assetid: ef816969-9857-37cf-9562-d5c80d2815ea
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836412(v=office.15)
ms:contentKeyID: 48548584
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f20c10ac6bb6fc313ffecb56b0d2852c3b488c26
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467579"
---
# <a name="recordset2close-method-dao"></a>Recordset2.Close Method (DAO)


**适用于**： Access 2013 |Office 2013

关闭已打开的 **Recordset**。

## <a name="syntax"></a>语法

*表达式*。关闭

*表达式*一个表示**Recordset2**对象的变量。

## <a name="remarks"></a>注解

如果使用 **Close** 时 **Recordset** 对象已被关闭，将发生运行时错误。

如果尝试关闭的 **Connection** 对象具有任何打开的 **Recordset** 对象，则会关闭 **Recordset** 对象，同时取消任何待定的更新或编辑。同样，如果尝试关闭的 **Workspace** 对象具有任何打开的 **Connection** 对象，则会关闭那些 **Connection** 对象，这样就可以关闭它们的 **Recordset** 对象。

**Close**方法的替代方法是将对象变量的值设置为**Nothing** (Set dbsTemp = Nothing)。

