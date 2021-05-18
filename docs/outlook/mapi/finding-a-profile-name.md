---
title: 查找配置文件名称
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 18df25b7-16b7-44cd-a9a0-5276966c1fd4
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b4efdd8d8238d4bc7e89a1153b9be34c7af76355
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407919"
---
# <a name="finding-a-profile-name"></a><span data-ttu-id="eacbc-103">查找配置文件名称</span><span class="sxs-lookup"><span data-stu-id="eacbc-103">Finding a Profile Name</span></span>

  
  
<span data-ttu-id="eacbc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="eacbc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="eacbc-105">客户端有时需要查找当前用于会话的配置文件的名称、默认配置文件的名称或计算机上安装的备用配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="eacbc-105">Clients sometimes need to find the name of the profile currently being used for the session, the name of the default profile, or the name of an alternate profile installed on the computer.</span></span>
  
<span data-ttu-id="eacbc-106">在会话过程中，有几个方法可以检索配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="eacbc-106">There are a few ways to retrieve the name of a profile during the course of a session.</span></span> <span data-ttu-id="eacbc-107">如果需要查找不一定用于会话的配置文件的名称，请使用第一个过程。</span><span class="sxs-lookup"><span data-stu-id="eacbc-107">If you need to find the name of a profile that is not necessarily the one being used for the session, use the first procedure.</span></span> <span data-ttu-id="eacbc-108">如果需要查找默认配置文件的名称，请使用第二个过程。</span><span class="sxs-lookup"><span data-stu-id="eacbc-108">If you need to find the name of the default profile, use the second procedure.</span></span> <span data-ttu-id="eacbc-109">如果需要查找会话的当前配置文件的名称，请使用上一过程。</span><span class="sxs-lookup"><span data-stu-id="eacbc-109">If you need to find the name of the current profile for the session, use the last procedure.</span></span> 
  
 <span data-ttu-id="eacbc-110">**查找任何配置文件的名称**</span><span class="sxs-lookup"><span data-stu-id="eacbc-110">**To find the name of any profile**</span></span>
  
1. <span data-ttu-id="eacbc-111">调用 [MAPIAdminProfiles](mapiadminprofiles.md) 以检索 **IProfAdmin** 接口指针。</span><span class="sxs-lookup"><span data-stu-id="eacbc-111">Call [MAPIAdminProfiles](mapiadminprofiles.md) to retrieve an **IProfAdmin** interface pointer.</span></span> 
    
2. <span data-ttu-id="eacbc-112">调用 [IProfAdmin：：GetProfileTable](iprofadmin-getprofiletable.md) 以访问配置文件表。</span><span class="sxs-lookup"><span data-stu-id="eacbc-112">Call [IProfAdmin::GetProfileTable](iprofadmin-getprofiletable.md) to access the profile table.</span></span> 
    
3. <span data-ttu-id="eacbc-113">调用配置文件表的 [IMAPITable：：QueryRows](imapitable-queryrows.md) 方法来检索表中的所有行，并检查每个行以确定它是否表示目标配置文件。</span><span class="sxs-lookup"><span data-stu-id="eacbc-113">Call the profile table's [IMAPITable::QueryRows](imapitable-queryrows.md) method to retrieve all of the rows in the table and examine each one to determine if it represents your target profile.</span></span> 
    
 <span data-ttu-id="eacbc-114">**查找默认配置文件的名称**</span><span class="sxs-lookup"><span data-stu-id="eacbc-114">**To find the name of the default profile**</span></span>
  
1. <span data-ttu-id="eacbc-115">调用 [MAPIAdminProfiles](mapiadminprofiles.md)。</span><span class="sxs-lookup"><span data-stu-id="eacbc-115">Call [MAPIAdminProfiles](mapiadminprofiles.md).</span></span>
    
