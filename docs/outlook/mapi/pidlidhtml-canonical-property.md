---
title: PidLidHtml 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidHtml
api_type:
- COM
ms.assetid: 5598cbaf-cb9a-4d3a-b123-9108a7aa7c1c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d05d34c18152c397df04bcf5a82a79d9f1fdd55e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776868"
---
# <a name="pidlidhtml-canonical-property"></a><span data-ttu-id="13845-103">PidLidHtml 规范属性</span><span class="sxs-lookup"><span data-stu-id="13845-103">PidLidHtml Canonical Property</span></span>

  
  
<span data-ttu-id="13845-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="13845-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="13845-105">指定联系人的业务网页的 URL。</span><span class="sxs-lookup"><span data-stu-id="13845-105">Specifies the contact's business Web page URL.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="13845-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="13845-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="13845-107">dispidHTML</span><span class="sxs-lookup"><span data-stu-id="13845-107">dispidHTML</span></span>  <br/> |
|<span data-ttu-id="13845-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="13845-108">Property set:</span></span>  <br/> |<span data-ttu-id="13845-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="13845-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="13845-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="13845-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="13845-111">0x0000802B</span><span class="sxs-lookup"><span data-stu-id="13845-111">0x0000802B</span></span>  <br/> |
|<span data-ttu-id="13845-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="13845-112">Data type:</span></span>  <br/> |<span data-ttu-id="13845-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="13845-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="13845-114">区域：</span><span class="sxs-lookup"><span data-stu-id="13845-114">Area:</span></span>  <br/> |<span data-ttu-id="13845-115">联系人</span><span class="sxs-lookup"><span data-stu-id="13845-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="13845-116">说明</span><span class="sxs-lookup"><span data-stu-id="13845-116">Remarks</span></span>

<span data-ttu-id="13845-117">此属性值，如果存在此参数，应为**PR_BUSINESS_HOME_PAGE** ([PidTagBusinessHomePage](pidtagbusinesshomepage-canonical-property.md)) 属性的值相同。</span><span class="sxs-lookup"><span data-stu-id="13845-117">The value of this property, if present, should be the same as the value of the **PR_BUSINESS_HOME_PAGE** ([PidTagBusinessHomePage](pidtagbusinesshomepage-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="13845-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="13845-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="13845-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="13845-119">Protocol specifications</span></span>

<span data-ttu-id="13845-120">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="13845-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="13845-121">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="13845-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="13845-122">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="13845-122">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="13845-123">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="13845-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="13845-124">头文件</span><span class="sxs-lookup"><span data-stu-id="13845-124">Header files</span></span>

<span data-ttu-id="13845-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="13845-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="13845-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="13845-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="13845-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13845-127">See also</span></span>



[<span data-ttu-id="13845-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="13845-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="13845-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="13845-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="13845-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="13845-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="13845-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="13845-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

