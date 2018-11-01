---
title: Parameters.Count Property (DAO)
TOCTitle: Count Property
ms:assetid: bc8c814b-da55-22b7-431f-a0f7e6cac994
ms:mtpsurl: https://msdn.microsoft.com/library/Ff822720(v=office.15)
ms:contentKeyID: 48547415
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: d9a45ce03c68b310042a1abd6673fb7811fa21d7
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25883811"
---
# <a name="parameterscount-property-dao"></a>Parameters.Count Property (DAO)


**适用于**： Access 2013、 Office 2013

返回指定集合中的对象数。只读。

## <a name="syntax"></a>语法

*表达式*。计数

*表达式*一个代表**Parameters**对象的变量。

## <a name="remarks"></a>注解

由于集合的成员是从 0 开始编号的，因此应始终将循环编写为从第 0 个成员开始，而在 **Count** 属性的值减 1 处结束。如果想要在不检查 **Count** 属性的情况下遍历集合成员，则可以使用 **For Each...Next** 命令。

**Count** 属性设置从不为 Null。如果其值为 0，则表示集合中没有对象。

