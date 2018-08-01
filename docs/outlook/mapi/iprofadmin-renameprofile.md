---
title: IProfAdminRenameProfile
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin.RenameProfile
api_type:
- COM
ms.assetid: 2a575cac-dbfd-4f42-9c10-4b7e355a065e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c94c60cf9ff1adbe2b54bd85b228e21b4be0e6e1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776002"
---
# <a name="iprofadminrenameprofile"></a><span data-ttu-id="ddd48-103">IProfAdmin::RenameProfile</span><span class="sxs-lookup"><span data-stu-id="ddd48-103">IProfAdmin::RenameProfile</span></span>

  
  
<span data-ttu-id="ddd48-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ddd48-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ddd48-105">向一个配置文件分配一个新名称。</span><span class="sxs-lookup"><span data-stu-id="ddd48-105">Assigns a new name to a profile.</span></span>
  
```cpp
HRESULT RenameProfile(
  LPSTR lpszOldProfileName,
  LPSTR lpszOldPassword,
  LPSTR lpszNewProfileName,
  ULONG_PTR ulUIParam,
  ULONG ulFlags
);
```

## <a name="parameters"></a><span data-ttu-id="ddd48-106">参数</span><span class="sxs-lookup"><span data-stu-id="ddd48-106">Parameters</span></span>

 <span data-ttu-id="ddd48-107">_lpszOldProfileName_</span><span class="sxs-lookup"><span data-stu-id="ddd48-107">_lpszOldProfileName_</span></span>
  
> <span data-ttu-id="ddd48-108">[in]一个指向当前重命名的配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="ddd48-108">[in] A pointer to the current name of the profile to rename.</span></span>
    
 <span data-ttu-id="ddd48-109">_lpszOldPassword_</span><span class="sxs-lookup"><span data-stu-id="ddd48-109">_lpszOldPassword_</span></span>
  
> <span data-ttu-id="ddd48-110">[in]始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="ddd48-110">[in] Always NULL.</span></span>
    
 <span data-ttu-id="ddd48-111">_lpszNewProfileName_</span><span class="sxs-lookup"><span data-stu-id="ddd48-111">_lpszNewProfileName_</span></span>
  
> <span data-ttu-id="ddd48-112">[in]一个指向重命名的配置文件的新名称。</span><span class="sxs-lookup"><span data-stu-id="ddd48-112">[in] A pointer to the new name of the profile to rename.</span></span>
    
 <span data-ttu-id="ddd48-113">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="ddd48-113">_ulUIParam_</span></span>
  
> <span data-ttu-id="ddd48-114">[in]任何对话框的父窗口或该方法显示的窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="ddd48-114">[in] A handle to the parent window of any dialog boxes or windows that this method displays.</span></span> 
    
 <span data-ttu-id="ddd48-115">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="ddd48-115">_ulFlags_</span></span>
  
> <span data-ttu-id="ddd48-116">[in]始终为 NULL。</span><span class="sxs-lookup"><span data-stu-id="ddd48-116">[in] Always NULL.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="ddd48-117">返回值</span><span class="sxs-lookup"><span data-stu-id="ddd48-117">Return value</span></span>

<span data-ttu-id="ddd48-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="ddd48-118">S_OK</span></span> 
  
> <span data-ttu-id="ddd48-119">已成功重命名配置文件。</span><span class="sxs-lookup"><span data-stu-id="ddd48-119">The profile was successfully renamed.</span></span>
    
<span data-ttu-id="ddd48-120">MAPI_E_LOGON_FAILED</span><span class="sxs-lookup"><span data-stu-id="ddd48-120">MAPI_E_LOGON_FAILED</span></span> 
  
> <span data-ttu-id="ddd48-121">配置文件密码不正确。</span><span class="sxs-lookup"><span data-stu-id="ddd48-121">The profile password is incorrect.</span></span>
    
<span data-ttu-id="ddd48-122">MAPI_E_USER_CANCEL</span><span class="sxs-lookup"><span data-stu-id="ddd48-122">MAPI_E_USER_CANCEL</span></span> 
  
> <span data-ttu-id="ddd48-123">用户取消操作，通常通过单击对话框中的**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="ddd48-123">The user canceled the operation, typically by clicking the **Cancel** button in a dialog box.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="ddd48-124">说明</span><span class="sxs-lookup"><span data-stu-id="ddd48-124">Remarks</span></span>

<span data-ttu-id="ddd48-125">如果有的话， **IProfAdmin::RenameProfile**方法向一个配置文件指定一个新名称。</span><span class="sxs-lookup"><span data-stu-id="ddd48-125">The **IProfAdmin::RenameProfile** method assigns a new name to a profile, if it has one.</span></span> <span data-ttu-id="ddd48-126">如果要重命名的配置文件，使用客户端调用**RenameProfile**时**RenameProfile**标记配置文件，并返回 S_OK 而不是使用配置文件时，尝试重命名操作。</span><span class="sxs-lookup"><span data-stu-id="ddd48-126">If the profile to rename is in use by a client when **RenameProfile** is called, **RenameProfile** marks the profile and returns S_OK instead of attempting the rename operation while the profile is in use.</span></span> <span data-ttu-id="ddd48-127">不再使用配置文件时， **RenameProfile**将其分配的新名称。</span><span class="sxs-lookup"><span data-stu-id="ddd48-127">When the profile is no longer being used, **RenameProfile** assigns it the new name.</span></span> 
  
<span data-ttu-id="ddd48-128">旧的和新的配置文件的名称可以是最多为 64 个字符的长度，并且可以包含下列字符：</span><span class="sxs-lookup"><span data-stu-id="ddd48-128">The old and new names of the profile can be up to 64 characters in length and can include the following characters:</span></span>
  
- <span data-ttu-id="ddd48-129">所有字母数字字符，包括重音字符和下划线字符。</span><span class="sxs-lookup"><span data-stu-id="ddd48-129">All alphanumeric characters, including accent characters and the underscore character.</span></span>
    
- <span data-ttu-id="ddd48-130">嵌入的空格，但不是前导或尾随空格。</span><span class="sxs-lookup"><span data-stu-id="ddd48-130">Embedded spaces, but not leading or trailing spaces.</span></span>
    
<span data-ttu-id="ddd48-131">_LpszPassword_应始终为 NULL 或为零长度字符串的指针。</span><span class="sxs-lookup"><span data-stu-id="ddd48-131">The  _lpszPassword_ should always be NULL or a pointer to a zero-length string.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ddd48-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ddd48-132">See also</span></span>



[<span data-ttu-id="ddd48-133">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="ddd48-133">IProfAdmin : IUnknown</span></span>](iprofadminiunknown.md)

