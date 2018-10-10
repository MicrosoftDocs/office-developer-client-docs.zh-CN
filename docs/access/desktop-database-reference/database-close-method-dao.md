---
title: Database.Close Method (DAO)
TOCTitle: Close Method
ms:assetid: b777ee92-172a-3342-31fc-76e7361c47fd
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822418(v=office.15)
ms:contentKeyID: 48547296
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 97246da6224ee04fa435638a0cb11d1bdac8859f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466242"
---
# <a name="databaseclose-method-dao"></a>Database.Close Method (DAO)


**适用于**： Access 2013 |Office 2013

关闭已打开的 **Database**。

## <a name="syntax"></a>语法

*表达式*。关闭

*表达式*一个代表**Database**对象的变量。

## <a name="remarks"></a>注解

如果使用 **Close** 时 **Database** 对象已被关闭，将发生运行时错误。

**Close**方法的替代方法是将对象变量的值设置为**Nothing** (Set dbsTemp = Nothing)。

