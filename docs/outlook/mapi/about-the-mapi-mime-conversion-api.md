---
title: 有关 MAPI MIME 转换 API
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: ffdfdff8-985d-35de-73b1-c34e1932cb9f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 43ce3ecea6b80bace2bcc2bd333b5c1839514f7d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774477"
---
# <a name="about-the-mapi-mime-conversion-api"></a>有关 MAPI MIME 转换 API

  
  
**适用于**： Outlook 
  
MAPI MIME 转换 API 允许邮件提供商 MIME 对象和 MAPI 邮件之间进行转换。 它提供了常量定义、 类标识符和界面标识符[MAPI 常量](mapi-constants.md)中所示。 邮件提供商必须共同**[IConverterSession](iconvertersessioniunknown.md)** 实例创建通过调用**CoCreateInstance**函数。 
  

