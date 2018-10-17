---
title: PidLidSharingRemoteStoreUid 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSharingRemoteStoreUid
api_type:
- COM
ms.assetid: f6773bba-45ef-4aef-90da-acad8ff64615
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bf1376e1efe23aa59aa9a70c1f0accdeac92d250
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25392913"
---
# <a name="pidlidsharingremotestoreuid-canonical-property"></a><span data-ttu-id="97667-103">PidLidSharingRemoteStoreUid 规范属性</span><span class="sxs-lookup"><span data-stu-id="97667-103">PidLidSharingRemoteStoreUid Canonical Property</span></span>

  
  
<span data-ttu-id="97667-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="97667-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="97667-105">指定的共享文件夹的十六进制字符串表示形式**PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="97667-105">Specifies the hexadecimal string representation of the value of the **PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) property on the shared folder.</span></span> <span data-ttu-id="97667-106">这是邮件的共享的属性。</span><span class="sxs-lookup"><span data-stu-id="97667-106">This is a property of a sharing message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="97667-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="97667-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="97667-108">dispidSharingRemoteStoreUid</span><span class="sxs-lookup"><span data-stu-id="97667-108">dispidSharingRemoteStoreUid</span></span>  <br/> |
|<span data-ttu-id="97667-109">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="97667-109">Property set:</span></span>  <br/> |<span data-ttu-id="97667-110">PSETID_Sharing</span><span class="sxs-lookup"><span data-stu-id="97667-110">PSETID_Sharing</span></span>  <br/> |
|<span data-ttu-id="97667-111">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="97667-111">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="97667-112">0x00008A48</span><span class="sxs-lookup"><span data-stu-id="97667-112">0x00008A48</span></span>  <br/> |
|<span data-ttu-id="97667-113">数据类型：</span><span class="sxs-lookup"><span data-stu-id="97667-113">Data type:</span></span>  <br/> |<span data-ttu-id="97667-114">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="97667-114">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="97667-115">区域：</span><span class="sxs-lookup"><span data-stu-id="97667-115">Area:</span></span>  <br/> |<span data-ttu-id="97667-116">共享</span><span class="sxs-lookup"><span data-stu-id="97667-116">Sharing</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="97667-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="97667-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="97667-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="97667-118">Protocol specifications</span></span>

<span data-ttu-id="97667-119">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="97667-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="97667-120">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="97667-120">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="97667-121">[[MS OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="97667-121">[[MS-OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="97667-122">共享客户端之间的邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="97667-122">Shares mailbox folders between clients.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="97667-123">头文件</span><span class="sxs-lookup"><span data-stu-id="97667-123">Header files</span></span>

<span data-ttu-id="97667-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="97667-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="97667-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="97667-125">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="97667-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97667-126">See also</span></span>



[<span data-ttu-id="97667-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="97667-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="97667-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="97667-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="97667-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="97667-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="97667-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="97667-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
