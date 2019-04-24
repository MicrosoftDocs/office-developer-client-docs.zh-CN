---
title: PidLidEmail3AddressType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidEmail3AddressType
api_type:
- COM
ms.assetid: c2bf94d9-0524-4a9d-8e30-1adbecd8f3dd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1f8c151d2d43423ba10773320c51912ef7fbda09
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338092"
---
# <a name="pidlidemail3addresstype-canonical-property"></a><span data-ttu-id="7916d-103">PidLidEmail3AddressType 规范属性</span><span class="sxs-lookup"><span data-stu-id="7916d-103">PidLidEmail3AddressType Canonical Property</span></span>

  
  
<span data-ttu-id="7916d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7916d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7916d-105">指定第三个电子邮件地址的地址类型。</span><span class="sxs-lookup"><span data-stu-id="7916d-105">Specifies the address type of the third email address.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7916d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7916d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7916d-107">dispidEmail3AddrType</span><span class="sxs-lookup"><span data-stu-id="7916d-107">dispidEmail3AddrType</span></span>  <br/> |
|<span data-ttu-id="7916d-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="7916d-108">Property set:</span></span>  <br/> |<span data-ttu-id="7916d-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="7916d-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="7916d-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="7916d-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="7916d-111">0x000080A2</span><span class="sxs-lookup"><span data-stu-id="7916d-111">0x000080A2</span></span>  <br/> |
|<span data-ttu-id="7916d-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7916d-112">Data type:</span></span>  <br/> |<span data-ttu-id="7916d-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="7916d-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="7916d-114">区域：</span><span class="sxs-lookup"><span data-stu-id="7916d-114">Area:</span></span>  <br/> |<span data-ttu-id="7916d-115">Contact</span><span class="sxs-lookup"><span data-stu-id="7916d-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7916d-116">注解</span><span class="sxs-lookup"><span data-stu-id="7916d-116">Remarks</span></span>

<span data-ttu-id="7916d-117">如果存在此属性值, 则必须为有效的地址类型。</span><span class="sxs-lookup"><span data-stu-id="7916d-117">If present, this property value must be a valid address type.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="7916d-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="7916d-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7916d-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="7916d-119">Protocol specifications</span></span>

<span data-ttu-id="7916d-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7916d-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7916d-121">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="7916d-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7916d-122">[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7916d-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7916d-123">指定允许用于联系人和个人通讯组列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="7916d-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7916d-124">头文件</span><span class="sxs-lookup"><span data-stu-id="7916d-124">Header files</span></span>

<span data-ttu-id="7916d-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="7916d-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="7916d-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7916d-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7916d-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7916d-127">See also</span></span>



[<span data-ttu-id="7916d-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7916d-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7916d-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7916d-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7916d-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7916d-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7916d-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7916d-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

