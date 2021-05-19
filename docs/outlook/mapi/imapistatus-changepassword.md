---
title: IMAPIStatusChangePassword
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIStatus.ChangePassword
api_type:
- COM
ms.assetid: 0cd1026a-342d-4d05-91ed-d3decced5bf3
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2c824b6b994bfb31b5e6ac7fed0eeae88c47cdba
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410355"
---
# <a name="imapistatuschangepassword"></a><span data-ttu-id="257be-103">IMAPIStatus::ChangePassword</span><span class="sxs-lookup"><span data-stu-id="257be-103">IMAPIStatus::ChangePassword</span></span>

  
  
<span data-ttu-id="257be-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="257be-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="257be-105">修改服务提供商的密码，而不显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="257be-105">Modifies a service provider's password without displaying a user interface.</span></span> <span data-ttu-id="257be-106">此方法在服务提供商实现的状态对象中受支持（ 可选）。</span><span class="sxs-lookup"><span data-stu-id="257be-106">This method is optionally supported in status objects that service providers implement.</span></span>
  
```cpp
HRESULT ChangePassword(
  LPSTR lpOldPass,
  LPSTR lpNewPass,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="257be-107">参数</span><span class="sxs-lookup"><span data-stu-id="257be-107">Parameters</span></span>

 <span data-ttu-id="257be-108">_lpOldPass_</span><span class="sxs-lookup"><span data-stu-id="257be-108">_lpOldPass_</span></span>
  
> <span data-ttu-id="257be-109">[in]指向旧密码的指针。</span><span class="sxs-lookup"><span data-stu-id="257be-109">[in] A pointer to the old password.</span></span>
    
 <span data-ttu-id="257be-110">_lpNewPass_</span><span class="sxs-lookup"><span data-stu-id="257be-110">_lpNewPass_</span></span>
  
> <span data-ttu-id="257be-111">[in]指向新密码的指针。</span><span class="sxs-lookup"><span data-stu-id="257be-111">[in] A pointer to the new password.</span></span>
    
 <span data-ttu-id="257be-112">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="257be-112">_ulFlags_</span></span>
  
> <span data-ttu-id="257be-113">[in]控制密码格式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="257be-113">[in] A bitmask of flags that controls the format of the passwords.</span></span> <span data-ttu-id="257be-114">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="257be-114">The following flag can be set:</span></span>
    
<span data-ttu-id="257be-115">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="257be-115">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="257be-116">密码采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="257be-116">The passwords are in Unicode format.</span></span> <span data-ttu-id="257be-117">如果未MAPI_UNICODE，则密码采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="257be-117">If the MAPI_UNICODE flag is not set, the passwords are in ANSI format.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="257be-118">返回值</span><span class="sxs-lookup"><span data-stu-id="257be-118">Return value</span></span>

<span data-ttu-id="257be-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="257be-119">S_OK</span></span> 
  
> <span data-ttu-id="257be-120">密码修改成功。</span><span class="sxs-lookup"><span data-stu-id="257be-120">The password modification was successful.</span></span>
    
<span data-ttu-id="257be-121">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="257be-121">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="257be-122">_lpOldPass_ 指向的旧密码无效。</span><span class="sxs-lookup"><span data-stu-id="257be-122">The old password pointed to by  _lpOldPass_ is invalid.</span></span> 
    
<span data-ttu-id="257be-123">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="257be-123">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="257be-124">status 对象不支持此操作，如状态对象的 PR_RESOURCE_METHODS ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)属性中缺少STATUS_CHANGE_PASSWORD 标志) 。</span><span class="sxs-lookup"><span data-stu-id="257be-124">The status object does not support this operation, as indicated by the absence of the STATUS_CHANGE_PASSWORD flag in the status object's **PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) property.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="257be-125">备注</span><span class="sxs-lookup"><span data-stu-id="257be-125">Remarks</span></span>

<span data-ttu-id="257be-126">并非所有状态对象都支持 **IMAPIStatus：：ChangePassword** 方法。</span><span class="sxs-lookup"><span data-stu-id="257be-126">Not all status objects support the **IMAPIStatus::ChangePassword** method.</span></span> <span data-ttu-id="257be-127">它仅受要求客户端输入密码的服务提供商支持。</span><span class="sxs-lookup"><span data-stu-id="257be-127">It is supported only by service providers that require clients to enter a password.</span></span> <span data-ttu-id="257be-128">MAPI 实现的所有状态对象都不支持密码更改操作。</span><span class="sxs-lookup"><span data-stu-id="257be-128">None of the status objects that MAPI implements support the password change operation.</span></span> 
  
 <span data-ttu-id="257be-129">**ChangePassword** 以编程方式修改密码，无需用户交互。</span><span class="sxs-lookup"><span data-stu-id="257be-129">**ChangePassword** modifies a password programmatically, without user interaction.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="257be-130">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="257be-130">Notes to implementers</span></span>

<span data-ttu-id="257be-131">远程传输提供程序实现 **此处指定的 ChangePassword。**</span><span class="sxs-lookup"><span data-stu-id="257be-131">Remote transport providers implement **ChangePassword** as specified here.</span></span> <span data-ttu-id="257be-132">没有特别注意事项。</span><span class="sxs-lookup"><span data-stu-id="257be-132">There are no special considerations.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="257be-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="257be-133">See also</span></span>



[<span data-ttu-id="257be-134">PidTagResourceMethods 规范属性</span><span class="sxs-lookup"><span data-stu-id="257be-134">PidTagResourceMethods Canonical Property</span></span>](pidtagresourcemethods-canonical-property.md)
  
[<span data-ttu-id="257be-135">IMAPIStatus : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="257be-135">IMAPIStatus : IMAPIProp</span></span>](imapistatusimapiprop.md)

