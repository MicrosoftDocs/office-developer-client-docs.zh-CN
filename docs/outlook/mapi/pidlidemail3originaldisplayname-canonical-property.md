---
title: PidLidEmail3OriginalDisplayName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidEmail3OriginalDisplayName
api_type:
- COM
ms.assetid: f3fa392a-c3b1-46dd-bf9b-5ce310719542
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e69bcde35bcfec7746893ee18423aca3a24a6c4a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338071"
---
# <a name="pidlidemail3originaldisplayname-canonical-property"></a><span data-ttu-id="786b6-103">PidLidEmail3OriginalDisplayName 规范属性</span><span class="sxs-lookup"><span data-stu-id="786b6-103">PidLidEmail3OriginalDisplayName Canonical Property</span></span>

  
  
<span data-ttu-id="786b6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="786b6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="786b6-105">指定与为联系人指定的电子邮件地址相对应的第三个显示名称。</span><span class="sxs-lookup"><span data-stu-id="786b6-105">Specifies the third display name that corresponds to the email address that is specified for the contact.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="786b6-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="786b6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="786b6-107">dispidEmail3OriginalDisplayName</span><span class="sxs-lookup"><span data-stu-id="786b6-107">dispidEmail3OriginalDisplayName</span></span>  <br/> |
|<span data-ttu-id="786b6-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="786b6-108">Property set:</span></span>  <br/> |<span data-ttu-id="786b6-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="786b6-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="786b6-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="786b6-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="786b6-111">0x000080A4</span><span class="sxs-lookup"><span data-stu-id="786b6-111">0x000080A4</span></span>  <br/> |
|<span data-ttu-id="786b6-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="786b6-112">Data type:</span></span>  <br/> |<span data-ttu-id="786b6-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="786b6-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="786b6-114">区域：</span><span class="sxs-lookup"><span data-stu-id="786b6-114">Area:</span></span>  <br/> |<span data-ttu-id="786b6-115">Contact</span><span class="sxs-lookup"><span data-stu-id="786b6-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="786b6-116">注解</span><span class="sxs-lookup"><span data-stu-id="786b6-116">Remarks</span></span>

<span data-ttu-id="786b6-117">如果**dispidEmail3AddrType** ([PidLidEmail3AddressType](pidlidemail3addresstype-canonical-property.md)) 属性的值为 "SMTP", 则各自的**dispidEmail3OriginalDisplayName**属性的值应等于其各自**的值。dispidEmail3EmailAddress** ([PidLidEmail3EmailAddress](pidlidemail3emailaddress-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="786b6-117">If the value of the **dispidEmail3AddrType** ([PidLidEmail3AddressType](pidlidemail3addresstype-canonical-property.md)) property is "SMTP", the value of the respective **dispidEmail3OriginalDisplayName** property should equal the value of the respective **dispidEmail3EmailAddress** ([PidLidEmail3EmailAddress](pidlidemail3emailaddress-canonical-property.md)).</span></span> <span data-ttu-id="786b6-118">此属性的用途是显示与**dispidEmail3EmailAddress**中的用户友好地址等效的替代用户友好地址。</span><span class="sxs-lookup"><span data-stu-id="786b6-118">The purpose of this property is to display an alternative user-friendly address that is equivalent to the one in the **dispidEmail3EmailAddress**.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="786b6-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="786b6-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="786b6-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="786b6-120">Protocol specifications</span></span>

<span data-ttu-id="786b6-121">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="786b6-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="786b6-122">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="786b6-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="786b6-123">[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="786b6-123">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="786b6-124">指定允许用于联系人和个人通讯组列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="786b6-124">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="786b6-125">头文件</span><span class="sxs-lookup"><span data-stu-id="786b6-125">Header files</span></span>

<span data-ttu-id="786b6-126">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="786b6-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="786b6-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="786b6-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="786b6-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="786b6-128">See also</span></span>



[<span data-ttu-id="786b6-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="786b6-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="786b6-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="786b6-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="786b6-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="786b6-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="786b6-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="786b6-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

