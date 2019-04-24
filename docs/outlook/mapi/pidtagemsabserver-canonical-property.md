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
ms.openlocfilehash: fba49b052a51bd498f61fc115f630d08fc6c8926
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32335795"
---
# <a name="pidtagemsabserver-canonical-property"></a><span data-ttu-id="699b3-103">PidTagEmsAbServer 规范属性</span><span class="sxs-lookup"><span data-stu-id="699b3-103">PidTagEmsAbServer Canonical Property</span></span>

  
  
<span data-ttu-id="699b3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="699b3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="699b3-105">指定脱机方案中的通讯簿容器的路径或全局编录服务器的完全限定域名, 通讯簿容器驻留在联机方案中。</span><span class="sxs-lookup"><span data-stu-id="699b3-105">Specifies either the path of an address book container in an offline scenario or the fully qualified domain name of the global catalog server where the address book container resides in an online scenario.</span></span>
  
## 

|||
|:-----|:-----|
|<span data-ttu-id="699b3-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="699b3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="699b3-107">PR_EMS_AB_SERVER、PR_EMS_AB_SERVER_A、PR_EMS_AB_SERVER_W</span><span class="sxs-lookup"><span data-stu-id="699b3-107">PR_EMS_AB_SERVER, PR_EMS_AB_SERVER_A, PR_EMS_AB_SERVER_W</span></span>  <br/> |
|<span data-ttu-id="699b3-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="699b3-108">Identifier:</span></span>  <br/> |<span data-ttu-id="699b3-109">0xFFFE</span><span class="sxs-lookup"><span data-stu-id="699b3-109">0xFFFE</span></span>  <br/> |
|<span data-ttu-id="699b3-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="699b3-110">Data type:</span></span>  <br/> |<span data-ttu-id="699b3-111">PT_TSTRING</span><span class="sxs-lookup"><span data-stu-id="699b3-111">PT_TSTRING</span></span>  <br/> |
|<span data-ttu-id="699b3-112">区域：</span><span class="sxs-lookup"><span data-stu-id="699b3-112">Area:</span></span>  <br/> |<span data-ttu-id="699b3-113">通讯簿</span><span class="sxs-lookup"><span data-stu-id="699b3-113">Address Book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="699b3-114">注解</span><span class="sxs-lookup"><span data-stu-id="699b3-114">Remarks</span></span>

<span data-ttu-id="699b3-115">当使用 UNICODE 平台上的`UNICODE`符号编译此属性的属性类型时, 此属性会将该属性重置为**PT_UNICODE** , 如果不使用`UNICODE`符号编译该属性, 则为**PT_STRING8** 。</span><span class="sxs-lookup"><span data-stu-id="699b3-115">This property has the property type reset to **PT_UNICODE** when it is compiled with the  `UNICODE` symbol on a Unicode platform, and to **PT_STRING8** when it is not compiled with the  `UNICODE` symbol.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="699b3-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="699b3-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="699b3-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="699b3-117">Protocol specifications</span></span>

<span data-ttu-id="699b3-118">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="699b3-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="699b3-119">提供属性集定义。</span><span class="sxs-lookup"><span data-stu-id="699b3-119">Provides property set definitions.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="699b3-120">头文件</span><span class="sxs-lookup"><span data-stu-id="699b3-120">Header files</span></span>

<span data-ttu-id="699b3-121">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="699b3-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="699b3-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="699b3-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="699b3-123">Mapitags</span><span class="sxs-lookup"><span data-stu-id="699b3-123">Mapitags.h</span></span>
  
> <span data-ttu-id="699b3-124">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="699b3-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="699b3-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="699b3-125">See also</span></span>



[<span data-ttu-id="699b3-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="699b3-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="699b3-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="699b3-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="699b3-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="699b3-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="699b3-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="699b3-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

