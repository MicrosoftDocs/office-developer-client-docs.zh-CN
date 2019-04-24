---
title: 配置文件表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cd8d60df-98fb-4e08-b547-0836bb31be79
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 15c07c05af82389bce697c300cd9b1d504e98736
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328558"
---
# <a name="profile-tables"></a><span data-ttu-id="25685-103">配置文件表</span><span class="sxs-lookup"><span data-stu-id="25685-103">Profile Tables</span></span>

  
  
<span data-ttu-id="25685-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="25685-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="25685-105">配置文件表列出了与特定客户端应用程序相关联的所有配置文件的相关信息。</span><span class="sxs-lookup"><span data-stu-id="25685-105">The profile table lists information about all profiles associated with a particular client application.</span></span> <span data-ttu-id="25685-106">每个会话都有一个配置文件表, 由 MAPI 实现, 以供客户端使用。</span><span class="sxs-lookup"><span data-stu-id="25685-106">There is one profile table for every session, implemented by MAPI for use by clients.</span></span> 
  
<span data-ttu-id="25685-107">客户端通过调用[IProfAdmin:: GetProfileTable](iprofadmin-getprofiletable.md)方法访问配置文件表。</span><span class="sxs-lookup"><span data-stu-id="25685-107">Clients access the profile table by calling the [IProfAdmin::GetProfileTable](iprofadmin-getprofiletable.md) method.</span></span> 
  
<span data-ttu-id="25685-108">配置文件表是静态表。</span><span class="sxs-lookup"><span data-stu-id="25685-108">The profile table is a static table.</span></span> <span data-ttu-id="25685-109">已标记为删除的配置文件不包含在配置文件表中。</span><span class="sxs-lookup"><span data-stu-id="25685-109">Profiles that have been marked for deletion are not included in the profile table.</span></span>
  
<span data-ttu-id="25685-110">与大多数表实现一样, 如果调用了**GetProfileTable**并且没有可用于客户端的配置文件, 则会创建表, 其中包含零行。</span><span class="sxs-lookup"><span data-stu-id="25685-110">As with most table implementations, if **GetProfileTable** is called and there are no profiles available to the client, the table is created with zero rows.</span></span> 
  
<span data-ttu-id="25685-111">以下属性构成了 profile 表中的必需列集:</span><span class="sxs-lookup"><span data-stu-id="25685-111">The following properties make up the required column set in profile tables:</span></span>
  
 <span data-ttu-id="25685-112">**PR_DEFAULT_PROFILE**([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="25685-112">**PR_DEFAULT_PROFILE** ([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md))</span></span> 
  
 <span data-ttu-id="25685-113">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="25685-113">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="25685-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25685-114">See also</span></span>



[<span data-ttu-id="25685-115">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="25685-115">MAPI Tables</span></span>](mapi-tables.md)

