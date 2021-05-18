---
title: PidTagMessageDownloadTime 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageDownloadTime
api_type:
- HeaderDef
ms.assetid: f0d34dd6-7ddb-4843-b848-c89923ff80cc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8078d31af497a437c983da7447a0aebbdfb643fb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407926"
---
# <a name="pidtagmessagedownloadtime-canonical-property"></a><span data-ttu-id="f7bc3-103">PidTagMessageDownloadTime 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7bc3-103">PidTagMessageDownloadTime Canonical Property</span></span>

  
  
<span data-ttu-id="f7bc3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f7bc3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f7bc3-105">包含将邮件从远程服务器下载到本地邮件存储的估计时间。</span><span class="sxs-lookup"><span data-stu-id="f7bc3-105">Contains the estimated time to download a message from a remote server to a local message store.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f7bc3-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="f7bc3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f7bc3-107">PR_MESSAGE_DOWNLOAD_TIME</span><span class="sxs-lookup"><span data-stu-id="f7bc3-107">PR_MESSAGE_DOWNLOAD_TIME</span></span>  <br/> |
|<span data-ttu-id="f7bc3-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="f7bc3-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f7bc3-109">0x0E18</span><span class="sxs-lookup"><span data-stu-id="f7bc3-109">0x0E18</span></span>  <br/> |
|<span data-ttu-id="f7bc3-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f7bc3-110">Data type:</span></span>  <br/> |<span data-ttu-id="f7bc3-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="f7bc3-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="f7bc3-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f7bc3-112">Area:</span></span>  <br/> |<span data-ttu-id="f7bc3-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="f7bc3-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f7bc3-114">备注</span><span class="sxs-lookup"><span data-stu-id="f7bc3-114">Remarks</span></span>

<span data-ttu-id="f7bc3-115">此属性以秒表示，表示远程传输提供程序将给定邮件从当前位置下载到客户端查看头文件夹的本地邮件存储所花的最佳估计时间。</span><span class="sxs-lookup"><span data-stu-id="f7bc3-115">This property is expressed in seconds and represents the best estimate of the time it would take a remote transport provider to download a given message from its current location to a message store local to the client viewing the header folder.</span></span> <span data-ttu-id="f7bc3-116">远程传输提供程序通常通过将 **PR_MESSAGE_SIZE** ([PidTagMessageSize](pidtagmessagesize-canonical-property.md)) 属性的值除以通信链接的速度（以字节/秒为单位）来计算此属性的值。</span><span class="sxs-lookup"><span data-stu-id="f7bc3-116">The remote transport provider typically calculates the value for this property by dividing the value of the **PR_MESSAGE_SIZE** ([PidTagMessageSize](pidtagmessagesize-canonical-property.md)) property by the speed of the communications link in bytes per second.</span></span> <span data-ttu-id="f7bc3-117">如果提供程序无法计算下载时间，例如，如果不知道链接速度，则应该提供 **PT_ERROR** 值（如 **MAPI_E_NO_SUPPORT）** 作为标题文件夹内容表中的此列。</span><span class="sxs-lookup"><span data-stu-id="f7bc3-117">If the provider cannot calculate the download time, for example if it does not know the link speed, it should furnish a **PT_ERROR** value such as **MAPI_E_NO_SUPPORT** for this column in the header folder contents table.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="f7bc3-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="f7bc3-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="f7bc3-119">头文件</span><span class="sxs-lookup"><span data-stu-id="f7bc3-119">Header files</span></span>

<span data-ttu-id="f7bc3-120">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f7bc3-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="f7bc3-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f7bc3-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="f7bc3-122">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="f7bc3-122">Mapitags.h</span></span>
  
> <span data-ttu-id="f7bc3-123">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f7bc3-123">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f7bc3-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7bc3-124">See also</span></span>



[<span data-ttu-id="f7bc3-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f7bc3-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f7bc3-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f7bc3-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f7bc3-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="f7bc3-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f7bc3-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f7bc3-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

