---
title: PidTagUserX509Certificate 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagUserX509Certificate
api_type:
- COM
ms.assetid: 278bb9e4-3ff6-4bef-b208-7924f7a5e9b1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4e6446283116c39080271e5c2fb3ec128b25d32e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360716"
---
# <a name="pidtaguserx509certificate-canonical-property"></a><span data-ttu-id="da2e4-103">PidTagUserX509Certificate 规范属性</span><span class="sxs-lookup"><span data-stu-id="da2e4-103">PidTagUserX509Certificate Canonical Property</span></span>

  
  
<span data-ttu-id="da2e4-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="da2e4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="da2e4-105">包含邮件用户的 X.509 版本 3 安全证书。</span><span class="sxs-lookup"><span data-stu-id="da2e4-105">Contains X.509 version 3 security certificates for a messaging user.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="da2e4-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="da2e4-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="da2e4-107">PR_USER_X509_CERTIFICATE</span><span class="sxs-lookup"><span data-stu-id="da2e4-107">PR_USER_X509_CERTIFICATE</span></span>  <br/> |
|<span data-ttu-id="da2e4-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="da2e4-108">Identifier:</span></span>  <br/> |<span data-ttu-id="da2e4-109">0x3A70</span><span class="sxs-lookup"><span data-stu-id="da2e4-109">0x3A70</span></span>  <br/> |
|<span data-ttu-id="da2e4-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="da2e4-110">Data type:</span></span>  <br/> |<span data-ttu-id="da2e4-111">PT_MV_BINARY</span><span class="sxs-lookup"><span data-stu-id="da2e4-111">PT_MV_BINARY</span></span>  <br/> |
|<span data-ttu-id="da2e4-112">区域：</span><span class="sxs-lookup"><span data-stu-id="da2e4-112">Area:</span></span>  <br/> |<span data-ttu-id="da2e4-113">MAPI 邮件用户</span><span class="sxs-lookup"><span data-stu-id="da2e4-113">MAPI mail user</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="da2e4-114">备注</span><span class="sxs-lookup"><span data-stu-id="da2e4-114">Remarks</span></span>

<span data-ttu-id="da2e4-115">此属性由使用公钥安全性的应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="da2e4-115">This property is used by applications that utilize public-key security.</span></span> <span data-ttu-id="da2e4-116">它保留一个或多个 X.509 版本 3 安全证书的二进制表示形式。</span><span class="sxs-lookup"><span data-stu-id="da2e4-116">It holds a binary representation of one or more X.509 version 3 security certificates.</span></span> 
  
<span data-ttu-id="da2e4-117">各种应用程序和客户端都可以将此属性用于其自己的安全证书。</span><span class="sxs-lookup"><span data-stu-id="da2e4-117">Various applications and clients can use this property for their own security certificates.</span></span> <span data-ttu-id="da2e4-118">X.509 数据的二进制格式可能因供应商而异。</span><span class="sxs-lookup"><span data-stu-id="da2e4-118">The binary format of the X.509 data can vary among vendors.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="da2e4-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="da2e4-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="da2e4-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="da2e4-120">Protocol specifications</span></span>

<span data-ttu-id="da2e4-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="da2e4-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="da2e4-122">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="da2e4-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="da2e4-123">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="da2e4-123">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="da2e4-124">指定用户、联系人、组和资源的列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="da2e4-124">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="da2e4-125">头文件</span><span class="sxs-lookup"><span data-stu-id="da2e4-125">Header files</span></span>

<span data-ttu-id="da2e4-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="da2e4-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="da2e4-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="da2e4-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="da2e4-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="da2e4-128">Mapitags.h</span></span>
  
> <span data-ttu-id="da2e4-129">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="da2e4-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="da2e4-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da2e4-130">See also</span></span>



[<span data-ttu-id="da2e4-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="da2e4-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="da2e4-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="da2e4-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="da2e4-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="da2e4-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="da2e4-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="da2e4-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

