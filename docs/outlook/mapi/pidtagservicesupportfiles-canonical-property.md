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
ms.openlocfilehash: 5165867e46d3d86d65932e7ae432b446efbd8fff
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589124"
---
# <a name="pidtagservicesupportfiles-canonical-property"></a><span data-ttu-id="8b7ca-103">PidTagServiceSupportFiles 规范属性</span><span class="sxs-lookup"><span data-stu-id="8b7ca-103">PidTagServiceSupportFiles Canonical Property</span></span>

  
  
<span data-ttu-id="8b7ca-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8b7ca-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8b7ca-105">包含属于邮件服务的文件列表。</span><span class="sxs-lookup"><span data-stu-id="8b7ca-105">Contains a list of the files that belong to the message service.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8b7ca-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8b7ca-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8b7ca-107">PR_SERVICE_SUPPORT_FILES，PR_SERVICE_SUPPORT_FILES_A，PR_SERVICE_SUPPORT_FILES_W</span><span class="sxs-lookup"><span data-stu-id="8b7ca-107">PR_SERVICE_SUPPORT_FILES, PR_SERVICE_SUPPORT_FILES_A, PR_SERVICE_SUPPORT_FILES_W</span></span>  <br/> |
|<span data-ttu-id="8b7ca-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="8b7ca-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8b7ca-109">0x3D0F</span><span class="sxs-lookup"><span data-stu-id="8b7ca-109">0x3D0F</span></span>  <br/> |
|<span data-ttu-id="8b7ca-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8b7ca-110">Data type:</span></span>  <br/> |<span data-ttu-id="8b7ca-111">PT_MV_STRING8 PT_MV_UNICODE</span><span class="sxs-lookup"><span data-stu-id="8b7ca-111">PT_MV_STRING8, PT_MV_UNICODE</span></span>  <br/> |
|<span data-ttu-id="8b7ca-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8b7ca-112">Area:</span></span>  <br/> |<span data-ttu-id="8b7ca-113">MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="8b7ca-113">MAPI profile</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8b7ca-114">注解</span><span class="sxs-lookup"><span data-stu-id="8b7ca-114">Remarks</span></span>

<span data-ttu-id="8b7ca-115">使用控制面板中的对话框，用户可以获得的文件属于邮件服务的列表。</span><span class="sxs-lookup"><span data-stu-id="8b7ca-115">Using a dialog box in the control panel applet, a user can obtain the list of files that belong to the message service.</span></span> <span data-ttu-id="8b7ca-116">例如，用户可以获得的所有动态链接库 (Dll) 属于该服务的名称。</span><span class="sxs-lookup"><span data-stu-id="8b7ca-116">For example, the user can obtain the names of all dynamic-link libraries (DLLs) that belong to the service.</span></span> <span data-ttu-id="8b7ca-117">然后，用户可以查找有关指定的文件，如名称和版本号的所有 Dll 的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="8b7ca-117">The user can then seek additional details about the specified files, such as the names and version numbers of all the DLLs.</span></span> <span data-ttu-id="8b7ca-118">MAPI 使用这些属性在消息用户所选内容的对话框中创建支持文件列表。</span><span class="sxs-lookup"><span data-stu-id="8b7ca-118">MAPI uses the these properties to create a support file list in a dialog box for messaging user selection.</span></span>
  
<span data-ttu-id="8b7ca-119">MAPI 仅适用于文件名，并在其他字符串传递给它，在 Active Directory 服务接口 (ANSI) 字符集。</span><span class="sxs-lookup"><span data-stu-id="8b7ca-119">MAPI works only with filenames, and other strings passed to it, in the Active Directory Service Interfaces (ANSI) character set.</span></span> <span data-ttu-id="8b7ca-120">使用文件名的原始设备制造商 (OEM) 字符集中的客户端应用程序必须将其转换为 ANSI 调用 MAPI 之前。</span><span class="sxs-lookup"><span data-stu-id="8b7ca-120">Client applications that use filenames in an original equipment manufacturer (OEM) character set must convert them to ANSI before calling MAPI.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="8b7ca-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="8b7ca-121">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="8b7ca-122">头文件</span><span class="sxs-lookup"><span data-stu-id="8b7ca-122">Header files</span></span>

<span data-ttu-id="8b7ca-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8b7ca-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="8b7ca-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8b7ca-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="8b7ca-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="8b7ca-125">Mapitags.h</span></span>
  
> <span data-ttu-id="8b7ca-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8b7ca-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8b7ca-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b7ca-127">See also</span></span>



[<span data-ttu-id="8b7ca-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8b7ca-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8b7ca-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8b7ca-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8b7ca-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8b7ca-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8b7ca-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8b7ca-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

