---
title: 邮件服务表
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b93ab837-3918-4427-b013-bedc6f5276e4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c644e89511033234aa45c5f82738e4c471ef646d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356908"
---
# <a name="message-service-tables"></a><span data-ttu-id="0e92e-103">邮件服务表</span><span class="sxs-lookup"><span data-stu-id="0e92e-103">Message Service Tables</span></span>

  
  
<span data-ttu-id="0e92e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0e92e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0e92e-105">邮件服务表包含有关当前配置文件中的邮件服务的信息。</span><span class="sxs-lookup"><span data-stu-id="0e92e-105">The message service table contains information about the message services in the current profile.</span></span> <span data-ttu-id="0e92e-106">每个 mapi 会话都有一个邮件服务表, 这些会话由 mapi 实现, 并由提供配置支持的特殊用途的客户端应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="0e92e-106">There is one message service table for every MAPI session, implemented by MAPI and used by special purpose client applications that provide configuration support.</span></span> 
  
<span data-ttu-id="0e92e-107">邮件服务表是静态表。</span><span class="sxs-lookup"><span data-stu-id="0e92e-107">The message service table is a static table.</span></span>
  
<span data-ttu-id="0e92e-108">客户端通过调用[IMsgServiceAdmin:: GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md)方法访问邮件服务表。</span><span class="sxs-lookup"><span data-stu-id="0e92e-108">Clients access the message service table by calling the [IMsgServiceAdmin::GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md) method.</span></span> 
  
<span data-ttu-id="0e92e-109">以下属性构成了在邮件服务表中设置的必需列:</span><span class="sxs-lookup"><span data-stu-id="0e92e-109">The following properties make up the required column set in the message service table:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0e92e-110">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="0e92e-110">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="0e92e-111">**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="0e92e-111">**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="0e92e-112">**PR_RESOURCE_FLAGS**([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="0e92e-112">**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="0e92e-113">**PR_SERVICE_DLL_NAME**([PidTagServiceDllName](pidtagservicedllname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="0e92e-113">**PR_SERVICE_DLL_NAME** ([PidTagServiceDllName](pidtagservicedllname-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="0e92e-114">**PR_SERVICE_ENTRY_NAME**([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="0e92e-114">**PR_SERVICE_ENTRY_NAME** ([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="0e92e-115">**PR_SERVICE_NAME**([PidTagServiceName](pidtagservicename-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="0e92e-115">**PR_SERVICE_NAME** ([PidTagServiceName](pidtagservicename-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="0e92e-116">**PR_SERVICE_SUPPORT_FILES**([PidTagServiceSupportFiles](pidtagservicesupportfiles-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="0e92e-116">**PR_SERVICE_SUPPORT_FILES** ([PidTagServiceSupportFiles](pidtagservicesupportfiles-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="0e92e-117">**PR_SERVICE_UID**([PidTagServiceUid](pidtagserviceuid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="0e92e-117">**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md))</span></span>  <br/> |
   
 <span data-ttu-id="0e92e-118">**PR_DISPLAY_NAME**是邮件服务和默认的排序关键字列的可显示名称。</span><span class="sxs-lookup"><span data-stu-id="0e92e-118">**PR_DISPLAY_NAME** is the displayable name for the message service and the default sort key column.</span></span> 
  
 <span data-ttu-id="0e92e-119">**PR_INSTANCE_KEY**充当表的索引列, 唯一标识行。</span><span class="sxs-lookup"><span data-stu-id="0e92e-119">**PR_INSTANCE_KEY** serves as the index column for the table, uniquely identifying a row.</span></span> 
  
 <span data-ttu-id="0e92e-120">**PR_RESOURCE_FLAGS**描述了邮件服务的功能。</span><span class="sxs-lookup"><span data-stu-id="0e92e-120">**PR_RESOURCE_FLAGS** describes the message service's capabilities.</span></span> 
  
 <span data-ttu-id="0e92e-121">**PR_SERVICE_DLL_NAME**是包含邮件服务实现的 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="0e92e-121">**PR_SERVICE_DLL_NAME** is the name of the DLL that contains the message service implementation.</span></span> 
  
 <span data-ttu-id="0e92e-122">**PR_SERVICE_ENTRY_NAME**是符合[MSGSERVICEENTRY](msgserviceentry.md)原型的邮件服务的入口点函数的名称。</span><span class="sxs-lookup"><span data-stu-id="0e92e-122">**PR_SERVICE_ENTRY_NAME** is the name of the message service's entry point function that conforms to the [MSGSERVICEENTRY](msgserviceentry.md) prototype.</span></span> 
  
 <span data-ttu-id="0e92e-123">**PR_SERVICE_NAME**是 mapisvc.inf 中的 **[服务]** 部分中的必需条目。</span><span class="sxs-lookup"><span data-stu-id="0e92e-123">**PR_SERVICE_NAME** is a required entry in the **[Services]** section in MAPISVC.INF.</span></span> <span data-ttu-id="0e92e-124">此属性的值永远不会更改或本地化。</span><span class="sxs-lookup"><span data-stu-id="0e92e-124">The value for this property will never be changed or localized.</span></span> <span data-ttu-id="0e92e-125">**PR_SERVICE_NAME**可用于以编程方式标识邮件服务。</span><span class="sxs-lookup"><span data-stu-id="0e92e-125">**PR_SERVICE_NAME** can be used to programmatically identify the message service.</span></span> 
  
 <span data-ttu-id="0e92e-126">**PR_SERVICE_SUPPORT_FILES**是必须随邮件服务一起安装的文件的列表。</span><span class="sxs-lookup"><span data-stu-id="0e92e-126">**PR_SERVICE_SUPPORT_FILES** is a list of files that must be installed with the message service.</span></span> 
  
 <span data-ttu-id="0e92e-127">**PR_SERVICE_UID**是邮件服务的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="0e92e-127">**PR_SERVICE_UID** is a unique identifier for the message service.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0e92e-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e92e-128">See also</span></span>



[<span data-ttu-id="0e92e-129">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="0e92e-129">MAPI Tables</span></span>](mapi-tables.md)

