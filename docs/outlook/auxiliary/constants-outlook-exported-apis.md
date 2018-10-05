---
title: （Outlook 导出的 Api） 的常量
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 7590a30e-3fd8-7ae3-f077-c80f6cc21d7b
description: 本主题包含常量定义的 Outlook 导出 Api。
ms.openlocfilehash: 65181932b858da1b32c3fbe5fd0bd7e92ca8dc9f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386073"
---
# <a name="constants-outlook-exported-apis"></a><span data-ttu-id="9c8e6-103">（Outlook 导出的 Api） 的常量</span><span class="sxs-lookup"><span data-stu-id="9c8e6-103">Constants (Outlook exported APIs)</span></span>

<span data-ttu-id="9c8e6-104">本主题包含常量定义的 Outlook 导出 Api。</span><span class="sxs-lookup"><span data-stu-id="9c8e6-104">This topic contains constant definitions for APIs that Outlook exports.</span></span>
  
## <a name="definitions-for-time-zone-support"></a><span data-ttu-id="9c8e6-105">定义时区的支持</span><span class="sxs-lookup"><span data-stu-id="9c8e6-105">Definitions for Time Zone support</span></span>

```cpp
const ULONG TZ_MAX_RULES                    = 0x00000001;  
const BYTE  TZ_BIN_VERSION_MAJOR            = 0x02;  
const BYTE  TZ_BIN_VERSION_MINOR            = 0x01; 
const WORD  TZRULE_FLAG_RECUR_CURRENT_TZREG = 0x0001; 
const WORD  TZRULE_FLAG_EFFECTIVE_TZREG     = 0x0002; 
const WORD  TZDEFINITION_FLAG_VALID_KEYNAME = 0x0002;
```

## <a name="definitions-for-category-support"></a><span data-ttu-id="9c8e6-106">为类别定义支持</span><span class="sxs-lookup"><span data-stu-id="9c8e6-106">Definitions for Category support</span></span>

|<span data-ttu-id="9c8e6-107">**常量**</span><span class="sxs-lookup"><span data-stu-id="9c8e6-107">**Constant**</span></span>|<span data-ttu-id="9c8e6-108">**定义**</span><span class="sxs-lookup"><span data-stu-id="9c8e6-108">**Definition**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9c8e6-109">PCAFSIF_MSGEID_IS_SEARCH_KEY</span><span class="sxs-lookup"><span data-stu-id="9c8e6-109">PCAFSIF_MSGEID_IS_SEARCH_KEY</span></span>  <br/> |<span data-ttu-id="9c8e6-110">0x00000001</span><span class="sxs-lookup"><span data-stu-id="9c8e6-110">0x00000001</span></span>  <br/> |
   
## <a name="miscellaneous-dispatch-identifiers"></a><span data-ttu-id="9c8e6-111">Miscellaneous 调度标识符</span><span class="sxs-lookup"><span data-stu-id="9c8e6-111">Miscellaneous dispatch identifiers</span></span>

<span data-ttu-id="9c8e6-112">Outlook 公开以下调度标识符 (dispid)，以便开发人员可以使用[idispatch:: Invoke](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke)访问的相应属性或方法，或收听对应的事件。</span><span class="sxs-lookup"><span data-stu-id="9c8e6-112">Outlook exposes the following dispatch identifiers (dispids) so that developers can use [IDispatch::Invoke](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nf-oaidl-idispatch-invoke) to access the corresponding property or method, or listen to the corresponding event.</span></span> 
  
