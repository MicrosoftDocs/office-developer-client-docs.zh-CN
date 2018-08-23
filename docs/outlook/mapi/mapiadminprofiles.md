---
title: MAPIAdminProfiles
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPIAdminProfiles
api_type:
- HeaderDef
ms.assetid: 82a9e379-39e4-4257-8cba-a6758f431cdc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 843eed06f30dcca530cf4306c9e03bbffbb05af5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581284"
---
# <a name="mapiadminprofiles"></a><span data-ttu-id="c7b76-103">MAPIAdminProfiles</span><span class="sxs-lookup"><span data-stu-id="c7b76-103">MAPIAdminProfiles</span></span>

  
  
<span data-ttu-id="c7b76-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c7b76-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c7b76-105">创建一个配置文件管理对象。</span><span class="sxs-lookup"><span data-stu-id="c7b76-105">Creates a profile administration object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c7b76-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="c7b76-106">Header file:</span></span>  <br/> |<span data-ttu-id="c7b76-107">Mapix.h</span><span class="sxs-lookup"><span data-stu-id="c7b76-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="c7b76-108">通过实现：</span><span class="sxs-lookup"><span data-stu-id="c7b76-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="c7b76-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="c7b76-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="c7b76-110">调用：</span><span class="sxs-lookup"><span data-stu-id="c7b76-110">Called by:</span></span>  <br/> |<span data-ttu-id="c7b76-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="c7b76-111">Client applications</span></span>  <br/> |
   
```cpp
HRESULT MAPIAdminProfiles(
  ULONG ulFlags,
  LPPROFADMIN FAR * lppProfAdmin
);
```

## <a name="parameters"></a><span data-ttu-id="c7b76-112">参数</span><span class="sxs-lookup"><span data-stu-id="c7b76-112">Parameters</span></span>

 <span data-ttu-id="c7b76-113">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="c7b76-113">_ulFlags_</span></span>
  
> <span data-ttu-id="c7b76-114">[in]标志指示的服务项功能的选项的位掩码。</span><span class="sxs-lookup"><span data-stu-id="c7b76-114">[in] Bitmask of flags indicating options for the service entry function.</span></span> 
    
 <span data-ttu-id="c7b76-115">_lppProfAdmin_</span><span class="sxs-lookup"><span data-stu-id="c7b76-115">_lppProfAdmin_</span></span>
  
> <span data-ttu-id="c7b76-116">[输出]为指向新的配置文件管理对象的指针。</span><span class="sxs-lookup"><span data-stu-id="c7b76-116">[out] Pointer to a pointer to the new profile administration object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="c7b76-117">返回值</span><span class="sxs-lookup"><span data-stu-id="c7b76-117">Return value</span></span>

<span data-ttu-id="c7b76-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="c7b76-118">S_OK</span></span> 
  
> <span data-ttu-id="c7b76-119">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="c7b76-119">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="c7b76-120">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="c7b76-120">MFCMAPI reference</span></span>

<span data-ttu-id="c7b76-121">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="c7b76-121">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="c7b76-122">**文件**</span><span class="sxs-lookup"><span data-stu-id="c7b76-122">**File**</span></span>|<span data-ttu-id="c7b76-123">**函数**</span><span class="sxs-lookup"><span data-stu-id="c7b76-123">**Function**</span></span>|<span data-ttu-id="c7b76-124">**Comment**</span><span class="sxs-lookup"><span data-stu-id="c7b76-124">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c7b76-125">MAPIObjects.cpp</span><span class="sxs-lookup"><span data-stu-id="c7b76-125">MAPIObjects.cpp</span></span>  <br/> |<span data-ttu-id="c7b76-126">CMapiObjects::GetProfAdmin</span><span class="sxs-lookup"><span data-stu-id="c7b76-126">CMapiObjects::GetProfAdmin</span></span>  <br/> |<span data-ttu-id="c7b76-127">MFCMAPI 使用**MAPIAdminProfiles**方法来获取配置文件管理对象。</span><span class="sxs-lookup"><span data-stu-id="c7b76-127">MFCMAPI uses the **MAPIAdminProfiles** method to get the profile administration object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c7b76-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7b76-128">See also</span></span>



[<span data-ttu-id="c7b76-129">IProfAdmin::CreateProfile</span><span class="sxs-lookup"><span data-stu-id="c7b76-129">IProfAdmin::CreateProfile</span></span>](iprofadmin-createprofile.md)


[<span data-ttu-id="c7b76-130">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="c7b76-130">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

