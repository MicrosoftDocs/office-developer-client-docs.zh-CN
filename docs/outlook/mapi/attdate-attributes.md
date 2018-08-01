---
title: attDate Attributes
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 22801641-752c-4c81-be90-02039eaa4277
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: f3319c9ae49fa97a6179b0ee800bd5dd594aefab
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774579"
---
# <a name="attdate-attributes"></a>attDate Attributes

  
  
**适用于**： Outlook 
  
所有与日期和时间的 MAPI 属性映射到具有**attDate**前缀的 TNEF 属性。 这些是所有编码为**DTR**结构。 日期和时间附件属性被编码为以及**DTR**结构。 
  
所有与日期和时间的 MAPI 属性映射到具有**attDate**前缀的 TNEF 属性。 这些是所有编码为**DTR**结构。 日期和时间附件属性被编码为以及**DTR**结构。 
  
**DTR**结构是非常类似于在 Win32 头文件中定义的**SYSTEMTIME**结构。 **DTR**结构 TNEF 用于将 stream 中编码为**sizeof(DTR)** 字节开头结构中的第一个成员。 **DTR**结构 TNEF 中定义。H 头文件。 
  

