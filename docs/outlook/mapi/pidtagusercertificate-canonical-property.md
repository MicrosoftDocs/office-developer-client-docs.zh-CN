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
ms.openlocfilehash: 53ee4019752cf717840199d4a51cbc90133b8636
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32320389"
---
# <a name="pidtagusercertificate-canonical-property"></a><span data-ttu-id="e755e-103">PidTagUserCertificate 规范属性</span><span class="sxs-lookup"><span data-stu-id="e755e-103">PidTagUserCertificate Canonical Property</span></span>

  
  
<span data-ttu-id="e755e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e755e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e755e-105">包含邮件用户的 ASN.1 身份验证证书。</span><span class="sxs-lookup"><span data-stu-id="e755e-105">Contains an ASN.1 authentication certificate for a messaging user.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e755e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="e755e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e755e-107">PR_USER_CERTIFICATE</span><span class="sxs-lookup"><span data-stu-id="e755e-107">PR_USER_CERTIFICATE</span></span>  <br/> |
|<span data-ttu-id="e755e-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="e755e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e755e-109">0x3A22</span><span class="sxs-lookup"><span data-stu-id="e755e-109">0x3A22</span></span>  <br/> |
|<span data-ttu-id="e755e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="e755e-110">Data type:</span></span>  <br/> |<span data-ttu-id="e755e-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="e755e-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="e755e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="e755e-112">Area:</span></span>  <br/> |<span data-ttu-id="e755e-113">MAPI 邮件用户</span><span class="sxs-lookup"><span data-stu-id="e755e-113">MAPI mail user</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e755e-114">备注</span><span class="sxs-lookup"><span data-stu-id="e755e-114">Remarks</span></span>

<span data-ttu-id="e755e-115">身份验证证书类似于数字签名。</span><span class="sxs-lookup"><span data-stu-id="e755e-115">An authentication certificate is similar to a digital signature.</span></span> <span data-ttu-id="e755e-116">多个 MAPI 属性提供 ASN.1 证书。</span><span class="sxs-lookup"><span data-stu-id="e755e-116">Several MAPI properties supply ASN.1 certificates.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="e755e-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="e755e-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e755e-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="e755e-118">Protocol specifications</span></span>

<span data-ttu-id="e755e-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e755e-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e755e-120">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="e755e-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e755e-121">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e755e-121">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e755e-122">指定用户、联系人、组和资源的列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="e755e-122">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e755e-123">头文件</span><span class="sxs-lookup"><span data-stu-id="e755e-123">Header files</span></span>

<span data-ttu-id="e755e-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e755e-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="e755e-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="e755e-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="e755e-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e755e-126">Mapitags.h</span></span>
  
> <span data-ttu-id="e755e-127">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="e755e-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e755e-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e755e-128">See also</span></span>



[<span data-ttu-id="e755e-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="e755e-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e755e-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="e755e-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e755e-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="e755e-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e755e-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="e755e-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

