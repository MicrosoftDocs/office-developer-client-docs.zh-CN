---
title: PidTagAddressBookChooseDirectoryAutomatically 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: cecd0679-4bc2-4399-8f89-a4e17bb909a0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 41fdaf333084b7d567f4e67ae9fd2638a1731349
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359785"
---
# <a name="pidtagaddressbookchoosedirectoryautomatically-canonical-property"></a><span data-ttu-id="28948-103">PidTagAddressBookChooseDirectoryAutomatically 规范属性</span><span class="sxs-lookup"><span data-stu-id="28948-103">PidTagAddressBookChooseDirectoryAutomatically Canonical Property</span></span>

  
  
<span data-ttu-id="28948-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="28948-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="28948-105">启用 microsoft outlook 2010 和 microsoft outlook 2013 以选择最适合的全局地址列表 (GAL) 或当前邮箱的联系人文件夹。</span><span class="sxs-lookup"><span data-stu-id="28948-105">Enables Microsoft Outlook 2010 and Microsoft Outlook 2013 to choose the most appropriate global address list (GAL) or contact folder for the current mailbox.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="28948-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="28948-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="28948-107">PR_AB_CHOOSE_DIRECTORY_AUTOMATICALLY</span><span class="sxs-lookup"><span data-stu-id="28948-107">PR_AB_CHOOSE_DIRECTORY_AUTOMATICALLY</span></span>  <br/> |
|<span data-ttu-id="28948-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="28948-108">Identifier:</span></span>  <br/> |<span data-ttu-id="28948-109">0x3D1C000B</span><span class="sxs-lookup"><span data-stu-id="28948-109">0x3D1C000B</span></span>  <br/> |
|<span data-ttu-id="28948-110">属性类型</span><span class="sxs-lookup"><span data-stu-id="28948-110">Property type:</span></span>  <br/> |<span data-ttu-id="28948-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="28948-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="28948-112">区域：</span><span class="sxs-lookup"><span data-stu-id="28948-112">Area:</span></span>  <br/> |<span data-ttu-id="28948-113">通讯簿</span><span class="sxs-lookup"><span data-stu-id="28948-113">Address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="28948-114">注解</span><span class="sxs-lookup"><span data-stu-id="28948-114">Remarks</span></span>

<span data-ttu-id="28948-115">此属性对应于 "通讯簿选项" 对话框中的 "**自动选择**" 设置。</span><span class="sxs-lookup"><span data-stu-id="28948-115">This property corresponds to the **Choose automatically** setting in the Address Book Options dialog.</span></span> <span data-ttu-id="28948-116">当 IID_CAPONE_PROF 配置文件部分中存在此属性并将其设置为**true**时, 通讯簿对话框不再默认为[SetDefaultDir](iaddrbook-setdefaultdir.md)方法指定的容器, 而是选择 outlook 2010 或 outlook 2013 的通讯簿。考虑适合显示对话框的上下文。</span><span class="sxs-lookup"><span data-stu-id="28948-116">When this property exists in the IID_CAPONE_PROF profile section and is set to **true**, the Address Book dialog no longer defaults to the container specified by the [SetDefaultDir](iaddrbook-setdefaultdir.md) method, but chooses an address book that Outlook 2010 or Outlook 2013 considers appropriate for the context in which the dialog was displayed.</span></span> <span data-ttu-id="28948-117">请注意, 这可能会导致第三方通讯簿提供程序的体验不佳。</span><span class="sxs-lookup"><span data-stu-id="28948-117">Note that this may result in a poor experience for third-party address book providers.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="28948-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="28948-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="28948-119">头文件</span><span class="sxs-lookup"><span data-stu-id="28948-119">Header files</span></span>

<span data-ttu-id="28948-120">Mapitags</span><span class="sxs-lookup"><span data-stu-id="28948-120">Mapitags.h</span></span>
  
> <span data-ttu-id="28948-121">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="28948-121">Contains definitions of properties listed as associated properties.</span></span>
    
<span data-ttu-id="28948-122">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="28948-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="28948-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="28948-123">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="28948-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28948-124">See also</span></span>



[<span data-ttu-id="28948-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="28948-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="28948-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="28948-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="28948-127">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="28948-127">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="28948-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="28948-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="28948-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="28948-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

