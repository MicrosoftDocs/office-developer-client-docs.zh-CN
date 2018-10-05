---
title: PidLidFreeBusyLocation 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidFreeBusyLocation
api_type:
- COM
ms.assetid: 1e7a36e6-2e93-4aa5-bef8-66fd5c407700
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 50fa3c1e1173a91d7c03759f4f635f1bb6e0600d
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385653"
---
# <a name="pidlidfreebusylocation-canonical-property"></a><span data-ttu-id="2d286-103">PidLidFreeBusyLocation 规范属性</span><span class="sxs-lookup"><span data-stu-id="2d286-103">PidLidFreeBusyLocation Canonical Property</span></span>

  
  
<span data-ttu-id="2d286-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2d286-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2d286-105">指定客户端可以从中检索忙/闲信息的联系人中指定[[MS OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)为 iCal 文件的 URL 路径。</span><span class="sxs-lookup"><span data-stu-id="2d286-105">Specifies a URL path from which a client can retrieve free/busy information for the contact as an iCal file, as specified in [[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2d286-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2d286-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2d286-107">dispidFreeBusyLocation</span><span class="sxs-lookup"><span data-stu-id="2d286-107">dispidFreeBusyLocation</span></span>  <br/> |
|<span data-ttu-id="2d286-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="2d286-108">Property set:</span></span>  <br/> |<span data-ttu-id="2d286-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="2d286-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="2d286-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="2d286-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="2d286-111">0x000080D8</span><span class="sxs-lookup"><span data-stu-id="2d286-111">0x000080D8</span></span>  <br/> |
|<span data-ttu-id="2d286-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2d286-112">Data type:</span></span>  <br/> |<span data-ttu-id="2d286-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="2d286-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="2d286-114">区域：</span><span class="sxs-lookup"><span data-stu-id="2d286-114">Area:</span></span>  <br/> |<span data-ttu-id="2d286-115">联系人</span><span class="sxs-lookup"><span data-stu-id="2d286-115">Contact</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="2d286-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="2d286-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2d286-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="2d286-117">Protocol specifications</span></span>

<span data-ttu-id="2d286-118">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2d286-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2d286-119">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="2d286-119">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="2d286-120">[[MS OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2d286-120">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2d286-121">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="2d286-121">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2d286-122">头文件</span><span class="sxs-lookup"><span data-stu-id="2d286-122">Header files</span></span>

<span data-ttu-id="2d286-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2d286-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="2d286-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2d286-124">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2d286-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2d286-125">See also</span></span>



[<span data-ttu-id="2d286-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2d286-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2d286-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2d286-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2d286-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2d286-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2d286-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2d286-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

