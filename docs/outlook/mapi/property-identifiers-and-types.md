---
title: 属性标识符和类型
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 39a5c97c-5ac8-47a8-b193-a4b3ba6a02a5
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7f31162e669af6efaf9e935c7c400d105c1321c2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778560"
---
# <a name="property-identifiers-and-types"></a>属性标识符和类型

  
  
**适用于**： Outlook 
  
由属性标记表示所有 MAPI 属性。 属性标记是一个 32 位无符号的整数值，包含该属性的标识符的高顺序 16 位和 low 中的该属性的类型排序 16 位。 Mapitags.h 标头文件中包含的所有属性定义的 MAPI 属性标记。
  
属性标识符用于指示属性用于以及由谁来负责它。 属性标识符可以分为若干通过 MAPI 范围;标识符属于范围中的其中指示其使用情况和所有权。 
  
属性类型用于指示该属性的数据的格式。 MAPI 定义的所有有效的类型。 客户端和创建新属性的服务提供商必须使用这些类型之一。 Mapidefs.h 头文件中包含的所有属性类型。
  

