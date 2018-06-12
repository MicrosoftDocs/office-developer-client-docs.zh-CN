---
title: PidTagAddressBookChooseDirectoryAutomatically 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: cecd0679-4bc2-4399-8f89-a4e17bb909a0
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 48dfced07a8fd78a1af22679759effbd3c6da343
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777302"
---
# <a name="pidtagaddressbookchoosedirectoryautomatically-canonical-property"></a><span data-ttu-id="59ff1-103">PidTagAddressBookChooseDirectoryAutomatically 规范属性</span><span class="sxs-lookup"><span data-stu-id="59ff1-103">PidTagAddressBookChooseDirectoryAutomatically Canonical Property</span></span>

  
  
<span data-ttu-id="59ff1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="59ff1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="59ff1-105">启用 Microsoft Outlook 2010 和 Microsoft Outlook 2013，选择最合适的全局地址列表 (GAL) 或联系人的当前邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="59ff1-105">Enables Microsoft Outlook 2010 and Microsoft Outlook 2013 to choose the most appropriate global address list (GAL) or contact folder for the current mailbox.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="59ff1-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="59ff1-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="59ff1-107">PR_AB_CHOOSE_DIRECTORY_AUTOMATICALLY</span><span class="sxs-lookup"><span data-stu-id="59ff1-107">PR_AB_CHOOSE_DIRECTORY_AUTOMATICALLY</span></span>  <br/> |
|<span data-ttu-id="59ff1-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="59ff1-108">Identifier:</span></span>  <br/> |<span data-ttu-id="59ff1-109">0x3D1C000B</span><span class="sxs-lookup"><span data-stu-id="59ff1-109">0x3D1C000B</span></span>  <br/> |
|<span data-ttu-id="59ff1-110">属性类型</span><span class="sxs-lookup"><span data-stu-id="59ff1-110">Property type:</span></span>  <br/> |<span data-ttu-id="59ff1-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="59ff1-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="59ff1-112">区域：</span><span class="sxs-lookup"><span data-stu-id="59ff1-112">Area:</span></span>  <br/> |<span data-ttu-id="59ff1-113">通讯簿</span><span class="sxs-lookup"><span data-stu-id="59ff1-113">Address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="59ff1-114">备注</span><span class="sxs-lookup"><span data-stu-id="59ff1-114">Remarks</span></span>

<span data-ttu-id="59ff1-115">此属性对应于通讯簿选项对话框中的**自动选择**设置。</span><span class="sxs-lookup"><span data-stu-id="59ff1-115">This property corresponds to the **Choose automatically** setting in the Address Book Options dialog.</span></span> <span data-ttu-id="59ff1-116">当此属性存在 IID_CAPONE_PROF 配置文件一节，并设置为**true**，通讯簿对话框不再默认为[SetDefaultDir](iaddrbook-setdefaultdir.md)方法中，指定的容器，但选择通讯簿的 Outlook 2010 或 Outlook 2013考虑适用于在其中显示对话框中的上下文。</span><span class="sxs-lookup"><span data-stu-id="59ff1-116">When this property exists in the IID_CAPONE_PROF profile section and is set to **true**, the Address Book dialog no longer defaults to the container specified by the [SetDefaultDir](iaddrbook-setdefaultdir.md) method, but chooses an address book that Outlook 2010 or Outlook 2013 considers appropriate for the context in which the dialog was displayed.</span></span> <span data-ttu-id="59ff1-117">请注意，这可能会导致不好的体验的第三方通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="59ff1-117">Note that this may result in a poor experience for third-party address book providers.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="59ff1-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="59ff1-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="59ff1-119">头文件</span><span class="sxs-lookup"><span data-stu-id="59ff1-119">Header files</span></span>

<span data-ttu-id="59ff1-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="59ff1-120">Mapitags.h</span></span>
  
> <span data-ttu-id="59ff1-121">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="59ff1-121">Contains definitions of properties listed as associated properties.</span></span>
    
<span data-ttu-id="59ff1-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="59ff1-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="59ff1-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="59ff1-123">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="59ff1-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59ff1-124">See also</span></span>



[<span data-ttu-id="59ff1-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="59ff1-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="59ff1-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="59ff1-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="59ff1-127">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="59ff1-127">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="59ff1-128">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="59ff1-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="59ff1-129">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="59ff1-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

