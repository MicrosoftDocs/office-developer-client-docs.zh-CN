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
ms.openlocfilehash: da01385f83d9af9ad02eeb2fed08e3bc22d4df84
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436823"
---
# <a name="pidtagservicedeletefiles-canonical-property"></a><span data-ttu-id="63fff-103">PidTagServiceDeleteFiles 规范属性</span><span class="sxs-lookup"><span data-stu-id="63fff-103">PidTagServiceDeleteFiles Canonical Property</span></span>

  
  
<span data-ttu-id="63fff-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="63fff-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="63fff-105">包含在卸载邮件服务时要删除的文件名的列表。</span><span class="sxs-lookup"><span data-stu-id="63fff-105">Contains a list of filenames that are to be deleted when the message service is uninstalled.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="63fff-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="63fff-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="63fff-107">PR_SERVICE_DELETE_FILES、PR_SERVICE_DELETE_FILES_A、PR_SERVICE_DELETE_FILES_W</span><span class="sxs-lookup"><span data-stu-id="63fff-107">PR_SERVICE_DELETE_FILES, PR_SERVICE_DELETE_FILES_A, PR_SERVICE_DELETE_FILES_W</span></span>  <br/> |
|<span data-ttu-id="63fff-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="63fff-108">Identifier:</span></span>  <br/> |<span data-ttu-id="63fff-109">0x3D10</span><span class="sxs-lookup"><span data-stu-id="63fff-109">0x3D10</span></span>  <br/> |
|<span data-ttu-id="63fff-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="63fff-110">Data type:</span></span>  <br/> |<span data-ttu-id="63fff-111">PT_MV_STRING8、PT_MV_UNICODE</span><span class="sxs-lookup"><span data-stu-id="63fff-111">PT_MV_STRING8, PT_MV_UNICODE</span></span>  <br/> |
|<span data-ttu-id="63fff-112">区域：</span><span class="sxs-lookup"><span data-stu-id="63fff-112">Area:</span></span>  <br/> |<span data-ttu-id="63fff-113">MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="63fff-113">MAPI profile</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="63fff-114">说明</span><span class="sxs-lookup"><span data-stu-id="63fff-114">Remarks</span></span>

<span data-ttu-id="63fff-115">使用 "控制面板" 卸载邮件服务时, 这些属性中包含的列表中的文件名将从计算机中删除。</span><span class="sxs-lookup"><span data-stu-id="63fff-115">The filenames in the list contained in these properties are deleted from the computer when using the control panel to uninstall the message service.</span></span> <span data-ttu-id="63fff-116">请勿在列表中包含任何支持多个邮件服务的 DLL, 或者可能无意中删除了其他邮件服务。</span><span class="sxs-lookup"><span data-stu-id="63fff-116">Do not include in the list any DLL that supports multiple message services, or additional message services could be inadvertently removed.</span></span>
  
<span data-ttu-id="63fff-117">MAPI 仅适用于文件名以及在 ANSI 字符集中传递给它的其他字符串。</span><span class="sxs-lookup"><span data-stu-id="63fff-117">MAPI works only with filenames, and other strings passed to it, in the ANSI character set.</span></span> <span data-ttu-id="63fff-118">使用 OEM 字符集中的文件名的应用程序必须先将其转换为 ANSI, 然后再调用 MAPI。</span><span class="sxs-lookup"><span data-stu-id="63fff-118">Applications that use filenames in an OEM character set must convert them to ANSI before calling MAPI.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="63fff-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="63fff-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="63fff-120">头文件</span><span class="sxs-lookup"><span data-stu-id="63fff-120">Header files</span></span>

<span data-ttu-id="63fff-121">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="63fff-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="63fff-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="63fff-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="63fff-123">Mapitags</span><span class="sxs-lookup"><span data-stu-id="63fff-123">Mapitags.h</span></span>
  
> <span data-ttu-id="63fff-124">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="63fff-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="63fff-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63fff-125">See also</span></span>



[<span data-ttu-id="63fff-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="63fff-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="63fff-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="63fff-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="63fff-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="63fff-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="63fff-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="63fff-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

