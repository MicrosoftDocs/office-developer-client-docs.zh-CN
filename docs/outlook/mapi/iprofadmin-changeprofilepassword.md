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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: c7124c8e3f2ced66d303321ff7aee8592a723a2b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420239"
---
# <a name="iprofadminchangeprofilepassword"></a><span data-ttu-id="eefe0-103">IProfAdmin::ChangeProfilePassword</span><span class="sxs-lookup"><span data-stu-id="eefe0-103">IProfAdmin::ChangeProfilePassword</span></span>

  
  
<span data-ttu-id="eefe0-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="eefe0-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="eefe0-105">已弃用。</span><span class="sxs-lookup"><span data-stu-id="eefe0-105">Deprecated.</span></span> <span data-ttu-id="eefe0-106">更改配置文件的密码。</span><span class="sxs-lookup"><span data-stu-id="eefe0-106">Changes the password for a profile.</span></span>
  
```cpp
HRESULT ChangeProfilePassword(
  LPSTR lpszProfileName,
  LPSTR lpszOldPassword,
  LPSTR lpszNewPassword,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="eefe0-107">参数</span><span class="sxs-lookup"><span data-stu-id="eefe0-107">Parameters</span></span>

 <span data-ttu-id="eefe0-108">_lpszProfileName_</span><span class="sxs-lookup"><span data-stu-id="eefe0-108">_lpszProfileName_</span></span>
  
> <span data-ttu-id="eefe0-109">[in]指向与要更改的密码关联的配置文件的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="eefe0-109">[in] A pointer to the name of the profile associated with the password to be changed.</span></span>
    
 <span data-ttu-id="eefe0-110">_lpszOldPassword_</span><span class="sxs-lookup"><span data-stu-id="eefe0-110">_lpszOldPassword_</span></span>
  
> <span data-ttu-id="eefe0-111">[in]指向当前密码的指针。</span><span class="sxs-lookup"><span data-stu-id="eefe0-111">[in] A pointer to the current password.</span></span>
    
 <span data-ttu-id="eefe0-112">_lpszNewPassword_</span><span class="sxs-lookup"><span data-stu-id="eefe0-112">_lpszNewPassword_</span></span>
  
> <span data-ttu-id="eefe0-113">[in]指向新密码的指针。</span><span class="sxs-lookup"><span data-stu-id="eefe0-113">[in] A pointer to the new password.</span></span>
    
 <span data-ttu-id="eefe0-114">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="eefe0-114">_ulFlags_</span></span>
  
> <span data-ttu-id="eefe0-115">[in]控制传入字符串类型的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="eefe0-115">[in] A bitmask of flags that controls the type of the passed-in strings.</span></span> <span data-ttu-id="eefe0-116">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="eefe0-116">The following flag can be set:</span></span>
    
<span data-ttu-id="eefe0-117">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="eefe0-117">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="eefe0-118">配置文件名称和密码采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="eefe0-118">The profile name and passwords are in Unicode format.</span></span> <span data-ttu-id="eefe0-119">如果未MAPI_UNICODE，则这些字符串采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="eefe0-119">If the MAPI_UNICODE flag is not set, these strings are in ANSI format.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="eefe0-120">返回值</span><span class="sxs-lookup"><span data-stu-id="eefe0-120">Return value</span></span>

<span data-ttu-id="eefe0-121">S_OK</span><span class="sxs-lookup"><span data-stu-id="eefe0-121">S_OK</span></span> 
  
> <span data-ttu-id="eefe0-122">如果调用此方法，它将返回S_OK。</span><span class="sxs-lookup"><span data-stu-id="eefe0-122">If this method is called, it will return S_OK.</span></span> <span data-ttu-id="eefe0-123">但是，不会执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="eefe0-123">However, no action will be taken.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="eefe0-124">备注</span><span class="sxs-lookup"><span data-stu-id="eefe0-124">Remarks</span></span>

<span data-ttu-id="eefe0-125">请勿使用此方法。</span><span class="sxs-lookup"><span data-stu-id="eefe0-125">Do not use this method.</span></span> <span data-ttu-id="eefe0-126">MAPI 不支持配置文件的密码。</span><span class="sxs-lookup"><span data-stu-id="eefe0-126">MAPI does not support passwords for profiles.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="eefe0-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eefe0-127">See also</span></span>



[<span data-ttu-id="eefe0-128">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="eefe0-128">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)

