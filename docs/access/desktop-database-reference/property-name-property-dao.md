---
title: Property.Name 属性 (DAO)
TOCTitle: Name Property
ms:assetid: 0dae15e0-5d2e-3bb4-8a44-98db4a8ce516
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845211(v=office.15)
ms:contentKeyID: 48543225
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: aa552a477ad6b9f047f3fd2231e4b0ba8d26c1ce
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28700407"
---
# <a name="propertyname-property-dao"></a>Property.Name 属性 (DAO)


**适用于**： Access 2013、 Office 2013

返回或设置指定对象的名称。对于尚未追加到集合中的对象，该属性为可读/写 **String** 类型；对于已追加到集合中的对象，该属性为只读 **String** 类型。

## <a name="syntax"></a>语法

*表达式*。名称

*表达式*一个代表**Property**对象的变量。

## <a name="remarks"></a>注解

内置属性的 **Name** 属性始终为只读。

**Property** 对象名称的最大长度为 64 个字符。

