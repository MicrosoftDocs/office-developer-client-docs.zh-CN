---
title: PidTagHomeAddressCountry 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagHomeAddressCountry
api_type:
- HeaderDef
ms.assetid: cf3a86f4-016e-49d2-a71d-7f3f68e69867
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3d9001250e4d39ea010af0fc04df297ceb497b1d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572555"
---
# <a name="pidtaghomeaddresscountry-canonical-property"></a><span data-ttu-id="58710-103">PidTagHomeAddressCountry 规范属性</span><span class="sxs-lookup"><span data-stu-id="58710-103">PidTagHomeAddressCountry Canonical Property</span></span>

  
  
<span data-ttu-id="58710-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="58710-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="58710-105">包含在联系人的地址县。</span><span class="sxs-lookup"><span data-stu-id="58710-105">Contains the county in a contact's address.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="58710-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="58710-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="58710-107">PR_HOME_ADDRESS_COUNTRY，PR_HOME_ADDRESS_COUNTRY_A，PR_HOME_ADDRESS_COUNTRY_W</span><span class="sxs-lookup"><span data-stu-id="58710-107">PR_HOME_ADDRESS_COUNTRY, PR_HOME_ADDRESS_COUNTRY_A, PR_HOME_ADDRESS_COUNTRY_W</span></span>  <br/> |
|<span data-ttu-id="58710-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="58710-108">Identifier:</span></span>  <br/> |<span data-ttu-id="58710-109">0x3A5A</span><span class="sxs-lookup"><span data-stu-id="58710-109">0x3A5A</span></span>  <br/> |
|<span data-ttu-id="58710-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="58710-110">Data type:</span></span>  <br/> |<span data-ttu-id="58710-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="58710-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="58710-112">区域：</span><span class="sxs-lookup"><span data-stu-id="58710-112">Area:</span></span>  <br/> |<span data-ttu-id="58710-113">MAPI 邮件用户</span><span class="sxs-lookup"><span data-stu-id="58710-113">MAPI mail user</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="58710-114">注解</span><span class="sxs-lookup"><span data-stu-id="58710-114">Remarks</span></span>

<span data-ttu-id="58710-115">由用户或用户的组织定义这些属性。</span><span class="sxs-lookup"><span data-stu-id="58710-115">These properties are defined by the user or the user's organization.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="58710-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="58710-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="58710-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="58710-117">Protocol specifications</span></span>

<span data-ttu-id="58710-118">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="58710-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="58710-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="58710-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="58710-120">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="58710-120">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="58710-121">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="58710-121">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="58710-122">头文件</span><span class="sxs-lookup"><span data-stu-id="58710-122">Header files</span></span>

<span data-ttu-id="58710-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="58710-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="58710-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="58710-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="58710-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="58710-125">Mapitags.h</span></span>
  
> <span data-ttu-id="58710-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="58710-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="58710-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58710-127">See also</span></span>



[<span data-ttu-id="58710-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="58710-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="58710-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="58710-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="58710-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="58710-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="58710-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="58710-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

