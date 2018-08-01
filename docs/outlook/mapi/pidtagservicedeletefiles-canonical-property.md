---
title: PidTagServiceDeleteFiles 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagServiceDeleteFiles
api_type:
- COM
ms.assetid: 9ec80a93-9e8f-46be-a1d4-7648aae47fec
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8f90d72e842df62c19c5aeeaf6c398c5db469560
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778413"
---
# <a name="pidtagservicedeletefiles-canonical-property"></a><span data-ttu-id="f64a1-103">PidTagServiceDeleteFiles 规范属性</span><span class="sxs-lookup"><span data-stu-id="f64a1-103">PidTagServiceDeleteFiles Canonical Property</span></span>

  
  
<span data-ttu-id="f64a1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f64a1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f64a1-105">包含文件名的要卸载邮件服务时删除的列表。</span><span class="sxs-lookup"><span data-stu-id="f64a1-105">Contains a list of filenames that are to be deleted when the message service is uninstalled.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f64a1-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f64a1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f64a1-107">PR_SERVICE_DELETE_FILES，PR_SERVICE_DELETE_FILES_A，PR_SERVICE_DELETE_FILES_W</span><span class="sxs-lookup"><span data-stu-id="f64a1-107">PR_SERVICE_DELETE_FILES, PR_SERVICE_DELETE_FILES_A, PR_SERVICE_DELETE_FILES_W</span></span>  <br/> |
|<span data-ttu-id="f64a1-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="f64a1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f64a1-109">0x3D10</span><span class="sxs-lookup"><span data-stu-id="f64a1-109">0x3D10</span></span>  <br/> |
|<span data-ttu-id="f64a1-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f64a1-110">Data type:</span></span>  <br/> |<span data-ttu-id="f64a1-111">PT_MV_STRING8 PT_MV_UNICODE</span><span class="sxs-lookup"><span data-stu-id="f64a1-111">PT_MV_STRING8, PT_MV_UNICODE</span></span>  <br/> |
|<span data-ttu-id="f64a1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f64a1-112">Area:</span></span>  <br/> |<span data-ttu-id="f64a1-113">MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="f64a1-113">MAPI profile</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f64a1-114">说明</span><span class="sxs-lookup"><span data-stu-id="f64a1-114">Remarks</span></span>

<span data-ttu-id="f64a1-115">使用控制面板卸载邮件服务时，将从计算机中删除这些属性中包含的列表中的文件名。</span><span class="sxs-lookup"><span data-stu-id="f64a1-115">The filenames in the list contained in these properties are deleted from the computer when using the control panel to uninstall the message service.</span></span> <span data-ttu-id="f64a1-116">不包含在列表中支持多个邮件服务，任何 DLL 或其他邮件服务无法无意删除。</span><span class="sxs-lookup"><span data-stu-id="f64a1-116">Do not include in the list any DLL that supports multiple message services, or additional message services could be inadvertently removed.</span></span>
  
<span data-ttu-id="f64a1-117">MAPI 仅适用于文件名，并在其他字符串传递给它，在 ANSI 字符集。</span><span class="sxs-lookup"><span data-stu-id="f64a1-117">MAPI works only with filenames, and other strings passed to it, in the ANSI character set.</span></span> <span data-ttu-id="f64a1-118">使用 OEM 字符集中的文件名的应用程序必须将其转换为 ANSI 调用 MAPI 之前。</span><span class="sxs-lookup"><span data-stu-id="f64a1-118">Applications that use filenames in an OEM character set must convert them to ANSI before calling MAPI.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="f64a1-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="f64a1-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="f64a1-120">头文件</span><span class="sxs-lookup"><span data-stu-id="f64a1-120">Header files</span></span>

<span data-ttu-id="f64a1-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f64a1-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="f64a1-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f64a1-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="f64a1-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="f64a1-123">Mapitags.h</span></span>
  
> <span data-ttu-id="f64a1-124">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f64a1-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f64a1-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f64a1-125">See also</span></span>



[<span data-ttu-id="f64a1-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f64a1-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f64a1-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f64a1-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f64a1-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f64a1-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f64a1-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f64a1-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

