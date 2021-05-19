---
title: PidLidEmail1OriginalDisplayName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidEmail1OriginalDisplayName
api_type:
- COM
ms.assetid: 991c2969-0180-4c7d-95ee-e62fd24d67ef
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a20ae8e3f19073bfb88d58db516a0e5f93d91445
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335040"
---
# <a name="pidlidemail1originaldisplayname-canonical-property"></a><span data-ttu-id="e6e49-103">PidLidEmail1OriginalDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="e6e49-103">PidLidEmail1OriginalDisplayName Canonical Property</span></span>

  
  
<span data-ttu-id="e6e49-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e6e49-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e6e49-105">指定第一显示名称对应于为联系人指定的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="e6e49-105">Specifies the first display name that corresponds to the email address that is specified for the contact.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e6e49-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e6e49-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e6e49-107">dispidEmail1OriginalDisplayName</span><span class="sxs-lookup"><span data-stu-id="e6e49-107">dispidEmail1OriginalDisplayName</span></span>  <br/> |
|<span data-ttu-id="e6e49-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="e6e49-108">Property set:</span></span>  <br/> |<span data-ttu-id="e6e49-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="e6e49-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="e6e49-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="e6e49-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="e6e49-111">0x00008084</span><span class="sxs-lookup"><span data-stu-id="e6e49-111">0x00008084</span></span>  <br/> |
|<span data-ttu-id="e6e49-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e6e49-112">Data type:</span></span>  <br/> |<span data-ttu-id="e6e49-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="e6e49-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="e6e49-114">区域：</span><span class="sxs-lookup"><span data-stu-id="e6e49-114">Area:</span></span>  <br/> |<span data-ttu-id="e6e49-115">联系人</span><span class="sxs-lookup"><span data-stu-id="e6e49-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e6e49-116">备注</span><span class="sxs-lookup"><span data-stu-id="e6e49-116">Remarks</span></span>

<span data-ttu-id="e6e49-117">如果 **dispidEmail1AddrType** ([PidLidEmail1AddressType](pidlidemail1addresstype-canonical-property.md)) 属性的值为"SMTP"，则各个 **dispidEmail1OriginalDisplayName** 属性的值应等于各自的 **dispidEmail1EmailAddress** ([PidLidEmail1EmailAddress](pidlidemail1emailaddress-canonical-property.md)) 属性的值。</span><span class="sxs-lookup"><span data-stu-id="e6e49-117">If the value of the **dispidEmail1AddrType** ([PidLidEmail1AddressType](pidlidemail1addresstype-canonical-property.md)) property is "SMTP", the value of the respective **dispidEmail1OriginalDisplayName** property should equal the value of the respective **dispidEmail1EmailAddress** ([PidLidEmail1EmailAddress](pidlidemail1emailaddress-canonical-property.md)) property.</span></span> <span data-ttu-id="e6e49-118">此属性显示与 **dispidEmail1EmailAddress** 属性中的用户友好地址等效的备用用户友好地址。</span><span class="sxs-lookup"><span data-stu-id="e6e49-118">This property displays an alternative user-friendly address that is equivalent to the one in the **dispidEmail1EmailAddress** property.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="e6e49-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="e6e49-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e6e49-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="e6e49-120">Protocol specifications</span></span>

<span data-ttu-id="e6e49-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e6e49-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e6e49-122">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="e6e49-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e6e49-123">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e6e49-123">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e6e49-124">指定联系人和个人通讯组列表允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="e6e49-124">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e6e49-125">头文件</span><span class="sxs-lookup"><span data-stu-id="e6e49-125">Header files</span></span>

<span data-ttu-id="e6e49-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e6e49-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="e6e49-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e6e49-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e6e49-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6e49-128">See also</span></span>



[<span data-ttu-id="e6e49-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e6e49-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e6e49-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e6e49-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e6e49-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e6e49-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e6e49-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e6e49-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

