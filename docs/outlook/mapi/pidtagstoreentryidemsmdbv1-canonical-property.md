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
# <a name="pidtagstoreentryidemsmdbv1-canonical-property"></a><span data-ttu-id="2ebc1-103">PidTagStoreEntryIdEmsmdbV1 规范属性</span><span class="sxs-lookup"><span data-stu-id="2ebc1-103">PidTagStoreEntryIdEmsmdbV1 Canonical Property</span></span>

  
  
<span data-ttu-id="2ebc1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2ebc1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2ebc1-105">包含 microsoft Exchange server 2010 或 Exchange server 2013 邮件存储的条目标识符的旧样式 (Microsoft Outlook 2002 及更早版本)。</span><span class="sxs-lookup"><span data-stu-id="2ebc1-105">Contains the old style (Microsoft Outlook 2002 and earlier versions) of the entry identifier of a Microsoft Exchange Server 2010 or Exchange Server 2013 message store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2ebc1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2ebc1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2ebc1-107">PR_STORE_ENTRYID_EMSMDB_V1</span><span class="sxs-lookup"><span data-stu-id="2ebc1-107">PR_STORE_ENTRYID_EMSMDB_V1</span></span>  <br/> |
|<span data-ttu-id="2ebc1-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="2ebc1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="2ebc1-109">0x65F60102</span><span class="sxs-lookup"><span data-stu-id="2ebc1-109">0x65F60102</span></span>  <br/> |
|<span data-ttu-id="2ebc1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2ebc1-110">Data type:</span></span>  <br/> |<span data-ttu-id="2ebc1-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="2ebc1-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="2ebc1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="2ebc1-112">Area:</span></span>  <br/> |<span data-ttu-id="2ebc1-113">ID 属性</span><span class="sxs-lookup"><span data-stu-id="2ebc1-113">ID properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2ebc1-114">说明</span><span class="sxs-lookup"><span data-stu-id="2ebc1-114">Remarks</span></span>

<span data-ttu-id="2ebc1-115">从 Microsoft Outlook 2003 开始, 服务器 fqdn 已集成到条目 id 中, 从而避免了其他用于引用的 rpc。</span><span class="sxs-lookup"><span data-stu-id="2ebc1-115">Starting with Microsoft Outlook 2003, the server FQDNs were integrated into the entry IDs, thereby avoiding additional RPCs for referrals.</span></span> <span data-ttu-id="2ebc1-116">但是, 这会使条目 id 变长并引入更多方案, 在这些方案中, 必须使用**CompareEntryIDs**方法来确定两个条目 id 是否等效。</span><span class="sxs-lookup"><span data-stu-id="2ebc1-116">However, this makes entry IDs longer and introduces more scenarios where the **CompareEntryIDs** method must be used to determine whether two entry IDs are equivalent.</span></span> <span data-ttu-id="2ebc1-117">PR_STORE_ENTRYID_EMSMDB_V1 (PidTagStoreIdEmsbdbV1) 属性访问 microsoft Outlook 2002 (microsoft Office XP) 和早期版本使用的 Exchange Server 条目 ID 的旧格式。</span><span class="sxs-lookup"><span data-stu-id="2ebc1-117">The PR_STORE_ENTRYID_EMSMDB_V1 (PidTagStoreIdEmsbdbV1) property accesses the older format of the Exchange Server entry ID used by Microsoft Outlook 2002 (Microsoft Office XP) and earlier versions.</span></span> <span data-ttu-id="2ebc1-118">这样可以节省空间, 还可以减少确定条目 id 何时等效时所需的**CompareEntryIDs**调用数。</span><span class="sxs-lookup"><span data-stu-id="2ebc1-118">This can save space and also reduce the number of **CompareEntryIDs** calls needed to determine when entry IDs are equivalent.</span></span> <span data-ttu-id="2ebc1-119">请注意, 如果需要引用, 使用较旧的条目 id 打开邮箱可能会产生一些额外的 rpc。</span><span class="sxs-lookup"><span data-stu-id="2ebc1-119">Note that using the older entry IDs to open a mailbox may incur some additional RPCs if a referral is required.</span></span> 
  
<span data-ttu-id="2ebc1-120">若要在缓存模式下访问 PR_STORE_ENTRYID_EMSMDB_V1 属性, 必须使用 MAPI_NO_CACHE 标志和[IMAPIProp:: GetProps](imapiprop-getprops.md)方法绕过缓存。</span><span class="sxs-lookup"><span data-stu-id="2ebc1-120">To access the PR_STORE_ENTRYID_EMSMDB_V1 property while in cached mode, you must bypass the cache using the MAPI_NO_CACHE flag with the [IMAPIProp::GetProps](imapiprop-getprops.md) method.</span></span> <span data-ttu-id="2ebc1-121">如果**PR_STORE_ENTRYID_EMSMDB_V1**不可用, 则代码应回退到 PR_STORE_ENTRYID。</span><span class="sxs-lookup"><span data-stu-id="2ebc1-121">If **PR_STORE_ENTRYID_EMSMDB_V1** isn't available, the code should fall back to PR_STORE_ENTRYID.</span></span> <span data-ttu-id="2ebc1-122">只有 Outlook 2003 至 Microsoft Outlook 2013 支持 PR_STORE_ENTRYID_EMSMDB_V1 属性。</span><span class="sxs-lookup"><span data-stu-id="2ebc1-122">Only Outlook 2003 through Microsoft Outlook 2013 support the PR_STORE_ENTRYID_EMSMDB_V1 property.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2ebc1-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ebc1-123">See also</span></span>



[<span data-ttu-id="2ebc1-124">PidTagStoreEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="2ebc1-124">PidTagStoreEntryId Canonical Property</span></span>](pidtagstoreentryid-canonical-property.md)


[<span data-ttu-id="2ebc1-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2ebc1-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2ebc1-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2ebc1-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2ebc1-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2ebc1-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2ebc1-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2ebc1-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

