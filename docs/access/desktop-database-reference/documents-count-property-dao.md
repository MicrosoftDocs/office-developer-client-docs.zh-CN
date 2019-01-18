---
title: Documents.Count 属性 (DAO)
TOCTitle: Count Property
ms:assetid: 3fc0b1e6-f7be-cd43-711f-5cf5763fe7f6
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192858(v=office.15)
ms:contentKeyID: 48544407
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053325
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: dd9cc563ecc885fca4fa0ef5829d82aa2f8bfef6
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28710683"
---
# <a name="documentscount-property-dao"></a>Documents.Count 属性 (DAO)


**适用于**： Access 2013、 Office 2013

返回指定集合中的对象数。只读。

## <a name="syntax"></a>语法

*表达式*。计数

*表达式*一个代表**Documents**对象的变量。

## <a name="remarks"></a>注解

由于集合的成员是从 0 开始编号的，因此应始终将循环编写为从第 0 个成员开始，而在 **Count** 属性的值减 1 处结束。如果想要在不检查 **Count** 属性的情况下遍历集合成员，则可以使用 **For Each...Next** 命令。

**Count** 属性设置从不为 Null。如果其值为 0，则表示集合中没有对象。

