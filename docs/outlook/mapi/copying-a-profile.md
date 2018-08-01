---
title: 复制配置文件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b722a157-0d92-404d-9075-39547241dbb7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 77c7853c07830804aaa044f08078d95785bcfda7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774696"
---
# <a name="copying-a-profile"></a><span data-ttu-id="433bc-103">复制配置文件</span><span class="sxs-lookup"><span data-stu-id="433bc-103">Copying a Profile</span></span>

  
  
<span data-ttu-id="433bc-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="433bc-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="433bc-105">创建一个配置文件的一种方法是从现有的配置文件复制和更改的必要消息服务和服务提供商。</span><span class="sxs-lookup"><span data-stu-id="433bc-105">One way to create a profile is to copy from an existing profile and alter the necessary message services and service providers.</span></span> <span data-ttu-id="433bc-106">复制一个配置文件包括使用通过[MAPIAdminProfiles](mapiadminprofiles.md)函数提供 MAPI 配置文件管理对象。</span><span class="sxs-lookup"><span data-stu-id="433bc-106">Copying a profile involves using a profile administration object, provided by MAPI through the [MAPIAdminProfiles](mapiadminprofiles.md) function.</span></span> 
  
 <span data-ttu-id="433bc-107">**若要将配置文件复制**</span><span class="sxs-lookup"><span data-stu-id="433bc-107">**To copy a profile**</span></span>
  
1. <span data-ttu-id="433bc-108">调用**MAPIAdminProfiles**检索**IProfAdmin**接口的指针。</span><span class="sxs-lookup"><span data-stu-id="433bc-108">Call **MAPIAdminProfiles** to retrieve an **IProfAdmin** interface pointer.</span></span> 
    
2. <span data-ttu-id="433bc-109">调用[IProfAdmin::GetProfileTable](iprofadmin-getprofiletable.md)访问 profile 表。</span><span class="sxs-lookup"><span data-stu-id="433bc-109">Call [IProfAdmin::GetProfileTable](iprofadmin-getprofiletable.md) to access the profile table.</span></span> 
    
3. <span data-ttu-id="433bc-110">生成与[SPropertyRestriction](spropertyrestriction.md)结构，以匹配**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 的属性限制要复制的配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="433bc-110">Build a property restriction with an [SPropertyRestriction](spropertyrestriction.md) structure to match **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) with the name of the profile to be copied.</span></span> 
    
4. <span data-ttu-id="433bc-111">调用[IMAPITable::FindRow](imapitable-findrow.md) profile 表中查找相应的行。</span><span class="sxs-lookup"><span data-stu-id="433bc-111">Call [IMAPITable::FindRow](imapitable-findrow.md) to locate the appropriate row in the profile table.</span></span> 
    
5. <span data-ttu-id="433bc-112">调用[IProfAdmin::CopyProfile](iprofadmin-copyprofile.md)，作为_lpszOldProfileName_参数传递**PR_DISPLAY_NAME**列的值。</span><span class="sxs-lookup"><span data-stu-id="433bc-112">Call [IProfAdmin::CopyProfile](iprofadmin-copyprofile.md), passing the value of the **PR_DISPLAY_NAME** column as the  _lpszOldProfileName_ parameter.</span></span> 
    

