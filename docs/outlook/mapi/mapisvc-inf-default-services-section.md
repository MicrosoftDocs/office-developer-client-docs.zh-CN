---
title: mapisvc.inf [默认服务] 部分
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: dec42f8d-0f5c-4665-b53a-11cbc58b8b76
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a7906a9a5e953332dba5c4776c63bb433a937a5d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270068"
---
# <a name="mapisvcinf-default-services-section"></a><span data-ttu-id="73619-103">mapisvc.inf [默认服务] 部分</span><span class="sxs-lookup"><span data-stu-id="73619-103">MapiSvc.inf [Default Services] Section</span></span>

  
  
<span data-ttu-id="73619-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="73619-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="73619-105">**[默认服务]** 部分列出了选定为默认邮件服务的所有邮件服务。</span><span class="sxs-lookup"><span data-stu-id="73619-105">The **[Default Services]** section lists all of the message services that are selected as default message services.</span></span> <span data-ttu-id="73619-106">这些默认邮件服务是 **[服务]** 一节中列出的邮件服务的子集。</span><span class="sxs-lookup"><span data-stu-id="73619-106">These default message services are a subset of the message services listed in the **[Services]** section.</span></span> <span data-ttu-id="73619-107">当配置文件配置程序创建默认配置文件时, 将自动包含此部分中的邮件服务。</span><span class="sxs-lookup"><span data-stu-id="73619-107">When a profile configuration program creates a default profile, the message services in this section are automatically included.</span></span> 
  
<span data-ttu-id="73619-108">这些条目使用与 **[服务]** 部分中的条目相同的格式, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="73619-108">The entries use the same format as entries in the **[Services]** section, as shown following:</span></span> 
  
 <span data-ttu-id="73619-109">**[默认服务]**</span><span class="sxs-lookup"><span data-stu-id="73619-109">**[Default Services]**</span></span>
  
 <span data-ttu-id="73619-110">_message service 部分名称_ =  _邮件服务名称_</span><span class="sxs-lookup"><span data-stu-id="73619-110">_message-service section name_ =  _message service name_</span></span>
  
<span data-ttu-id="73619-111">在前面的图所示的 mapisvc.inf 的 **[默认服务]** 部分中, 将包含以下项:</span><span class="sxs-lookup"><span data-stu-id="73619-111">The following entries would be included in the **[Default Services]** section for the mapisvc.inf shown in the earlier illustration:</span></span> 
  
```cpp
[Default Services]
AB=Default Address Book
MsgService=My Own Service

```


