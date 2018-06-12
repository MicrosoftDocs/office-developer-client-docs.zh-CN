---
title: 配置文件表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cd8d60df-98fb-4e08-b547-0836bb31be79
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 84c2d02da840dfcad077462954cb10894ba153d9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778555"
---
# <a name="profile-tables"></a><span data-ttu-id="77411-103">配置文件表</span><span class="sxs-lookup"><span data-stu-id="77411-103">Profile Tables</span></span>

  
  
<span data-ttu-id="77411-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="77411-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="77411-105">配置文件表列出了有关与特定客户端应用程序关联的所有配置文件信息。</span><span class="sxs-lookup"><span data-stu-id="77411-105">The profile table lists information about all profiles associated with a particular client application.</span></span> <span data-ttu-id="77411-106">一个配置文件表是为每个会话，由 MAPI 客户端使用的实现。</span><span class="sxs-lookup"><span data-stu-id="77411-106">There is one profile table for every session, implemented by MAPI for use by clients.</span></span> 
  
<span data-ttu-id="77411-107">客户端通过调用[IProfAdmin::GetProfileTable](iprofadmin-getprofiletable.md)方法访问配置文件表。</span><span class="sxs-lookup"><span data-stu-id="77411-107">Clients access the profile table by calling the [IProfAdmin::GetProfileTable](iprofadmin-getprofiletable.md) method.</span></span> 
  
<span data-ttu-id="77411-108">配置文件表是一个静态表。</span><span class="sxs-lookup"><span data-stu-id="77411-108">The profile table is a static table.</span></span> <span data-ttu-id="77411-109">配置文件表中不包含已标记为删除的配置文件。</span><span class="sxs-lookup"><span data-stu-id="77411-109">Profiles that have been marked for deletion are not included in the profile table.</span></span>
  
<span data-ttu-id="77411-110">为与大多数表实现，如果调用**GetProfileTable** ，并且没有配置文件供客户端，表创建零行。</span><span class="sxs-lookup"><span data-stu-id="77411-110">As with most table implementations, if **GetProfileTable** is called and there are no profiles available to the client, the table is created with zero rows.</span></span> 
  
<span data-ttu-id="77411-111">以下属性构成 profile 表中所需的列：</span><span class="sxs-lookup"><span data-stu-id="77411-111">The following properties make up the required column set in profile tables:</span></span>
  
 <span data-ttu-id="77411-112">**PR_DEFAULT_PROFILE**([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="77411-112">**PR_DEFAULT_PROFILE** ([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md))</span></span> 
  
 <span data-ttu-id="77411-113">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="77411-113">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="77411-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77411-114">See also</span></span>



[<span data-ttu-id="77411-115">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="77411-115">MAPI Tables</span></span>](mapi-tables.md)

