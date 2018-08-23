---
title: IProfAdminChangeProfilePassword
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin.ChangeProfilePassword
api_type:
- COM
ms.assetid: a41f707a-5c84-49aa-aeb6-469b2600e181
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 41066d4418760a676fbc02241bfc12d83275da9d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22572996"
---
# <a name="iprofadminchangeprofilepassword"></a><span data-ttu-id="65049-103">IProfAdmin::ChangeProfilePassword</span><span class="sxs-lookup"><span data-stu-id="65049-103">IProfAdmin::ChangeProfilePassword</span></span>

  
  
<span data-ttu-id="65049-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="65049-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="65049-105">已弃用。</span><span class="sxs-lookup"><span data-stu-id="65049-105">Deprecated.</span></span> <span data-ttu-id="65049-106">更改配置文件的密码。</span><span class="sxs-lookup"><span data-stu-id="65049-106">Changes the password for a profile.</span></span>
  
```cpp
HRESULT ChangeProfilePassword(
  LPSTR lpszProfileName,
  LPSTR lpszOldPassword,
  LPSTR lpszNewPassword,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="65049-107">参数</span><span class="sxs-lookup"><span data-stu-id="65049-107">Parameters</span></span>

 <span data-ttu-id="65049-108">_lpszProfileName_</span><span class="sxs-lookup"><span data-stu-id="65049-108">_lpszProfileName_</span></span>
  
> <span data-ttu-id="65049-109">[in]一个指向相关联的密码更改配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="65049-109">[in] A pointer to the name of the profile associated with the password to be changed.</span></span>
    
 <span data-ttu-id="65049-110">_lpszOldPassword_</span><span class="sxs-lookup"><span data-stu-id="65049-110">_lpszOldPassword_</span></span>
  
> <span data-ttu-id="65049-111">[in]一个指向当前密码。</span><span class="sxs-lookup"><span data-stu-id="65049-111">[in] A pointer to the current password.</span></span>
    
 <span data-ttu-id="65049-112">_lpszNewPassword_</span><span class="sxs-lookup"><span data-stu-id="65049-112">_lpszNewPassword_</span></span>
  
> <span data-ttu-id="65049-113">[in]一个指向新密码。</span><span class="sxs-lookup"><span data-stu-id="65049-113">[in] A pointer to the new password.</span></span>
    
 <span data-ttu-id="65049-114">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="65049-114">_ulFlags_</span></span>
  
> <span data-ttu-id="65049-115">[in]位掩码的标志的控制传入的字符串的类型。</span><span class="sxs-lookup"><span data-stu-id="65049-115">[in] A bitmask of flags that controls the type of the passed-in strings.</span></span> <span data-ttu-id="65049-116">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="65049-116">The following flag can be set:</span></span>
    
<span data-ttu-id="65049-117">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="65049-117">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="65049-118">配置文件的名称和密码的 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="65049-118">The profile name and passwords are in Unicode format.</span></span> <span data-ttu-id="65049-119">如果未设置 MAPI_UNICODE 标志，这些字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="65049-119">If the MAPI_UNICODE flag is not set, these strings are in ANSI format.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="65049-120">返回值</span><span class="sxs-lookup"><span data-stu-id="65049-120">Return value</span></span>

<span data-ttu-id="65049-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="65049-121">S_OK</span></span> 
  
> <span data-ttu-id="65049-122">如果调用此方法，则它将返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="65049-122">If this method is called, it will return S_OK.</span></span> <span data-ttu-id="65049-123">但是，不会执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="65049-123">However, no action will be taken.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="65049-124">注解</span><span class="sxs-lookup"><span data-stu-id="65049-124">Remarks</span></span>

<span data-ttu-id="65049-125">不要使用此方法。</span><span class="sxs-lookup"><span data-stu-id="65049-125">Do not use this method.</span></span> <span data-ttu-id="65049-126">MAPI 不支持的配置文件的密码。</span><span class="sxs-lookup"><span data-stu-id="65049-126">MAPI does not support passwords for profiles.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="65049-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65049-127">See also</span></span>



[<span data-ttu-id="65049-128">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="65049-128">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)

