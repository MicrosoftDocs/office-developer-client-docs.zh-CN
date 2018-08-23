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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e09a1de5f85edd7e352a090c573fed9ca16f017f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565548"
---
# <a name="imapistatuschangepassword"></a><span data-ttu-id="1df0e-103">IMAPIStatus::ChangePassword</span><span class="sxs-lookup"><span data-stu-id="1df0e-103">IMAPIStatus::ChangePassword</span></span>

  
  
<span data-ttu-id="1df0e-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1df0e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1df0e-105">不显示用户界面中修改服务提供商的密码。</span><span class="sxs-lookup"><span data-stu-id="1df0e-105">Modifies a service provider's password without displaying a user interface.</span></span> <span data-ttu-id="1df0e-106">（可选） 在服务提供商实现的状态对象支持使用此方法。</span><span class="sxs-lookup"><span data-stu-id="1df0e-106">This method is optionally supported in status objects that service providers implement.</span></span>
  
```cpp
HRESULT ChangePassword(
  LPSTR lpOldPass,
  LPSTR lpNewPass,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="1df0e-107">参数</span><span class="sxs-lookup"><span data-stu-id="1df0e-107">Parameters</span></span>

 <span data-ttu-id="1df0e-108">_lpOldPass_</span><span class="sxs-lookup"><span data-stu-id="1df0e-108">_lpOldPass_</span></span>
  
> <span data-ttu-id="1df0e-109">[in]指向旧密码的指针。</span><span class="sxs-lookup"><span data-stu-id="1df0e-109">[in] A pointer to the old password.</span></span>
    
 <span data-ttu-id="1df0e-110">_lpNewPass_</span><span class="sxs-lookup"><span data-stu-id="1df0e-110">_lpNewPass_</span></span>
  
> <span data-ttu-id="1df0e-111">[in]一个指向新密码。</span><span class="sxs-lookup"><span data-stu-id="1df0e-111">[in] A pointer to the new password.</span></span>
    
 <span data-ttu-id="1df0e-112">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="1df0e-112">_ulFlags_</span></span>
  
> <span data-ttu-id="1df0e-113">[in]位掩码的标志的控制的密码的格式。</span><span class="sxs-lookup"><span data-stu-id="1df0e-113">[in] A bitmask of flags that controls the format of the passwords.</span></span> <span data-ttu-id="1df0e-114">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="1df0e-114">The following flag can be set:</span></span>
    
<span data-ttu-id="1df0e-115">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="1df0e-115">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="1df0e-116">密码是以 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="1df0e-116">The passwords are in Unicode format.</span></span> <span data-ttu-id="1df0e-117">如果未设置 MAPI_UNICODE 标志，密码为 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="1df0e-117">If the MAPI_UNICODE flag is not set, the passwords are in ANSI format.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="1df0e-118">返回值</span><span class="sxs-lookup"><span data-stu-id="1df0e-118">Return value</span></span>

<span data-ttu-id="1df0e-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="1df0e-119">S_OK</span></span> 
  
> <span data-ttu-id="1df0e-120">密码修改成功。</span><span class="sxs-lookup"><span data-stu-id="1df0e-120">The password modification was successful.</span></span>
    
<span data-ttu-id="1df0e-121">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="1df0e-121">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="1df0e-122">由_lpOldPass_指向旧密码无效。</span><span class="sxs-lookup"><span data-stu-id="1df0e-122">The old password pointed to by  _lpOldPass_ is invalid.</span></span> 
    
<span data-ttu-id="1df0e-123">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="1df0e-123">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="1df0e-124">状态对象不支持此操作，如缺少 STATUS_CHANGE_PASSWORD 标志状态对象的**PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) 属性中所示。</span><span class="sxs-lookup"><span data-stu-id="1df0e-124">The status object does not support this operation, as indicated by the absence of the STATUS_CHANGE_PASSWORD flag in the status object's **PR_RESOURCE_METHODS** ([PidTagResourceMethods](pidtagresourcemethods-canonical-property.md)) property.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="1df0e-125">注解</span><span class="sxs-lookup"><span data-stu-id="1df0e-125">Remarks</span></span>

<span data-ttu-id="1df0e-126">并非所有状态对象都支持**IMAPIStatus::ChangePassword**方法。</span><span class="sxs-lookup"><span data-stu-id="1df0e-126">Not all status objects support the **IMAPIStatus::ChangePassword** method.</span></span> <span data-ttu-id="1df0e-127">它只受服务提供商的要求客户端输入密码。</span><span class="sxs-lookup"><span data-stu-id="1df0e-127">It is supported only by service providers that require clients to enter a password.</span></span> <span data-ttu-id="1df0e-128">MAPI 实现的状态对象都未支持密码更改操作。</span><span class="sxs-lookup"><span data-stu-id="1df0e-128">None of the status objects that MAPI implements support the password change operation.</span></span> 
  
 <span data-ttu-id="1df0e-129">**ChangePassword**修改密码以编程方式，无需用户交互。</span><span class="sxs-lookup"><span data-stu-id="1df0e-129">**ChangePassword** modifies a password programmatically, without user interaction.</span></span> 
  
## <a name="notes-to-implementers"></a><span data-ttu-id="1df0e-130">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="1df0e-130">Notes to implementers</span></span>

<span data-ttu-id="1df0e-131">远程传输提供程序指定此处实现**ChangePassword** 。</span><span class="sxs-lookup"><span data-stu-id="1df0e-131">Remote transport providers implement **ChangePassword** as specified here.</span></span> <span data-ttu-id="1df0e-132">没有任何特殊的注意事项。</span><span class="sxs-lookup"><span data-stu-id="1df0e-132">There are no special considerations.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1df0e-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1df0e-133">See also</span></span>



[<span data-ttu-id="1df0e-134">PidTagResourceMethods 规范属性</span><span class="sxs-lookup"><span data-stu-id="1df0e-134">PidTagResourceMethods Canonical Property</span></span>](pidtagresourcemethods-canonical-property.md)
  
[<span data-ttu-id="1df0e-135">IMAPIStatus : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="1df0e-135">IMAPIStatus : IMAPIProp</span></span>](imapistatusimapiprop.md)