|<span data-ttu-id="9c8e6-113">**关联的常量**</span><span class="sxs-lookup"><span data-stu-id="9c8e6-113">**Associated constant**</span></span>|<span data-ttu-id="9c8e6-114">**Dispid 值**</span><span class="sxs-lookup"><span data-stu-id="9c8e6-114">**Dispid value**</span></span>|<span data-ttu-id="9c8e6-115">**说明**</span><span class="sxs-lookup"><span data-stu-id="9c8e6-115">**Description**</span></span>|<span data-ttu-id="9c8e6-116">**适用的接口**</span><span class="sxs-lookup"><span data-stu-id="9c8e6-116">**Applicable interface**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9c8e6-117">**dispidFDirty**</span><span class="sxs-lookup"><span data-stu-id="9c8e6-117">**dispidFDirty**</span></span> <br/> |<span data-ttu-id="9c8e6-118">0xF024</span><span class="sxs-lookup"><span data-stu-id="9c8e6-118">0xF024</span></span>  <br/> |<span data-ttu-id="9c8e6-119">用于调用以验证项目是否已修改但未保存项目上的相应属性。</span><span class="sxs-lookup"><span data-stu-id="9c8e6-119">Used to invoke the corresponding property on an item to verify whether the item has been modified but has not been saved.</span></span>  <br/> |<span data-ttu-id="9c8e6-120">项目级对象</span><span class="sxs-lookup"><span data-stu-id="9c8e6-120">Item-level objects</span></span>  <br/> |
|<span data-ttu-id="9c8e6-121">**dispidShowSenderPhoto**</span><span class="sxs-lookup"><span data-stu-id="9c8e6-121">**dispidShowSenderPhoto**</span></span> <br/> |<span data-ttu-id="9c8e6-122">0xF0D0</span><span class="sxs-lookup"><span data-stu-id="9c8e6-122">0xF0D0</span></span>  <br/> |<span data-ttu-id="9c8e6-123">用于调用以指定是否显示联系人的图片，基于给定的参数的资源管理器或检查器的对应方法。</span><span class="sxs-lookup"><span data-stu-id="9c8e6-123">Used to invoke the corresponding method on the explorer or inspector to specify whether to display a contact's picture, based on a given argument.</span></span>  <br/> |<span data-ttu-id="9c8e6-124">资源管理器或检查器</span><span class="sxs-lookup"><span data-stu-id="9c8e6-124">Explorer or inspector</span></span>  <br/> |
|<span data-ttu-id="9c8e6-125">**dispidBeforePrint**</span><span class="sxs-lookup"><span data-stu-id="9c8e6-125">**dispidBeforePrint**</span></span> <br/> |<span data-ttu-id="9c8e6-126">0xFC8E</span><span class="sxs-lookup"><span data-stu-id="9c8e6-126">0xFC8E</span></span>  <br/> |<span data-ttu-id="9c8e6-127">用于处理来自**idispatch:: Invoke**函数打印操作前触发的事件。</span><span class="sxs-lookup"><span data-stu-id="9c8e6-127">Used to handle the event from the **IDispatch::Invoke** function that fires before a printing operation.</span></span>  <br/> |<span data-ttu-id="9c8e6-128">应用程序</span><span class="sxs-lookup"><span data-stu-id="9c8e6-128">Application</span></span>  <br/> |
|<span data-ttu-id="9c8e6-129">**dispidEventReadComplete**</span><span class="sxs-lookup"><span data-stu-id="9c8e6-129">**dispidEventReadComplete**</span></span> <br/> |<span data-ttu-id="9c8e6-130">0xFC8F</span><span class="sxs-lookup"><span data-stu-id="9c8e6-130">0xFC8F</span></span>  <br/> |<span data-ttu-id="9c8e6-131">用于处理从**idispatch:: Invoke**函数 Outlook 已完成读取项目的属性时触发的事件。</span><span class="sxs-lookup"><span data-stu-id="9c8e6-131">Used to handle the event from the **IDispatch::Invoke** function that fires when Outlook has completed reading the properties of the item.</span></span>  <br/> |<span data-ttu-id="9c8e6-132">项目级对象</span><span class="sxs-lookup"><span data-stu-id="9c8e6-132">Item-level objects</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="9c8e6-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c8e6-133">See also</span></span>

- [<span data-ttu-id="9c8e6-134">Outlook 导出的 API</span><span class="sxs-lookup"><span data-stu-id="9c8e6-134">Outlook exported APIs</span></span>](outlook-exported-apis.md)
- [<span data-ttu-id="9c8e6-135">关于 Outlook 导出的 API</span><span class="sxs-lookup"><span data-stu-id="9c8e6-135">About APIs exported by Outlook</span></span>](about-apis-exported-by-outlook.md)
- [<span data-ttu-id="9c8e6-136">确定某个 Outlook 项目是否已修改但未保存（Outlook 辅助参考）</span><span class="sxs-lookup"><span data-stu-id="9c8e6-136">Determine whether an Outlook item has been modified but not saved (Outlook Auxiliary Reference)</span></span>](how-to-determine-if-outlook-item-has-been-modified-but-not-saved.md)
- [<span data-ttu-id="9c8e6-137">指定是否要在 Outlook（Outlook 辅助参考）中显示联系人的图片</span><span class="sxs-lookup"><span data-stu-id="9c8e6-137">Specify whether to display a contact's picture in Outlook (Outlook Auxiliary Reference)</span></span>](https://msdn.microsoft.com/library/office/gg262879.aspx)
- [<span data-ttu-id="9c8e6-138">可用的事件和其 dispid （Outlook 导出的 Api）</span><span class="sxs-lookup"><span data-stu-id="9c8e6-138">Available events and their dispids (Outlook exported APIs)</span></span>](available-events-and-their-dispids-outlook-exported-apis.md)

