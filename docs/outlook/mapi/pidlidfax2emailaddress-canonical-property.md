---
title: PidLidFax2EmailAddress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidFax2EmailAddress
api_type:
- COM
ms.assetid: 119c00cf-b7df-4354-aef8-575429e5ab3c
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 16b1ebeb67b48c62bcccc804415d962831f13d7a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776795"
---
# <a name="pidlidfax2emailaddress-canonical-property"></a><span data-ttu-id="7386e-103">PidLidFax2EmailAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="7386e-103">PidLidFax2EmailAddress Canonical Property</span></span>

  
  
<span data-ttu-id="7386e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7386e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7386e-105">指定联系人的住宅传真地址的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="7386e-105">Specifies the email address of the contact's home fax address.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7386e-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="7386e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7386e-107">dispidFax2EmailAddress</span><span class="sxs-lookup"><span data-stu-id="7386e-107">dispidFax2EmailAddress</span></span>  <br/> |
|<span data-ttu-id="7386e-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="7386e-108">Property set:</span></span>  <br/> |<span data-ttu-id="7386e-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="7386e-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="7386e-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="7386e-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="7386e-111">0x000080C3</span><span class="sxs-lookup"><span data-stu-id="7386e-111">0x000080C3</span></span>  <br/> |
|<span data-ttu-id="7386e-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7386e-112">Data type:</span></span>  <br/> |<span data-ttu-id="7386e-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="7386e-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="7386e-114">区域：</span><span class="sxs-lookup"><span data-stu-id="7386e-114">Area:</span></span>  <br/> |<span data-ttu-id="7386e-115">联系人</span><span class="sxs-lookup"><span data-stu-id="7386e-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7386e-116">备注</span><span class="sxs-lookup"><span data-stu-id="7386e-116">Remarks</span></span>

<span data-ttu-id="7386e-117">此属性，如果存在此参数，应会包含一个用户可读的显示名称后, 跟"@"字符后, 跟传真号码。</span><span class="sxs-lookup"><span data-stu-id="7386e-117">This property, if present, should contain a user-readable display name, followed by the "@" character, followed by a fax number.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="7386e-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="7386e-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7386e-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="7386e-119">Protocol specifications</span></span>

<span data-ttu-id="7386e-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7386e-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7386e-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="7386e-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7386e-122">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7386e-122">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7386e-123">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="7386e-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7386e-124">头文件</span><span class="sxs-lookup"><span data-stu-id="7386e-124">Header files</span></span>

<span data-ttu-id="7386e-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7386e-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="7386e-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7386e-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7386e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7386e-127">See also</span></span>



[<span data-ttu-id="7386e-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7386e-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7386e-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7386e-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7386e-130">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7386e-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7386e-131">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7386e-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

