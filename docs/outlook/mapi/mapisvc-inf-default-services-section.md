---
title: MapiSvc.inf [默认服务] 部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: dec42f8d-0f5c-4665-b53a-11cbc58b8b76
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5d860135d846df8ef1ea0784d7430c71ad0fe64e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776395"
---
# <a name="mapisvcinf-default-services-section"></a><span data-ttu-id="3562e-103">MapiSvc.inf [默认服务] 部分</span><span class="sxs-lookup"><span data-stu-id="3562e-103">MapiSvc.inf [Default Services] Section</span></span>

  
  
<span data-ttu-id="3562e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3562e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3562e-105">**[默认服务]** 部分列出的所有消息服务作为默认邮件服务所选的。</span><span class="sxs-lookup"><span data-stu-id="3562e-105">The **[Default Services]** section lists all of the message services that are selected as default message services.</span></span> <span data-ttu-id="3562e-106">这些默认邮件服务是 **[服务]** 节中列出的消息服务的子集。</span><span class="sxs-lookup"><span data-stu-id="3562e-106">These default message services are a subset of the message services listed in the **[Services]** section.</span></span> <span data-ttu-id="3562e-107">当配置文件配置程序创建默认配置文件时，本节中的消息服务都自动包含。</span><span class="sxs-lookup"><span data-stu-id="3562e-107">When a profile configuration program creates a default profile, the message services in this section are automatically included.</span></span> 
  
<span data-ttu-id="3562e-108">条目以显示以下条目 **[服务]** 部分中，为使用相同的格式：</span><span class="sxs-lookup"><span data-stu-id="3562e-108">The entries use the same format as entries in the **[Services]** section, as shown following:</span></span> 
  
 <span data-ttu-id="3562e-109">**[默认服务]**</span><span class="sxs-lookup"><span data-stu-id="3562e-109">**[Default Services]**</span></span>
  
 <span data-ttu-id="3562e-110">_消息服务的部分名称_ =  _消息服务名称_</span><span class="sxs-lookup"><span data-stu-id="3562e-110">_message-service section name_ =  _message service name_</span></span>
  
<span data-ttu-id="3562e-111">将在早期图所示 mapisvc.inf **[默认服务]** 部分中包含下列项：</span><span class="sxs-lookup"><span data-stu-id="3562e-111">The following entries would be included in the **[Default Services]** section for the mapisvc.inf shown in the earlier illustration:</span></span> 
  
```cpp
[Default Services]
AB=Default Address Book
MsgService=My Own Service

```


