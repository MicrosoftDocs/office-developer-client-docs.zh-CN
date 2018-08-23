---
title: 邮件存储区表
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cdb7d8c5-8e35-47ff-8be7-2cb17e341ad3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 735c778cd8e6ccb41de3d3d8cb0fdc163493f712
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572016"
---
# <a name="message-store-tables"></a><span data-ttu-id="6ac7f-103">邮件存储区表</span><span class="sxs-lookup"><span data-stu-id="6ac7f-103">Message Store Tables</span></span>

  
  
<span data-ttu-id="6ac7f-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6ac7f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6ac7f-105">消息存储表包含有关当前配置文件中的消息存储提供程序的信息。</span><span class="sxs-lookup"><span data-stu-id="6ac7f-105">The message store table contains information about message store providers in the current profile.</span></span> <span data-ttu-id="6ac7f-106">没有为每个 MAPI 会话，由 MAPI 实现和客户端使用的一个消息存储表。</span><span class="sxs-lookup"><span data-stu-id="6ac7f-106">There is one message store table for every MAPI session, implemented by MAPI and used by clients.</span></span> <span data-ttu-id="6ac7f-107">客户端可以使用此表中，例如，来查找特定提供程序的所有实例，或查找特定的邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="6ac7f-107">Clients can use this table, for example, to locate all instances of a particular provider or to locate a specific message store.</span></span> 
  
<span data-ttu-id="6ac7f-108">消息存储表是动态的。</span><span class="sxs-lookup"><span data-stu-id="6ac7f-108">The message store table is dynamic.</span></span> <span data-ttu-id="6ac7f-109">如果客户端应用程序的用户编辑配置文件更改默认的邮件存储，例如**PR_DEFAULT_STORE**值受影响的邮件存储的属性将立即更新。</span><span class="sxs-lookup"><span data-stu-id="6ac7f-109">If the user of a client application edits the profile, changing the default message store, for example, the values of the **PR_DEFAULT_STORE** properties for the affected message stores are immediately updated.</span></span> 
  
<span data-ttu-id="6ac7f-110">客户端通过调用[IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md)方法访问消息存储表。</span><span class="sxs-lookup"><span data-stu-id="6ac7f-110">Clients access the message store table by calling the [IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md) method.</span></span> 
  
<span data-ttu-id="6ac7f-111">以下属性构成设置消息存储表中所需的列：</span><span class="sxs-lookup"><span data-stu-id="6ac7f-111">The following properties make up the required column set in the message store table:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6ac7f-112">**PR_DEFAULT_STORE**([PidTagDefaultStore](pidtagdefaultstore-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="6ac7f-112">**PR_DEFAULT_STORE** ([PidTagDefaultStore](pidtagdefaultstore-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="6ac7f-113">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="6ac7f-113">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="6ac7f-114">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="6ac7f-114">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="6ac7f-115">**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="6ac7f-115">**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="6ac7f-116">**PR_MDB_PROVIDER**([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="6ac7f-116">**PR_MDB_PROVIDER** ([PidTagStoreProvider](pidtagstoreprovider-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="6ac7f-117">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="6ac7f-117">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="6ac7f-118">**PR_PROVIDER_DISPLAY**([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="6ac7f-118">**PR_PROVIDER_DISPLAY** ([PidTagProviderDisplay](pidtagproviderdisplay-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="6ac7f-119">**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="6ac7f-119">**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="6ac7f-120">**PR_RESOURCE_FLAGS**([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="6ac7f-120">**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="6ac7f-121">**PR_RESOURCE_TYPE**([PidTagResourceType](pidtagresourcetype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="6ac7f-121">**PR_RESOURCE_TYPE** ([PidTagResourceType](pidtagresourcetype-canonical-property.md))</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="6ac7f-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ac7f-122">See also</span></span>



[<span data-ttu-id="6ac7f-123">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="6ac7f-123">MAPI Tables</span></span>](mapi-tables.md)

