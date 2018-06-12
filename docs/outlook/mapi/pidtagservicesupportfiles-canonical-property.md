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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 2dc431d807bd74640e5b5a9c020f668b13530197
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778437"
---
# <a name="pidtagservicesupportfiles-canonical-property"></a><span data-ttu-id="f18a7-103">PidTagServiceSupportFiles 规范属性</span><span class="sxs-lookup"><span data-stu-id="f18a7-103">PidTagServiceSupportFiles Canonical Property</span></span>

  
  
<span data-ttu-id="f18a7-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f18a7-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f18a7-105">包含属于邮件服务的文件列表。</span><span class="sxs-lookup"><span data-stu-id="f18a7-105">Contains a list of the files that belong to the message service.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f18a7-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="f18a7-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="f18a7-107">PR_SERVICE_SUPPORT_FILES，PR_SERVICE_SUPPORT_FILES_A，PR_SERVICE_SUPPORT_FILES_W</span><span class="sxs-lookup"><span data-stu-id="f18a7-107">PR_SERVICE_SUPPORT_FILES, PR_SERVICE_SUPPORT_FILES_A, PR_SERVICE_SUPPORT_FILES_W</span></span>  <br/> |
|<span data-ttu-id="f18a7-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="f18a7-108">Identifier:</span></span>  <br/> |<span data-ttu-id="f18a7-109">0x3D0F</span><span class="sxs-lookup"><span data-stu-id="f18a7-109">0x3D0F</span></span>  <br/> |
|<span data-ttu-id="f18a7-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="f18a7-110">Data type:</span></span>  <br/> |<span data-ttu-id="f18a7-111">PT_MV_STRING8 PT_MV_UNICODE</span><span class="sxs-lookup"><span data-stu-id="f18a7-111">PT_MV_STRING8, PT_MV_UNICODE</span></span>  <br/> |
|<span data-ttu-id="f18a7-112">区域：</span><span class="sxs-lookup"><span data-stu-id="f18a7-112">Area:</span></span>  <br/> |<span data-ttu-id="f18a7-113">MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="f18a7-113">MAPI profile</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="f18a7-114">备注</span><span class="sxs-lookup"><span data-stu-id="f18a7-114">Remarks</span></span>

<span data-ttu-id="f18a7-115">使用控制面板中的对话框，用户可以获得的文件属于邮件服务的列表。</span><span class="sxs-lookup"><span data-stu-id="f18a7-115">Using a dialog box in the control panel applet, a user can obtain the list of files that belong to the message service.</span></span> <span data-ttu-id="f18a7-116">例如，用户可以获得的所有动态链接库 (Dll) 属于该服务的名称。</span><span class="sxs-lookup"><span data-stu-id="f18a7-116">For example, the user can obtain the names of all dynamic-link libraries (DLLs) that belong to the service.</span></span> <span data-ttu-id="f18a7-117">然后，用户可以查找有关指定的文件，如名称和版本号的所有 Dll 的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="f18a7-117">The user can then seek additional details about the specified files, such as the names and version numbers of all the DLLs.</span></span> <span data-ttu-id="f18a7-118">MAPI 使用这些属性在消息用户所选内容的对话框中创建支持文件列表。</span><span class="sxs-lookup"><span data-stu-id="f18a7-118">MAPI uses the these properties to create a support file list in a dialog box for messaging user selection.</span></span>
  
<span data-ttu-id="f18a7-119">MAPI 仅适用于文件名，并在其他字符串传递给它，在 Active Directory 服务接口 (ANSI) 字符集。</span><span class="sxs-lookup"><span data-stu-id="f18a7-119">MAPI works only with filenames, and other strings passed to it, in the Active Directory Service Interfaces (ANSI) character set.</span></span> <span data-ttu-id="f18a7-120">使用文件名的原始设备制造商 (OEM) 字符集中的客户端应用程序必须将其转换为 ANSI 调用 MAPI 之前。</span><span class="sxs-lookup"><span data-stu-id="f18a7-120">Client applications that use filenames in an original equipment manufacturer (OEM) character set must convert them to ANSI before calling MAPI.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="f18a7-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="f18a7-121">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="f18a7-122">头文件</span><span class="sxs-lookup"><span data-stu-id="f18a7-122">Header files</span></span>

<span data-ttu-id="f18a7-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f18a7-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="f18a7-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="f18a7-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="f18a7-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="f18a7-125">Mapitags.h</span></span>
  
> <span data-ttu-id="f18a7-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="f18a7-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f18a7-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f18a7-127">See also</span></span>



[<span data-ttu-id="f18a7-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="f18a7-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="f18a7-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="f18a7-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="f18a7-130">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f18a7-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="f18a7-131">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="f18a7-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

