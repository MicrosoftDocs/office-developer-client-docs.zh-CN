---
title: PidTagStoreEntryIdEmsmdbV1 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 40161358-4d41-43cf-83c7-fdd843bec87b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c8bccbfeb7f04745a66831618deff490bc651b02
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415150"
---
# <a name="pidtagstoreentryidemsmdbv1-canonical-property"></a><span data-ttu-id="3a58d-103">PidTagStoreEntryIdEmsmdbV1 规范属性</span><span class="sxs-lookup"><span data-stu-id="3a58d-103">PidTagStoreEntryIdEmsmdbV1 Canonical Property</span></span>

  
  
<span data-ttu-id="3a58d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3a58d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3a58d-105">包含 microsoft (2002 Outlook 2002 和早期版本) 的 Microsoft Exchange Server 2010 或 Exchange Server 2013 邮件存储的条目标识符的旧样式。</span><span class="sxs-lookup"><span data-stu-id="3a58d-105">Contains the old style (Microsoft Outlook 2002 and earlier versions) of the entry identifier of a Microsoft Exchange Server 2010 or Exchange Server 2013 message store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3a58d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3a58d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3a58d-107">PR_STORE_ENTRYID_EMSMDB_V1</span><span class="sxs-lookup"><span data-stu-id="3a58d-107">PR_STORE_ENTRYID_EMSMDB_V1</span></span>  <br/> |
|<span data-ttu-id="3a58d-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="3a58d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="3a58d-109">0x65F60102</span><span class="sxs-lookup"><span data-stu-id="3a58d-109">0x65F60102</span></span>  <br/> |
|<span data-ttu-id="3a58d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3a58d-110">Data type:</span></span>  <br/> |<span data-ttu-id="3a58d-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="3a58d-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="3a58d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="3a58d-112">Area:</span></span>  <br/> |<span data-ttu-id="3a58d-113">ID 属性</span><span class="sxs-lookup"><span data-stu-id="3a58d-113">ID properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3a58d-114">备注</span><span class="sxs-lookup"><span data-stu-id="3a58d-114">Remarks</span></span>

<span data-ttu-id="3a58d-115">从 Microsoft Outlook 2003 开始，服务器 FQN 已集成到条目 ID 中，从而避免了用于引用的其他 RPC。</span><span class="sxs-lookup"><span data-stu-id="3a58d-115">Starting with Microsoft Outlook 2003, the server FQDNs were integrated into the entry IDs, thereby avoiding additional RPCs for referrals.</span></span> <span data-ttu-id="3a58d-116">但是，这会使条目 ID 更长，并引入更多方案， **其中必须使用 CompareEntryIDs** 方法来确定两个条目 ID 是否等效。</span><span class="sxs-lookup"><span data-stu-id="3a58d-116">However, this makes entry IDs longer and introduces more scenarios where the **CompareEntryIDs** method must be used to determine whether two entry IDs are equivalent.</span></span> <span data-ttu-id="3a58d-117">PR_STORE_ENTRYID_EMSMDB_V1 (PidTagStoreIdEmsbdbV1) 属性访问 Microsoft Outlook 2002 (Microsoft Office XP) 及早期版本使用的 Exchange Server 条目 ID 的较旧格式。</span><span class="sxs-lookup"><span data-stu-id="3a58d-117">The PR_STORE_ENTRYID_EMSMDB_V1 (PidTagStoreIdEmsbdbV1) property accesses the older format of the Exchange Server entry ID used by Microsoft Outlook 2002 (Microsoft Office XP) and earlier versions.</span></span> <span data-ttu-id="3a58d-118">这可以节省空间，还可以减少确定条目 ID 何时等效所需的 **CompareEntryIDs** 调用次数。</span><span class="sxs-lookup"><span data-stu-id="3a58d-118">This can save space and also reduce the number of **CompareEntryIDs** calls needed to determine when entry IDs are equivalent.</span></span> <span data-ttu-id="3a58d-119">请注意，如果需要引用，使用较旧的条目 ID 打开邮箱可能会产生一些额外的 RPC。</span><span class="sxs-lookup"><span data-stu-id="3a58d-119">Note that using the older entry IDs to open a mailbox may incur some additional RPCs if a referral is required.</span></span> 
  
<span data-ttu-id="3a58d-120">若要在PR_STORE_ENTRYID_EMSMDB_V1访问 PR_STORE_ENTRYID_EMSMDB_V1 属性，必须使用带 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法的 MAPI_NO_CACHE 标志绕过缓存。</span><span class="sxs-lookup"><span data-stu-id="3a58d-120">To access the PR_STORE_ENTRYID_EMSMDB_V1 property while in cached mode, you must bypass the cache using the MAPI_NO_CACHE flag with the [IMAPIProp::GetProps](imapiprop-getprops.md) method.</span></span> <span data-ttu-id="3a58d-121">如果 **PR_STORE_ENTRYID_EMSMDB_V1** 不可用，则代码应回退到PR_STORE_ENTRYID。</span><span class="sxs-lookup"><span data-stu-id="3a58d-121">If **PR_STORE_ENTRYID_EMSMDB_V1** isn't available, the code should fall back to PR_STORE_ENTRYID.</span></span> <span data-ttu-id="3a58d-122">只有 Outlook 2003 Microsoft Outlook 2013支持 PR_STORE_ENTRYID_EMSMDB_V1 属性。</span><span class="sxs-lookup"><span data-stu-id="3a58d-122">Only Outlook 2003 through Microsoft Outlook 2013 support the PR_STORE_ENTRYID_EMSMDB_V1 property.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3a58d-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a58d-123">See also</span></span>



[<span data-ttu-id="3a58d-124">PidTagStoreEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="3a58d-124">PidTagStoreEntryId Canonical Property</span></span>](pidtagstoreentryid-canonical-property.md)


[<span data-ttu-id="3a58d-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3a58d-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3a58d-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3a58d-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3a58d-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3a58d-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3a58d-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3a58d-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

