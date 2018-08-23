---
title: IProfAdminSetDefaultProfile
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin.SetDefaultProfile
api_type:
- COM
ms.assetid: 58f50535-b0ed-4097-bda8-fd3ccc2d4b49
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: af695d55cdd5f8d7e24d7e60e6eebaf03868b03f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22587703"
---
# <a name="iprofadminsetdefaultprofile"></a><span data-ttu-id="81c4e-103">IProfAdmin::SetDefaultProfile</span><span class="sxs-lookup"><span data-stu-id="81c4e-103">IProfAdmin::SetDefaultProfile</span></span>

  
  
<span data-ttu-id="81c4e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="81c4e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="81c4e-105">设置或清除客户端的默认配置文件。</span><span class="sxs-lookup"><span data-stu-id="81c4e-105">Sets or clears a client's default profile.</span></span>
  
```cpp
HRESULT SetDefaultProfile(
  LPSTR lpszProfileName,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="81c4e-106">参数</span><span class="sxs-lookup"><span data-stu-id="81c4e-106">Parameters</span></span>

 <span data-ttu-id="81c4e-107">_lpszProfileName_</span><span class="sxs-lookup"><span data-stu-id="81c4e-107">_lpszProfileName_</span></span>
  
> <span data-ttu-id="81c4e-108">[in]一个指向将成为默认值，则为 NULL 的配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="81c4e-108">[in] A pointer to the name of the profile that will become the default, or NULL.</span></span> <span data-ttu-id="81c4e-109">将_lpszProfileName_设置为 NULL 指示**SetDefaultProfile**应删除现有的默认配置文件，而客户端无默认值。</span><span class="sxs-lookup"><span data-stu-id="81c4e-109">Setting  _lpszProfileName_ to NULL indicates that **SetDefaultProfile** should remove the existing default profile, leaving the client without a default.</span></span> 
    
 <span data-ttu-id="81c4e-110">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="81c4e-110">_ulFlags_</span></span>
  
> <span data-ttu-id="81c4e-111">[in]由_lpszProfileName_指向控制字符串的类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="81c4e-111">[in] A bitmask of flags that controls the type of the string pointed to by  _lpszProfileName_.</span></span> <span data-ttu-id="81c4e-112">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="81c4e-112">The following flag can be set:</span></span>
    
<span data-ttu-id="81c4e-113">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="81c4e-113">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="81c4e-114">配置文件名称为 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="81c4e-114">The profile name is in Unicode format.</span></span> <span data-ttu-id="81c4e-115">如果未设置 MAPI_UNICODE 标志，是 ANSI 格式的配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="81c4e-115">If the MAPI_UNICODE flag is not set, the profile name is in ANSI format.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="81c4e-116">返回值</span><span class="sxs-lookup"><span data-stu-id="81c4e-116">Return value</span></span>

<span data-ttu-id="81c4e-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="81c4e-117">S_OK</span></span> 
  
> <span data-ttu-id="81c4e-118">默认配置文件成功建立或删除。</span><span class="sxs-lookup"><span data-stu-id="81c4e-118">A default profile was successfully established or removed.</span></span>
    
<span data-ttu-id="81c4e-119">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="81c4e-119">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="81c4e-120">指定的配置文件不存在。</span><span class="sxs-lookup"><span data-stu-id="81c4e-120">The specified profile does not exist.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="81c4e-121">注解</span><span class="sxs-lookup"><span data-stu-id="81c4e-121">Remarks</span></span>

<span data-ttu-id="81c4e-122">**IProfAdmin::SetDefaultProfile**方法建立为客户端的默认配置文件的特定配置文件，或清除当前的默认配置文件。</span><span class="sxs-lookup"><span data-stu-id="81c4e-122">The **IProfAdmin::SetDefaultProfile** method either establishes a particular profile as the client's default profile or clears the current default profile.</span></span> <span data-ttu-id="81c4e-123">默认配置文件是客户端开始 MAPI 会话时，系统将自动使用的配置文件。</span><span class="sxs-lookup"><span data-stu-id="81c4e-123">The default profile is the profile that is automatically used whenever the client begins a MAPI session.</span></span> <span data-ttu-id="81c4e-124">**SetDefaultProfile**还将该新的默认配置文件的**PR_DEFAULT_PROFILE** ([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md)) 属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="81c4e-124">**SetDefaultProfile** also sets the new default profile's **PR_DEFAULT_PROFILE** ([PidTagDefaultProfile](pidtagdefaultprofile-canonical-property.md)) property to TRUE.</span></span>
  
## <a name="notes-to-callers"></a><span data-ttu-id="81c4e-125">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="81c4e-125">Notes to callers</span></span>

<span data-ttu-id="81c4e-126">要使用的默认配置文件启动会话，传递给[MAPILogonEx](mapilogonex.md)函数 MAPI_USE_DEFAULT 标志。</span><span class="sxs-lookup"><span data-stu-id="81c4e-126">To start a session with the default profile, pass the MAPI_USE_DEFAULT flag to the [MAPILogonEx](mapilogonex.md) function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="81c4e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81c4e-127">See also</span></span>



[<span data-ttu-id="81c4e-128">IProfAdmin::GetProfileTable</span><span class="sxs-lookup"><span data-stu-id="81c4e-128">IProfAdmin::GetProfileTable</span></span>](iprofadmin-getprofiletable.md)
  
[<span data-ttu-id="81c4e-129">MAPILogonEx</span><span class="sxs-lookup"><span data-stu-id="81c4e-129">MAPILogonEx</span></span>](mapilogonex.md)
  
[<span data-ttu-id="81c4e-130">PidTagDefaultProfile 规范属性</span><span class="sxs-lookup"><span data-stu-id="81c4e-130">PidTagDefaultProfile Canonical Property</span></span>](pidtagdefaultprofile-canonical-property.md)
  
[<span data-ttu-id="81c4e-131">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="81c4e-131">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)

