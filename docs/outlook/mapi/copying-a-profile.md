---
title: 复制配置文件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b722a157-0d92-404d-9075-39547241dbb7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 86f381eff1dab0144afe0f94dcd6dd54d1ad7fa8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285228"
---
# <a name="copying-a-profile"></a><span data-ttu-id="3de90-103">复制配置文件</span><span class="sxs-lookup"><span data-stu-id="3de90-103">Copying a Profile</span></span>

  
  
<span data-ttu-id="3de90-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3de90-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3de90-105">创建配置文件的一种方法是复制现有的配置文件, 并改变必要的邮件服务和服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="3de90-105">One way to create a profile is to copy from an existing profile and alter the necessary message services and service providers.</span></span> <span data-ttu-id="3de90-106">复制配置文件涉及使用由 MAPI 通过[MAPIAdminProfiles](mapiadminprofiles.md)函数提供的配置文件管理对象。</span><span class="sxs-lookup"><span data-stu-id="3de90-106">Copying a profile involves using a profile administration object, provided by MAPI through the [MAPIAdminProfiles](mapiadminprofiles.md) function.</span></span> 
  
 <span data-ttu-id="3de90-107">**复制配置文件**</span><span class="sxs-lookup"><span data-stu-id="3de90-107">**To copy a profile**</span></span>
  
1. <span data-ttu-id="3de90-108">调用**MAPIAdminProfiles**以检索**IProfAdmin**接口指针。</span><span class="sxs-lookup"><span data-stu-id="3de90-108">Call **MAPIAdminProfiles** to retrieve an **IProfAdmin** interface pointer.</span></span> 
    
2. <span data-ttu-id="3de90-109">调用[IProfAdmin:: GetProfileTable](iprofadmin-getprofiletable.md)以访问配置文件表。</span><span class="sxs-lookup"><span data-stu-id="3de90-109">Call [IProfAdmin::GetProfileTable](iprofadmin-getprofiletable.md) to access the profile table.</span></span> 
    
3. <span data-ttu-id="3de90-110">使用[SPropertyRestriction](spropertyrestriction.md)结构生成属性限制, 以匹配**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 和要复制的配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="3de90-110">Build a property restriction with an [SPropertyRestriction](spropertyrestriction.md) structure to match **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) with the name of the profile to be copied.</span></span> 
    
4. <span data-ttu-id="3de90-111">调用[IMAPITable:: FindRow](imapitable-findrow.md)以在配置文件表中查找相应的行。</span><span class="sxs-lookup"><span data-stu-id="3de90-111">Call [IMAPITable::FindRow](imapitable-findrow.md) to locate the appropriate row in the profile table.</span></span> 
    
5. <span data-ttu-id="3de90-112">调用[IProfAdmin:: CopyProfile](iprofadmin-copyprofile.md), 将**PR_DISPLAY_NAME**列的值作为_lpszOldProfileName_参数进行传递。</span><span class="sxs-lookup"><span data-stu-id="3de90-112">Call [IProfAdmin::CopyProfile](iprofadmin-copyprofile.md), passing the value of the **PR_DISPLAY_NAME** column as the  _lpszOldProfileName_ parameter.</span></span> 
    

