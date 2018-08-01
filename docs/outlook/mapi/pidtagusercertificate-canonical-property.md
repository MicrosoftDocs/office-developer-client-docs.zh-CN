---
title: PidTagUserCertificate 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagUserCertificate
api_type:
- COM
ms.assetid: 2ac14c43-36c1-4f2f-97b0-2462f2360575
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0dd477a055562f692c8869bc436c4238c77fd02a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778530"
---
# <a name="pidtagusercertificate-canonical-property"></a><span data-ttu-id="7f55b-103">PidTagUserCertificate 规范属性</span><span class="sxs-lookup"><span data-stu-id="7f55b-103">PidTagUserCertificate Canonical Property</span></span>

  
  
<span data-ttu-id="7f55b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7f55b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7f55b-105">包含消息的用户 ASN.1 身份验证证书。</span><span class="sxs-lookup"><span data-stu-id="7f55b-105">Contains an ASN.1 authentication certificate for a messaging user.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7f55b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7f55b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7f55b-107">PR_USER_CERTIFICATE</span><span class="sxs-lookup"><span data-stu-id="7f55b-107">PR_USER_CERTIFICATE</span></span>  <br/> |
|<span data-ttu-id="7f55b-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="7f55b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="7f55b-109">0x3A22</span><span class="sxs-lookup"><span data-stu-id="7f55b-109">0x3A22</span></span>  <br/> |
|<span data-ttu-id="7f55b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7f55b-110">Data type:</span></span>  <br/> |<span data-ttu-id="7f55b-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="7f55b-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="7f55b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="7f55b-112">Area:</span></span>  <br/> |<span data-ttu-id="7f55b-113">MAPI 邮件用户</span><span class="sxs-lookup"><span data-stu-id="7f55b-113">MAPI mail user</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7f55b-114">说明</span><span class="sxs-lookup"><span data-stu-id="7f55b-114">Remarks</span></span>

<span data-ttu-id="7f55b-115">类似于数字签名的身份验证证书。</span><span class="sxs-lookup"><span data-stu-id="7f55b-115">An authentication certificate is similar to a digital signature.</span></span> <span data-ttu-id="7f55b-116">几个 MAPI 属性提供 ASN.1 证书。</span><span class="sxs-lookup"><span data-stu-id="7f55b-116">Several MAPI properties supply ASN.1 certificates.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="7f55b-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="7f55b-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7f55b-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="7f55b-118">Protocol specifications</span></span>

<span data-ttu-id="7f55b-119">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7f55b-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7f55b-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="7f55b-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7f55b-121">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7f55b-121">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7f55b-122">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="7f55b-122">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7f55b-123">头文件</span><span class="sxs-lookup"><span data-stu-id="7f55b-123">Header files</span></span>

<span data-ttu-id="7f55b-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7f55b-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="7f55b-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7f55b-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="7f55b-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="7f55b-126">Mapitags.h</span></span>
  
> <span data-ttu-id="7f55b-127">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="7f55b-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7f55b-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7f55b-128">See also</span></span>



[<span data-ttu-id="7f55b-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7f55b-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7f55b-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7f55b-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7f55b-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7f55b-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7f55b-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7f55b-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

