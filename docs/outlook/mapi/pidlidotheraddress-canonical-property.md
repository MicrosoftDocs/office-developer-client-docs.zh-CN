---
title: PidLidOtherAddress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidOtherAddress
api_type:
- COM
ms.assetid: 2b8acb69-4c84-4075-8457-d7aadce26c73
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0b05e83e48bf144ca317a64f90fb533f6d7d1c24
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359071"
---
# <a name="pidlidotheraddress-canonical-property"></a><span data-ttu-id="39dfc-103">PidLidOtherAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="39dfc-103">PidLidOtherAddress Canonical Property</span></span>

  
  
<span data-ttu-id="39dfc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="39dfc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="39dfc-105">指定联系人其他地址的完整地址。</span><span class="sxs-lookup"><span data-stu-id="39dfc-105">Specifies the complete address of the contact's other address.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="39dfc-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="39dfc-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="39dfc-107">dispidOtherAddress</span><span class="sxs-lookup"><span data-stu-id="39dfc-107">dispidOtherAddress</span></span>  <br/> |
|<span data-ttu-id="39dfc-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="39dfc-108">Property set:</span></span>  <br/> |<span data-ttu-id="39dfc-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="39dfc-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="39dfc-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="39dfc-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="39dfc-111">0x0000801C</span><span class="sxs-lookup"><span data-stu-id="39dfc-111">0x0000801C</span></span>  <br/> |
|<span data-ttu-id="39dfc-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="39dfc-112">Data type:</span></span>  <br/> |<span data-ttu-id="39dfc-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="39dfc-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="39dfc-114">区域：</span><span class="sxs-lookup"><span data-stu-id="39dfc-114">Area:</span></span>  <br/> |<span data-ttu-id="39dfc-115">Contact</span><span class="sxs-lookup"><span data-stu-id="39dfc-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="39dfc-116">注解</span><span class="sxs-lookup"><span data-stu-id="39dfc-116">Remarks</span></span>

<span data-ttu-id="39dfc-117">此属性应为其他物理地址属性的组合, 并且基于客户端区域设置。</span><span class="sxs-lookup"><span data-stu-id="39dfc-117">This property should be a combination of other physical address properties, and is based on client locale.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="39dfc-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="39dfc-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="39dfc-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="39dfc-119">Protocol specifications</span></span>

<span data-ttu-id="39dfc-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="39dfc-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="39dfc-121">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="39dfc-121">Provides property set definition and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="39dfc-122">[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="39dfc-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="39dfc-123">指定允许用于联系人和个人通讯组列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="39dfc-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="39dfc-124">头文件</span><span class="sxs-lookup"><span data-stu-id="39dfc-124">Header files</span></span>

<span data-ttu-id="39dfc-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="39dfc-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="39dfc-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="39dfc-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="39dfc-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39dfc-127">See also</span></span>



[<span data-ttu-id="39dfc-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="39dfc-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="39dfc-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="39dfc-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="39dfc-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="39dfc-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="39dfc-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="39dfc-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

