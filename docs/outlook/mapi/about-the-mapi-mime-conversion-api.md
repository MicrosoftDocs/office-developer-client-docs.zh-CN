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
# <a name="about-the-mapi-mime-conversion-api"></a><span data-ttu-id="7b897-103">有关 MAPI MIME 转换 API</span><span class="sxs-lookup"><span data-stu-id="7b897-103">About the MAPI-MIME Conversion API</span></span>

  
  
<span data-ttu-id="7b897-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7b897-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7b897-105">MAPI MIME 转换 API 允许邮件提供商 MIME 对象和 MAPI 邮件之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="7b897-105">The MAPI-MIME Conversion API allows mail providers to convert between MIME objects and MAPI messages.</span></span> <span data-ttu-id="7b897-106">它提供了常量定义、 类标识符和界面标识符[MAPI 常量](mapi-constants.md)中所示。</span><span class="sxs-lookup"><span data-stu-id="7b897-106">It provides constant definitions, class identifiers, and interface identifiers as shown in [MAPI Constants](mapi-constants.md).</span></span> <span data-ttu-id="7b897-107">邮件提供商必须共同**[IConverterSession](iconvertersessioniunknown.md)** 实例创建通过调用**CoCreateInstance**函数。</span><span class="sxs-lookup"><span data-stu-id="7b897-107">Mail providers must cocreate an instance of **[IConverterSession](iconvertersessioniunknown.md)** by calling the **CoCreateInstance** function.</span></span> 
  

