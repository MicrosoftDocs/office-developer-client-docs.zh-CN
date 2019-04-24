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
ms.openlocfilehash: dd80c969c3ef7af280248d9570e684cd7278e9e1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357573"
---
# <a name="pidlidhtml-canonical-property"></a><span data-ttu-id="f23e0-103">PidLidHtml 规范属性</span><span class="sxs-lookup"><span data-stu-id="f23e0-103">PidLidHtml Canonical Property</span></span>

  
  
<span data-ttu-id="f23e0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f23e0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f23e0-105">指定联系人的业务网页 URL。</span><span class="sxs-lookup"><span data-stu-id="f23e0-105">Specifies the contact's business Web page URL.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f23e0-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f23e0-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f23e0-107">dispidHTML</span><span class="sxs-lookup"><span data-stu-id="f23e0-107">dispidHTML</span></span>  <br/> |
|<span data-ttu-id="f23e0-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="f23e0-108">Property set:</span></span>  <br/> |<span data-ttu-id="f23e0-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="f23e0-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="f23e0-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="f23e0-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="f23e0-111">0x0000802B</span><span class="sxs-lookup"><span data-stu-id="f23e0-111">0x0000802B</span></span>  <br/> |
|<span data-ttu-id="f23e0-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f23e0-112">Data type:</span></span>  <br/> |<span data-ttu-id="f23e0-113">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="f23e0-113">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="f23e0-114">区域：</span><span class="sxs-lookup"><span data-stu-id="f23e0-114">Area:</span></span>  <br/> |<span data-ttu-id="f23e0-115">Contact</span><span class="sxs-lookup"><span data-stu-id="f23e0-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f23e0-116">注解</span><span class="sxs-lookup"><span data-stu-id="f23e0-116">Remarks</span></span>

<span data-ttu-id="f23e0-117">此属性的值 (如果存在) 应与**PR_BUSINESS_HOME_PAGE** ([PidTagBusinessHomePage](pidtagbusinesshomepage-canonical-property.md)) 属性的值相同。</span><span class="sxs-lookup"><span data-stu-id="f23e0-117">The value of this property, if present, should be the same as the value of the **PR_BUSINESS_HOME_PAGE** ([PidTagBusinessHomePage](pidtagbusinesshomepage-canonical-property.md)) property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="f23e0-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="f23e0-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="f23e0-119">协议规范</span><span class="sxs-lookup"><span data-stu-id="f23e0-119">Protocol specifications</span></span>

<span data-ttu-id="f23e0-120">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f23e0-120">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f23e0-121">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="f23e0-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="f23e0-122">[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="f23e0-122">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="f23e0-123">指定允许用于联系人和个人通讯组列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="f23e0-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="f23e0-124">头文件</span><span class="sxs-lookup"><span data-stu-id="f23e0-124">Header files</span></span>

<span data-ttu-id="f23e0-125">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="f23e0-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="f23e0-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f23e0-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f23e0-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f23e0-127">See also</span></span>



[<span data-ttu-id="f23e0-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f23e0-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f23e0-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f23e0-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f23e0-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f23e0-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f23e0-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f23e0-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

