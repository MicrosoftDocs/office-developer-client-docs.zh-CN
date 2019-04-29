---
title: 属性标识符和类型
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 39a5c97c-5ac8-47a8-b193-a4b3ba6a02a5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: caba60b7059d1c1f8f0440aeb55abb88801fbc9a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437215"
---
# <a name="property-identifiers-and-types"></a>属性标识符和类型

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
所有 MAPI 属性均由属性标记表示。 属性标记是一个32位无符号整数值, 其中包含高序位16位中的属性标识符和低位16位的属性类型。 MAPI 定义的所有属性的属性标记都包含在 mapitags 头文件中。
  
属性标识符用于指示属性的用途和负责的所有者。 将属性标识符除以 MAPI 到区域中;其中, 标识符位于范围内表示其使用和所有权。 
  
属性类型用于指示属性的数据的格式。 MAPI 定义所有有效的类型。 客户端和服务提供程序创建新属性必须使用以下类型之一。 所有属性类型都包含在 mapidefs.h 头文件中。
  

