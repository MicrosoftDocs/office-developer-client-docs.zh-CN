---
title: attDate 属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 22801641-752c-4c81-be90-02039eaa4277
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b7c1ce8d0338a2bda63a276628bdd6e8be3b8eb1
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408276"
---
# <a name="attdate-attributes"></a>attDate 属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
与日期和时间相关的所有 MAPI 属性都映射到具有 **attDate** 前缀的 TNEF 属性。 所有这些都编码为 **DTR** 结构。 附件属性的日期和时间也编码为 **DTR** 结构。 
  
与日期和时间相关的所有 MAPI 属性都映射到具有 **attDate** 前缀的 TNEF 属性。 所有这些都编码为 **DTR** 结构。 附件属性的日期和时间也编码为 **DTR** 结构。 
  
**DTR** 结构与 Win32 头文件中定义的 **SYSTEMTIME** 结构非常相似。 **DTR** 结构在 TNEF 流中编码为 sizeof (**DTR**) 从结构的第一个成员开始。 **DTR** 结构在 TNEF 中定义。H 头文件。 
  

