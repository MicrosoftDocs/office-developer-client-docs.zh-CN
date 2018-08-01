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
ms.openlocfilehash: 81772115fcd4f081718dd560759f6ab93dc7c11c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776521"
---
# <a name="message-service-tables"></a><span data-ttu-id="5c062-103">邮件服务表</span><span class="sxs-lookup"><span data-stu-id="5c062-103">Message Service Tables</span></span>

  
  
<span data-ttu-id="5c062-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5c062-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="5c062-105">邮件服务表包含有关当前配置文件中的消息服务的信息。</span><span class="sxs-lookup"><span data-stu-id="5c062-105">The message service table contains information about the message services in the current profile.</span></span> <span data-ttu-id="5c062-106">对于每个 MAPI 会话，由 MAPI 实现并供提供配置支持的特殊用途客户端应用程序没有邮件服务的一个表。</span><span class="sxs-lookup"><span data-stu-id="5c062-106">There is one message service table for every MAPI session, implemented by MAPI and used by special purpose client applications that provide configuration support.</span></span> 
  
<span data-ttu-id="5c062-107">邮件服务表是一个静态表。</span><span class="sxs-lookup"><span data-stu-id="5c062-107">The message service table is a static table.</span></span>
  
<span data-ttu-id="5c062-108">客户端调用[IMsgServiceAdmin::GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md)方法来访问邮件服务表。</span><span class="sxs-lookup"><span data-stu-id="5c062-108">Clients access the message service table by calling the [IMsgServiceAdmin::GetMsgServiceTable](imsgserviceadmin-getmsgservicetable.md) method.</span></span> 
  
<span data-ttu-id="5c062-109">以下属性构成设置消息服务表中所需的列：</span><span class="sxs-lookup"><span data-stu-id="5c062-109">The following properties make up the required column set in the message service table:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5c062-110">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="5c062-110">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="5c062-111">**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="5c062-111">**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="5c062-112">**PR_RESOURCE_FLAGS**([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="5c062-112">**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="5c062-113">**PR_SERVICE_DLL_NAME**([PidTagServiceDllName](pidtagservicedllname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="5c062-113">**PR_SERVICE_DLL_NAME** ([PidTagServiceDllName](pidtagservicedllname-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="5c062-114">**PR_SERVICE_ENTRY_NAME**([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="5c062-114">**PR_SERVICE_ENTRY_NAME** ([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="5c062-115">**PR_SERVICE_NAME**([PidTagServiceName](pidtagservicename-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="5c062-115">**PR_SERVICE_NAME** ([PidTagServiceName](pidtagservicename-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="5c062-116">**PR_SERVICE_SUPPORT_FILES**([PidTagServiceSupportFiles](pidtagservicesupportfiles-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="5c062-116">**PR_SERVICE_SUPPORT_FILES** ([PidTagServiceSupportFiles](pidtagservicesupportfiles-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="5c062-117">**PR_SERVICE_UID**([PidTagServiceUid](pidtagserviceuid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="5c062-117">**PR_SERVICE_UID** ([PidTagServiceUid](pidtagserviceuid-canonical-property.md))</span></span>  <br/> |
   
 <span data-ttu-id="5c062-118">**PR_DISPLAY_NAME**是可显示名称的消息服务和默认排序键列。</span><span class="sxs-lookup"><span data-stu-id="5c062-118">**PR_DISPLAY_NAME** is the displayable name for the message service and the default sort key column.</span></span> 
  
 <span data-ttu-id="5c062-119">**PR_INSTANCE_KEY**充当索引列的表中，用于唯一地标识行。</span><span class="sxs-lookup"><span data-stu-id="5c062-119">**PR_INSTANCE_KEY** serves as the index column for the table, uniquely identifying a row.</span></span> 
  
 <span data-ttu-id="5c062-120">**PR_RESOURCE_FLAGS**描述消息服务的功能。</span><span class="sxs-lookup"><span data-stu-id="5c062-120">**PR_RESOURCE_FLAGS** describes the message service's capabilities.</span></span> 
  
 <span data-ttu-id="5c062-121">**PR_SERVICE_DLL_NAME**是包含消息服务实现的 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="5c062-121">**PR_SERVICE_DLL_NAME** is the name of the DLL that contains the message service implementation.</span></span> 
  
 <span data-ttu-id="5c062-122">**PR_SERVICE_ENTRY_NAME**是符合[MSGSERVICEENTRY](msgserviceentry.md)原型的消息服务的入口点函数的名称。</span><span class="sxs-lookup"><span data-stu-id="5c062-122">**PR_SERVICE_ENTRY_NAME** is the name of the message service's entry point function that conforms to the [MSGSERVICEENTRY](msgserviceentry.md) prototype.</span></span> 
  
 <span data-ttu-id="5c062-123">**PR_SERVICE_NAME**是必的填项 **[服务]** 节中 MAPISVC.INF。</span><span class="sxs-lookup"><span data-stu-id="5c062-123">**PR_SERVICE_NAME** is a required entry in the **[Services]** section in MAPISVC.INF.</span></span> <span data-ttu-id="5c062-124">将永远不会更改此属性的值，或为其本地化。</span><span class="sxs-lookup"><span data-stu-id="5c062-124">The value for this property will never be changed or localized.</span></span> <span data-ttu-id="5c062-125">**PR_SERVICE_NAME**可用于以编程方式标识邮件服务。</span><span class="sxs-lookup"><span data-stu-id="5c062-125">**PR_SERVICE_NAME** can be used to programmatically identify the message service.</span></span> 
  
 <span data-ttu-id="5c062-126">**PR_SERVICE_SUPPORT_FILES**是必须与消息服务安装文件的列表。</span><span class="sxs-lookup"><span data-stu-id="5c062-126">**PR_SERVICE_SUPPORT_FILES** is a list of files that must be installed with the message service.</span></span> 
  
 <span data-ttu-id="5c062-127">**PR_SERVICE_UID**是邮件服务的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="5c062-127">**PR_SERVICE_UID** is a unique identifier for the message service.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5c062-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c062-128">See also</span></span>



[<span data-ttu-id="5c062-129">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="5c062-129">MAPI Tables</span></span>](mapi-tables.md)

