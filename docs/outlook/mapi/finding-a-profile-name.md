---
title: 查找配置文件名称
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 18df25b7-16b7-44cd-a9a0-5276966c1fd4
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 332b78bcebbcd54de43376553ec4aea386c1c359
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774928"
---
# <a name="finding-a-profile-name"></a><span data-ttu-id="bdd25-103">查找配置文件名称</span><span class="sxs-lookup"><span data-stu-id="bdd25-103">Finding a Profile Name</span></span>

  
  
<span data-ttu-id="bdd25-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="bdd25-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="bdd25-105">有时，客户端需要查找当前正在使用的会话、 默认配置文件的名称或其他计算机上安装的配置文件的名称的配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="bdd25-105">Clients sometimes need to find the name of the profile currently being used for the session, the name of the default profile, or the name of an alternate profile installed on the computer.</span></span>
  
<span data-ttu-id="bdd25-106">有几种方法在会话过程中的过程中检索一个配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="bdd25-106">There are a few ways to retrieve the name of a profile during the course of a session.</span></span> <span data-ttu-id="bdd25-107">如果您需要查找不一定是一个会话所用的配置文件的名称，请使用第一个过程。</span><span class="sxs-lookup"><span data-stu-id="bdd25-107">If you need to find the name of a profile that is not necessarily the one being used for the session, use the first procedure.</span></span> <span data-ttu-id="bdd25-108">如果您需要查找默认配置文件的名称，请使用第二个过程。</span><span class="sxs-lookup"><span data-stu-id="bdd25-108">If you need to find the name of the default profile, use the second procedure.</span></span> <span data-ttu-id="bdd25-109">如果您需要为会话中查找当前配置文件的名称，请使用上一过程。</span><span class="sxs-lookup"><span data-stu-id="bdd25-109">If you need to find the name of the current profile for the session, use the last procedure.</span></span> 
  
 <span data-ttu-id="bdd25-110">**若要查找的任何配置文件名称**</span><span class="sxs-lookup"><span data-stu-id="bdd25-110">**To find the name of any profile**</span></span>
  
1. <span data-ttu-id="bdd25-111">调用[MAPIAdminProfiles](mapiadminprofiles.md)检索**IProfAdmin**接口的指针。</span><span class="sxs-lookup"><span data-stu-id="bdd25-111">Call [MAPIAdminProfiles](mapiadminprofiles.md) to retrieve an **IProfAdmin** interface pointer.</span></span> 
    
2. <span data-ttu-id="bdd25-112">调用[IProfAdmin::GetProfileTable](iprofadmin-getprofiletable.md)访问 profile 表。</span><span class="sxs-lookup"><span data-stu-id="bdd25-112">Call [IProfAdmin::GetProfileTable](iprofadmin-getprofiletable.md) to access the profile table.</span></span> 
    
3. <span data-ttu-id="bdd25-113">调用 profile 表的[IMAPITable::QueryRows](imapitable-queryrows.md)方法来检索所有表中的行和检查每个以确定它是否代表您目标的配置文件。</span><span class="sxs-lookup"><span data-stu-id="bdd25-113">Call the profile table's [IMAPITable::QueryRows](imapitable-queryrows.md) method to retrieve all of the rows in the table and examine each one to determine if it represents your target profile.</span></span> 
    
 <span data-ttu-id="bdd25-114">**若要查找的默认配置文件的名称**</span><span class="sxs-lookup"><span data-stu-id="bdd25-114">**To find the name of the default profile**</span></span>
  
1. <span data-ttu-id="bdd25-115">调用[MAPIAdminProfiles](mapiadminprofiles.md)。</span><span class="sxs-lookup"><span data-stu-id="bdd25-115">Call [MAPIAdminProfiles](mapiadminprofiles.md).</span></span>
    
2. <span data-ttu-id="bdd25-116">调用[IProfAdmin::GetProfileTable](iprofadmin-getprofiletable.md)访问 profile 表。</span><span class="sxs-lookup"><span data-stu-id="bdd25-116">Call [IProfAdmin::GetProfileTable](iprofadmin-getprofiletable.md) to access the profile table.</span></span> 
    
3. <span data-ttu-id="bdd25-117">生成与[SPropertyRestriction](spropertyrestriction.md)结构，以匹配的值为 TRUE **PR_DEFAULT_PROFILE** ([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md)) 的属性限制。</span><span class="sxs-lookup"><span data-stu-id="bdd25-117">Build a property restriction with an [SPropertyRestriction](spropertyrestriction.md) structure to match **PR_DEFAULT_PROFILE** ([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md)) with the value TRUE.</span></span>
    
4. <span data-ttu-id="bdd25-118">调用[IMAPITable::FindRow](imapitable-findrow.md)以表示的默认配置文件的配置文件表中找到的行。</span><span class="sxs-lookup"><span data-stu-id="bdd25-118">Call [IMAPITable::FindRow](imapitable-findrow.md) to locate the row in the profile table that represents the default profile.</span></span> <span data-ttu-id="bdd25-119">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 列中包含的默认配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="bdd25-119">The **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) column contains the name of the default profile.</span></span>
    
 <span data-ttu-id="bdd25-120">**若要查找的当前配置文件名称**</span><span class="sxs-lookup"><span data-stu-id="bdd25-120">**To find the name of the current profile**</span></span>
  
<span data-ttu-id="bdd25-121">若要查找当前配置文件的名称，请完成以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="bdd25-121">To find the name of the current profile, complete one of the following steps:</span></span>
  
- <span data-ttu-id="bdd25-122">假定您有[MAPIUID](mapiuid.md)结构，它表示当前配置文件的部分之一，将其传递_lpUID_参数中给[IMAPISession::OpenProfileSection](imapisession-openprofilesection.md)。</span><span class="sxs-lookup"><span data-stu-id="bdd25-122">Assuming that you have the [MAPIUID](mapiuid.md) structure representing one of the current profile's sections, pass it in the  _lpUID_ parameter to [IMAPISession::OpenProfileSection](imapisession-openprofilesection.md).</span></span> <span data-ttu-id="bdd25-123">检索使用其[IMAPIProp::GetProps](imapiprop-getprops.md)方法的配置文件部分的**PR_PROFILE_NAME** ([PidTagProfileName](pidtagprofilename-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="bdd25-123">Retrieve the profile section's **PR_PROFILE_NAME** ([PidTagProfileName](pidtagprofilename-canonical-property.md)) property using its [IMAPIProp::GetProps](imapiprop-getprops.md) method.</span></span> 
    
- <span data-ttu-id="bdd25-124">调用[IMAPISession::GetStatusTable](imapisession-getstatustable.md)访问状态表和查找已设置为 MAPI_SUBSYSTEM 其**PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 列的行。</span><span class="sxs-lookup"><span data-stu-id="bdd25-124">Call [IMAPISession::GetStatusTable](imapisession-getstatustable.md) to access the status table and find the row that has its **PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) column set to MAPI_SUBSYSTEM.</span></span> <span data-ttu-id="bdd25-125">此行**PR_DISPLAY_NAME**列是配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="bdd25-125">The **PR_DISPLAY_NAME** column for this row is the profile name.</span></span> <span data-ttu-id="bdd25-126">不要使用状态表期间开始因为它会阻止应用程序直到 MAPI 后台处理程序完成初始化所有传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="bdd25-126">Do not use the status table during start up because it blocks an application until the MAPI spooler has finished initializing all of the transport providers.</span></span> <span data-ttu-id="bdd25-127">这样做会降低性能。</span><span class="sxs-lookup"><span data-stu-id="bdd25-127">This can degrade your performance.</span></span> 
    

