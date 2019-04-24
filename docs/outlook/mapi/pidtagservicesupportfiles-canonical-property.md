---
title: PidTagServiceSupportFiles 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagServiceSupportFiles
api_type:
- COM
ms.assetid: df4be986-62a8-49d6-8eca-25b55c74f830
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3753177552d45e32e53ae192a9dfae15b601afcc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359470"
---
# <a name="pidtagservicesupportfiles-canonical-property"></a><span data-ttu-id="0528b-103">PidTagServiceSupportFiles 规范属性</span><span class="sxs-lookup"><span data-stu-id="0528b-103">PidTagServiceSupportFiles Canonical Property</span></span>

  
  
<span data-ttu-id="0528b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0528b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0528b-105">包含属于邮件服务的文件的列表。</span><span class="sxs-lookup"><span data-stu-id="0528b-105">Contains a list of the files that belong to the message service.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0528b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0528b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0528b-107">PR_SERVICE_SUPPORT_FILES、PR_SERVICE_SUPPORT_FILES_A、PR_SERVICE_SUPPORT_FILES_W</span><span class="sxs-lookup"><span data-stu-id="0528b-107">PR_SERVICE_SUPPORT_FILES, PR_SERVICE_SUPPORT_FILES_A, PR_SERVICE_SUPPORT_FILES_W</span></span>  <br/> |
|<span data-ttu-id="0528b-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="0528b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0528b-109">0x3D0F</span><span class="sxs-lookup"><span data-stu-id="0528b-109">0x3D0F</span></span>  <br/> |
|<span data-ttu-id="0528b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0528b-110">Data type:</span></span>  <br/> |<span data-ttu-id="0528b-111">PT_MV_STRING8、PT_MV_UNICODE</span><span class="sxs-lookup"><span data-stu-id="0528b-111">PT_MV_STRING8, PT_MV_UNICODE</span></span>  <br/> |
|<span data-ttu-id="0528b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0528b-112">Area:</span></span>  <br/> |<span data-ttu-id="0528b-113">MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="0528b-113">MAPI profile</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0528b-114">注解</span><span class="sxs-lookup"><span data-stu-id="0528b-114">Remarks</span></span>

<span data-ttu-id="0528b-115">通过在控制面板小程序中使用对话框, 用户可以获取属于邮件服务的文件的列表。</span><span class="sxs-lookup"><span data-stu-id="0528b-115">Using a dialog box in the control panel applet, a user can obtain the list of files that belong to the message service.</span></span> <span data-ttu-id="0528b-116">例如, 用户可以获取属于该服务的所有动态链接库 (dll) 的名称。</span><span class="sxs-lookup"><span data-stu-id="0528b-116">For example, the user can obtain the names of all dynamic-link libraries (DLLs) that belong to the service.</span></span> <span data-ttu-id="0528b-117">然后, 用户可以查找有关指定文件的其他详细信息, 如所有 dll 的名称和版本号。</span><span class="sxs-lookup"><span data-stu-id="0528b-117">The user can then seek additional details about the specified files, such as the names and version numbers of all the DLLs.</span></span> <span data-ttu-id="0528b-118">MAPI 使用这些属性在用于邮件用户选择的对话框中创建支持文件列表。</span><span class="sxs-lookup"><span data-stu-id="0528b-118">MAPI uses the these properties to create a support file list in a dialog box for messaging user selection.</span></span>
  
<span data-ttu-id="0528b-119">MAPI 仅适用于在 Active Directory 服务接口 (ANSI) 字符集中的文件名和传递给它的其他字符串。</span><span class="sxs-lookup"><span data-stu-id="0528b-119">MAPI works only with filenames, and other strings passed to it, in the Active Directory Service Interfaces (ANSI) character set.</span></span> <span data-ttu-id="0528b-120">使用原始设备制造商 (OEM) 字符集中的文件名的客户端应用程序必须先将其转换为 ANSI, 然后再调用 MAPI。</span><span class="sxs-lookup"><span data-stu-id="0528b-120">Client applications that use filenames in an original equipment manufacturer (OEM) character set must convert them to ANSI before calling MAPI.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="0528b-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="0528b-121">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="0528b-122">头文件</span><span class="sxs-lookup"><span data-stu-id="0528b-122">Header files</span></span>

<span data-ttu-id="0528b-123">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="0528b-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="0528b-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0528b-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="0528b-125">Mapitags</span><span class="sxs-lookup"><span data-stu-id="0528b-125">Mapitags.h</span></span>
  
> <span data-ttu-id="0528b-126">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0528b-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0528b-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0528b-127">See also</span></span>



[<span data-ttu-id="0528b-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0528b-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0528b-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0528b-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0528b-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0528b-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0528b-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0528b-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

