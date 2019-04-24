---
title: 索引号属性 (DAO)
TOCTitle: Count Property
ms:assetid: 195ede10-f91e-50c6-6af4-b318c476b9ea
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845647(v=office.15)
ms:contentKeyID: 48543499
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: cffbf14e73e97113194eb25b8e0d5799d3578086
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32291543"
---
# <a name="indexescount-property-dao"></a>索引号属性 (DAO)


**适用于**：Access 2013、Office 2013

返回指定集合中的对象数。 此为只读属性。

## <a name="syntax"></a>语法

*表达式*。计数

*表达式*一个代表**索引**对象的变量。

## <a name="remarks"></a>注解

由于集合的成员由 0 开始，因此应始终将循环编写为从第 0 个成员开始，并在 **Count** 属性的值减 1 处结束。如果需要在集合的成员中循环且不检查 **Count** 属性，可以使用 **For Each...Next** 命令。

**Count** 属性设置从不为 Null。如果其值为 0，则表示集合中没有对象。

