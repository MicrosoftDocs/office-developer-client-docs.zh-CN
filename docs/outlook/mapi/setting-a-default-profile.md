---
title: 设置默认配置文件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1d1e862d-ba49-48a1-bb51-0af861323b7b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f6bf8f88fa3e87ae619fa32d759fc182290998ad
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439812"
---
# <a name="setting-a-default-profile"></a><span data-ttu-id="0608b-103">设置默认配置文件</span><span class="sxs-lookup"><span data-stu-id="0608b-103">Setting a Default Profile</span></span>

  
  
<span data-ttu-id="0608b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0608b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0608b-105">如果未在对[MAPILogonEx](mapilogonex.md)的调用中显式指定一个配置文件, 则将使用默认配置文件, 而改为设置 MAPI_USE_DEFAULT 标志。</span><span class="sxs-lookup"><span data-stu-id="0608b-105">The default profile is the profile that is used if you do not explicitly specify one in the call to [MAPILogonEx](mapilogonex.md), setting instead the MAPI_USE_DEFAULT flag.</span></span>
  
 <span data-ttu-id="0608b-106">**建立默认配置文件**</span><span class="sxs-lookup"><span data-stu-id="0608b-106">**To establish a default profile**</span></span>
  
1. <span data-ttu-id="0608b-107">调用[MAPIAdminProfiles](mapiadminprofiles.md)函数以检索**IProfAdmin**接口指针。</span><span class="sxs-lookup"><span data-stu-id="0608b-107">Call the [MAPIAdminProfiles](mapiadminprofiles.md) function to retrieve an **IProfAdmin** interface pointer.</span></span> 
    
2. <span data-ttu-id="0608b-108">调用[IProfAdmin:: SetDefaultProfile](iprofadmin-setdefaultprofile.md)。</span><span class="sxs-lookup"><span data-stu-id="0608b-108">Call [IProfAdmin::SetDefaultProfile](iprofadmin-setdefaultprofile.md).</span></span> <span data-ttu-id="0608b-109">**SetDefaultProfile**设置新的默认配置文件的**PR_DEFAULT_PROFILE** ([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md)) 属性, 并删除以前的默认配置文件的设置。</span><span class="sxs-lookup"><span data-stu-id="0608b-109">**SetDefaultProfile** sets the **PR_DEFAULT_PROFILE** ([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md)) property for the new default profile and removes the setting for the previous default profile.</span></span>
    

