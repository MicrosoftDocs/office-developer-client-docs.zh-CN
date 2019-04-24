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
ms.openlocfilehash: e5043a614ccd94994fe86838f15aa1a43f22733e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357328"
---
# <a name="mapiadminprofiles"></a><span data-ttu-id="95c0e-103">MAPIAdminProfiles</span><span class="sxs-lookup"><span data-stu-id="95c0e-103">MAPIAdminProfiles</span></span>

  
  
<span data-ttu-id="95c0e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="95c0e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="95c0e-105">创建配置文件管理对象。</span><span class="sxs-lookup"><span data-stu-id="95c0e-105">Creates a profile administration object.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="95c0e-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="95c0e-106">Header file:</span></span>  <br/> |<span data-ttu-id="95c0e-107">Mapix</span><span class="sxs-lookup"><span data-stu-id="95c0e-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="95c0e-108">实现者：</span><span class="sxs-lookup"><span data-stu-id="95c0e-108">Implemented by:</span></span>  <br/> |<span data-ttu-id="95c0e-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="95c0e-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="95c0e-110">调用者：</span><span class="sxs-lookup"><span data-stu-id="95c0e-110">Called by:</span></span>  <br/> |<span data-ttu-id="95c0e-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="95c0e-111">Client applications</span></span>  <br/> |
   
```cpp
HRESULT MAPIAdminProfiles(
  ULONG ulFlags,
  LPPROFADMIN FAR * lppProfAdmin
);
```

## <a name="parameters"></a><span data-ttu-id="95c0e-112">参数</span><span class="sxs-lookup"><span data-stu-id="95c0e-112">Parameters</span></span>

 <span data-ttu-id="95c0e-113">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="95c0e-113">_ulFlags_</span></span>
  
> <span data-ttu-id="95c0e-114">实时指示服务输入函数选项的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="95c0e-114">[in] Bitmask of flags indicating options for the service entry function.</span></span> 
    
 <span data-ttu-id="95c0e-115">_lppProfAdmin_</span><span class="sxs-lookup"><span data-stu-id="95c0e-115">_lppProfAdmin_</span></span>
  
> <span data-ttu-id="95c0e-116">排除指向新的配置文件管理对象的指针的指针。</span><span class="sxs-lookup"><span data-stu-id="95c0e-116">[out] Pointer to a pointer to the new profile administration object.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="95c0e-117">返回值</span><span class="sxs-lookup"><span data-stu-id="95c0e-117">Return value</span></span>

<span data-ttu-id="95c0e-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="95c0e-118">S_OK</span></span> 
  
> <span data-ttu-id="95c0e-119">调用成功, 并返回了所需的值或值。</span><span class="sxs-lookup"><span data-stu-id="95c0e-119">The call succeeded and has returned the expected value or values.</span></span>
    
## <a name="mfcmapi-reference"></a><span data-ttu-id="95c0e-120">MFCMAPI 引用</span><span class="sxs-lookup"><span data-stu-id="95c0e-120">MFCMAPI reference</span></span>

<span data-ttu-id="95c0e-121">有关 MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="95c0e-121">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="95c0e-122">**文件**</span><span class="sxs-lookup"><span data-stu-id="95c0e-122">**File**</span></span>|<span data-ttu-id="95c0e-123">**函数**</span><span class="sxs-lookup"><span data-stu-id="95c0e-123">**Function**</span></span>|<span data-ttu-id="95c0e-124">**备注**</span><span class="sxs-lookup"><span data-stu-id="95c0e-124">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="95c0e-125">MAPIObjects</span><span class="sxs-lookup"><span data-stu-id="95c0e-125">MAPIObjects.cpp</span></span>  <br/> |<span data-ttu-id="95c0e-126">CMapiObjects:: GetProfAdmin</span><span class="sxs-lookup"><span data-stu-id="95c0e-126">CMapiObjects::GetProfAdmin</span></span>  <br/> |<span data-ttu-id="95c0e-127">MFCMAPI 使用**MAPIAdminProfiles**方法获取配置文件管理对象。</span><span class="sxs-lookup"><span data-stu-id="95c0e-127">MFCMAPI uses the **MAPIAdminProfiles** method to get the profile administration object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="95c0e-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95c0e-128">See also</span></span>



[<span data-ttu-id="95c0e-129">IProfAdmin::CreateProfile</span><span class="sxs-lookup"><span data-stu-id="95c0e-129">IProfAdmin::CreateProfile</span></span>](iprofadmin-createprofile.md)


[<span data-ttu-id="95c0e-130">MFCMAPI 代码示例</span><span class="sxs-lookup"><span data-stu-id="95c0e-130">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

