---
title: PidTagEmsAbServer 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagEmsAbServer
api_type:
- HeaderDef
ms.assetid: de942619-2507-8fe0-bc81-f9da9ef7266f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0d31272e63df7f68a83b23ca7a3824c081de3c1d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569265"
---
# <a name="pidtagemsabserver-canonical-property"></a><span data-ttu-id="bffa9-103">PidTagEmsAbServer 规范属性</span><span class="sxs-lookup"><span data-stu-id="bffa9-103">PidTagEmsAbServer Canonical Property</span></span>

  
  
<span data-ttu-id="bffa9-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bffa9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bffa9-105">指定通讯簿容器路径中脱机方案或通讯簿容器所在 online 方案中的全局编录服务器的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="bffa9-105">Specifies either the path of an address book container in an offline scenario or the fully qualified domain name of the global catalog server where the address book container resides in an online scenario.</span></span>
  
## 

|||
|:-----|:-----|
|<span data-ttu-id="bffa9-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="bffa9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="bffa9-107">PR_EMS_AB_SERVER，PR_EMS_AB_SERVER_A，PR_EMS_AB_SERVER_W</span><span class="sxs-lookup"><span data-stu-id="bffa9-107">PR_EMS_AB_SERVER, PR_EMS_AB_SERVER_A, PR_EMS_AB_SERVER_W</span></span>  <br/> |
|<span data-ttu-id="bffa9-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="bffa9-108">Identifier:</span></span>  <br/> |<span data-ttu-id="bffa9-109">0xFFFE</span><span class="sxs-lookup"><span data-stu-id="bffa9-109">0xFFFE</span></span>  <br/> |
|<span data-ttu-id="bffa9-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="bffa9-110">Data type:</span></span>  <br/> |<span data-ttu-id="bffa9-111">PT_TSTRING</span><span class="sxs-lookup"><span data-stu-id="bffa9-111">PT_TSTRING</span></span>  <br/> |
|<span data-ttu-id="bffa9-112">区域：</span><span class="sxs-lookup"><span data-stu-id="bffa9-112">Area:</span></span>  <br/> |<span data-ttu-id="bffa9-113">通讯簿</span><span class="sxs-lookup"><span data-stu-id="bffa9-113">Address Book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bffa9-114">注解</span><span class="sxs-lookup"><span data-stu-id="bffa9-114">Remarks</span></span>

<span data-ttu-id="bffa9-115">此属性包含属性类型与编译时重置为**PT_UNICODE** `UNICODE`符号在 Unicode 平台上，并为**PT_STRING8**不与编译时`UNICODE`符号。</span><span class="sxs-lookup"><span data-stu-id="bffa9-115">This property has the property type reset to **PT_UNICODE** when it is compiled with the  `UNICODE` symbol on a Unicode platform, and to **PT_STRING8** when it is not compiled with the  `UNICODE` symbol.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="bffa9-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="bffa9-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="bffa9-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="bffa9-117">Protocol specifications</span></span>

<span data-ttu-id="bffa9-118">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="bffa9-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="bffa9-119">提供属性集定义。</span><span class="sxs-lookup"><span data-stu-id="bffa9-119">Provides property set definitions.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="bffa9-120">头文件</span><span class="sxs-lookup"><span data-stu-id="bffa9-120">Header files</span></span>

<span data-ttu-id="bffa9-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="bffa9-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="bffa9-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="bffa9-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="bffa9-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="bffa9-123">Mapitags.h</span></span>
  
> <span data-ttu-id="bffa9-124">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="bffa9-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="bffa9-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bffa9-125">See also</span></span>



[<span data-ttu-id="bffa9-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="bffa9-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="bffa9-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="bffa9-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="bffa9-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="bffa9-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="bffa9-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="bffa9-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

