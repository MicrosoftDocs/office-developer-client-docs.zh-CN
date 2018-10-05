---
title: PidLidEmail1EmailAddress 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidEmail1EmailAddress
api_type:
- COM
ms.assetid: 790800a0-34a2-4223-8b75-b50c57881022
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1ebdd25d02b7539a151b03c4c8e1304164f72313
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25397798"
---
# <a name="pidlidemail1emailaddress-canonical-property"></a><span data-ttu-id="f834c-103">PidLidEmail1EmailAddress 规范属性</span><span class="sxs-lookup"><span data-stu-id="f834c-103">PidLidEmail1EmailAddress Canonical Property</span></span>

  
  
<span data-ttu-id="f834c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f834c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f834c-105">指定联系人的第一个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="f834c-105">Specifies the first email address of the contact.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f834c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f834c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f834c-107">dispidEmail1EmailAddress</span><span class="sxs-lookup"><span data-stu-id="f834c-107">dispidEmail1EmailAddress</span></span>  <br/> |
|<span data-ttu-id="f834c-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="f834c-108">Property set:</span></span>  <br/> |<span data-ttu-id="f834c-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="f834c-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="f834c-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="f834c-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="f834c-111">0x00008083</span><span class="sxs-lookup"><span data-stu-id="f834c-111">0x00008083</span></span>  <br/> |
|<span data-ttu-id="f834c-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f834c-112">Data type:</span></span>  <br/> |<span data-ttu-id="f834c-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="f834c-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="f834c-114">区域：</span><span class="sxs-lookup"><span data-stu-id="f834c-114">Area:</span></span>  <br/> |<span data-ttu-id="f834c-115">联系人</span><span class="sxs-lookup"><span data-stu-id="f834c-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f834c-116">说明</span><span class="sxs-lookup"><span data-stu-id="f834c-116">Remarks</span></span>

<span data-ttu-id="f834c-117">此属性的值必须是适用于此电子邮件地址为指定的地址类型。</span><span class="sxs-lookup"><span data-stu-id="f834c-117">The value of this property must be appropriate for the address type specified for this email address.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="f834c-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="f834c-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f834c-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="f834c-119">Protocol specifications</span></span>

<span data-ttu-id="f834c-120">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f834c-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f834c-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="f834c-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="f834c-122">[[MS OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f834c-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f834c-123">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="f834c-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f834c-124">头文件</span><span class="sxs-lookup"><span data-stu-id="f834c-124">Header files</span></span>

<span data-ttu-id="f834c-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f834c-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="f834c-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f834c-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f834c-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f834c-127">See also</span></span>



[<span data-ttu-id="f834c-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f834c-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f834c-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f834c-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f834c-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f834c-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f834c-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f834c-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

