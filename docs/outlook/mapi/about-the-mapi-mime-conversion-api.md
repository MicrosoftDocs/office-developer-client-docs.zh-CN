---
title: 关于 MAPI-MIME 转换 API
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: ffdfdff8-985d-35de-73b1-c34e1932cb9f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 23e68d18a6de93a99d2db32c1d93dac33d9a1225
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575264"
---
# <a name="about-the-mapi-mime-conversion-api"></a><span data-ttu-id="fbbc8-103">关于 MAPI-MIME 转换 API</span><span class="sxs-lookup"><span data-stu-id="fbbc8-103">About the MAPI-MIME Conversion API</span></span>

  
  
<span data-ttu-id="fbbc8-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fbbc8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fbbc8-105">MAPI MIME 转换 API 允许邮件提供商 MIME 对象和 MAPI 邮件之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="fbbc8-105">The MAPI-MIME Conversion API allows mail providers to convert between MIME objects and MAPI messages.</span></span> <span data-ttu-id="fbbc8-106">它提供了常量定义、 类标识符和界面标识符[MAPI 常量](mapi-constants.md)中所示。</span><span class="sxs-lookup"><span data-stu-id="fbbc8-106">It provides constant definitions, class identifiers, and interface identifiers as shown in [MAPI Constants](mapi-constants.md).</span></span> <span data-ttu-id="fbbc8-107">邮件提供商必须共同**[IConverterSession](iconvertersessioniunknown.md)** 实例创建通过调用**CoCreateInstance**函数。</span><span class="sxs-lookup"><span data-stu-id="fbbc8-107">Mail providers must cocreate an instance of **[IConverterSession](iconvertersessioniunknown.md)** by calling the **CoCreateInstance** function.</span></span> 
  

