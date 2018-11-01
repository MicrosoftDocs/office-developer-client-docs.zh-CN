---
title: Property.Name Property (DAO)
TOCTitle: Name Property
ms:assetid: 0dae15e0-5d2e-3bb4-8a44-98db4a8ce516
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845211(v=office.15)
ms:contentKeyID: 48543225
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 09a5e37bf9874888ca37935db38c98773cb03806
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25867298"
---
# <a name="propertyname-property-dao"></a>Property.Name Property (DAO)


**适用于**： Access 2013、 Office 2013

返回或设置指定对象的名称。对于尚未追加到集合中的对象，该属性为可读/写 **String** 类型；对于已追加到集合中的对象，该属性为只读 **String** 类型。

## <a name="syntax"></a>语法

*表达式*。名称

*表达式*一个代表**Property**对象的变量。

## <a name="remarks"></a>注解

内置属性的 **Name** 属性始终为只读。

**Property** 对象名称的最大长度为 64 个字符。

