---
title: Property.Name 属性 (DAO)
TOCTitle: Name Property
ms:assetid: 0dae15e0-5d2e-3bb4-8a44-98db4a8ce516
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845211(v=office.15)
ms:contentKeyID: 48543225
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 47053a815d6728087c8a0c4f5e584ee5da5abcac
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25930579"
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