2. <span data-ttu-id="eacbc-116">调用 [IProfAdmin：：GetProfileTable](iprofadmin-getprofiletable.md) 以访问配置文件表。</span><span class="sxs-lookup"><span data-stu-id="eacbc-116">Call [IProfAdmin::GetProfileTable](iprofadmin-getprofiletable.md) to access the profile table.</span></span> 
    
3. <span data-ttu-id="eacbc-117">使用[SPropertyRestriction](spropertyrestriction.md)结构构建一个属性限制，PR_DEFAULT_PROFILE ([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md)) 值 TRUE。</span><span class="sxs-lookup"><span data-stu-id="eacbc-117">Build a property restriction with an [SPropertyRestriction](spropertyrestriction.md) structure to match **PR_DEFAULT_PROFILE** ([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md)) with the value TRUE.</span></span>
    
4. <span data-ttu-id="eacbc-118">调用 [IMAPITable：：FindRow](imapitable-findrow.md) 以查找配置文件表中表示默认配置文件的行。</span><span class="sxs-lookup"><span data-stu-id="eacbc-118">Call [IMAPITable::FindRow](imapitable-findrow.md) to locate the row in the profile table that represents the default profile.</span></span> <span data-ttu-id="eacbc-119">**"PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 列包含默认配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="eacbc-119">The **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) column contains the name of the default profile.</span></span>
    
 <span data-ttu-id="eacbc-120">**查找当前配置文件的名称**</span><span class="sxs-lookup"><span data-stu-id="eacbc-120">**To find the name of the current profile**</span></span>
  
<span data-ttu-id="eacbc-121">若要查找当前配置文件的名称，请完成以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="eacbc-121">To find the name of the current profile, complete one of the following steps:</span></span>
  
- <span data-ttu-id="eacbc-122">假设您具有表示当前配置文件的其中一个节的 [MAPIUID](mapiuid.md) 结构，请用  _lpUID_ 参数将结构传递给 [IMAPISession：：OpenProfileSection](imapisession-openprofilesection.md)。</span><span class="sxs-lookup"><span data-stu-id="eacbc-122">Assuming that you have the [MAPIUID](mapiuid.md) structure representing one of the current profile's sections, pass it in the  _lpUID_ parameter to [IMAPISession::OpenProfileSection](imapisession-openprofilesection.md).</span></span> <span data-ttu-id="eacbc-123">使用配置文件节的 [IMAPIProp：：PR_PROFILE_NAME](imapiprop-getprops.md) **(** 方法) [PidTagProfileName](pidtagprofilename-canonical-property.md)属性检索配置文件节的配置文件。</span><span class="sxs-lookup"><span data-stu-id="eacbc-123">Retrieve the profile section's **PR_PROFILE_NAME** ([PidTagProfileName](pidtagprofilename-canonical-property.md)) property using its [IMAPIProp::GetProps](imapiprop-getprops.md) method.</span></span> 
    
- <span data-ttu-id="eacbc-124">调用 [IMAPISession：：GetStatusTable](imapisession-getstatustable.md) 以访问状态表并查找其 **PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) 设置为 MAPI_SUBSYSTEM 的行。</span><span class="sxs-lookup"><span data-stu-id="eacbc-124">Call [IMAPISession::GetStatusTable](imapisession-getstatustable.md) to access the status table and find the row that has its **PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md)) column set to MAPI_SUBSYSTEM.</span></span> <span data-ttu-id="eacbc-125">该行 **PR_DISPLAY_NAME** 列是配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="eacbc-125">The **PR_DISPLAY_NAME** column for this row is the profile name.</span></span> <span data-ttu-id="eacbc-126">请勿在启动期间使用状态表，因为它会阻止应用程序，直到 MAPI 后台处理程序完成初始化所有传输提供程序。</span><span class="sxs-lookup"><span data-stu-id="eacbc-126">Do not use the status table during start up because it blocks an application until the MAPI spooler has finished initializing all of the transport providers.</span></span> <span data-ttu-id="eacbc-127">这会降低性能。</span><span class="sxs-lookup"><span data-stu-id="eacbc-127">This can degrade your performance.</span></span> 
    

