---
title: PidTagHomeAddressPostalCode 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagHomeAddressPostalCode
api_type:
- HeaderDef
ms.assetid: f89fd4ab-61b1-4405-89de-dfe599117a24
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3504011b99333d4b632c7edbf22136c5b5f0a511
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25391673"
---
# <a name="pidtaghomeaddresspostalcode-canonical-property"></a><span data-ttu-id="612f9-103">PidTagHomeAddressPostalCode 规范属性</span><span class="sxs-lookup"><span data-stu-id="612f9-103">PidTagHomeAddressPostalCode Canonical Property</span></span>

  
  
<span data-ttu-id="612f9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="612f9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="612f9-105">包含用户的主地址的邮政编码。</span><span class="sxs-lookup"><span data-stu-id="612f9-105">Contains the postal code for the user's home address.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="612f9-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="612f9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="612f9-107">PR_HOME_ADDRESS_POSTAL_CODE，PR_HOME_ADDRESS_POSTAL_CODE_A，PR_HOME_ADDRESS_POSTAL_CODE_W</span><span class="sxs-lookup"><span data-stu-id="612f9-107">PR_HOME_ADDRESS_POSTAL_CODE, PR_HOME_ADDRESS_POSTAL_CODE_A, PR_HOME_ADDRESS_POSTAL_CODE_W</span></span>  <br/> |
|<span data-ttu-id="612f9-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="612f9-108">Identifier:</span></span>  <br/> |<span data-ttu-id="612f9-109">0x3A5B</span><span class="sxs-lookup"><span data-stu-id="612f9-109">0x3A5B</span></span>  <br/> |
|<span data-ttu-id="612f9-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="612f9-110">Data type:</span></span>  <br/> |<span data-ttu-id="612f9-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="612f9-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="612f9-112">区域：</span><span class="sxs-lookup"><span data-stu-id="612f9-112">Area:</span></span>  <br/> |<span data-ttu-id="612f9-113">MAPI 邮件用户</span><span class="sxs-lookup"><span data-stu-id="612f9-113">MAPI mail user</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="612f9-114">说明</span><span class="sxs-lookup"><span data-stu-id="612f9-114">Remarks</span></span>

<span data-ttu-id="612f9-115">由用户或用户的组织定义这些属性。</span><span class="sxs-lookup"><span data-stu-id="612f9-115">These properties are defined by the user or the user's organization.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="612f9-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="612f9-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="612f9-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="612f9-117">Protocol specifications</span></span>

<span data-ttu-id="612f9-118">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="612f9-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="612f9-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="612f9-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="612f9-120">[[MS OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="612f9-120">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="612f9-121">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="612f9-121">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="612f9-122">头文件</span><span class="sxs-lookup"><span data-stu-id="612f9-122">Header files</span></span>

<span data-ttu-id="612f9-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="612f9-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="612f9-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="612f9-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="612f9-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="612f9-125">Mapitags.h</span></span>
  
> <span data-ttu-id="612f9-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="612f9-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="612f9-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="612f9-127">See also</span></span>



[<span data-ttu-id="612f9-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="612f9-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="612f9-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="612f9-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="612f9-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="612f9-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="612f9-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="612f9-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

